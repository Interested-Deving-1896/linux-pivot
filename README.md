# linux-pivot

Distro-agnostic, arch-agnostic Linux system converter. Converts a running
system (or a rootfs directory) from one distro to another, preserving users,
home directories, hostname, fstab, network config, and services. Optionally
converts the kernel via [lkf](https://github.com/lkf-project/lkf).

## Supported distros

| Distro | Extract | Install |
|--------|---------|---------|
| Debian | ✓ | ✓ |
| Ubuntu | ✓ | ✓ |
| Devuan | ✓ | ✓ |
| Arch Linux | ✓ | ✓ |
| Fedora | ✓ | ✓ |
| Alpine | ✓ | ✓ |
| Void | ✓ | ✓ |
| openSUSE | ✓ | ✓ |
| Gentoo | ✓ | ✓ |

## Supported architectures

`amd64` `arm64` `armhf` `riscv64` `ppc64el` `s390x` `loong64` `i386`

Cross-arch conversions use `qemu-user-static` + `binfmt_misc` automatically.

## Usage

```bash
# Convert running system to Debian
sudo ./pivot.sh --to debian

# Convert to Arch Linux targeting arm64
sudo ./pivot.sh --to arch --arch arm64

# Convert to Gentoo and rebuild kernel as ebuild
sudo ./pivot.sh --to gentoo --kernel-convert

# Extract manifest only (no install)
sudo ./pivot.sh --extract-only --manifest /tmp/my-system.toml

# Apply an existing manifest to a target distro
sudo ./pivot.sh --from /tmp/my-system.toml --to fedora

# Dry run (show what would happen)
sudo ./pivot.sh --to ubuntu --dry-run
```

## How it works

1. **Extract** — a per-distro extractor script reads the source system and
   writes a `system.manifest.toml` capturing: hostname, arch, timezone, locale,
   users, groups, installed packages, enabled services, fstab, and network
   config.

2. **Translate** — `lib/pkgmap.sh` maps package names across distros using
   `config/package-map.toml`.

3. **Install** — a per-distro installer script bootstraps the target rootfs
   (debootstrap / pacstrap / dnf --installroot / etc.), then applies the
   manifest: creates users, restores home directories, enables services,
   writes fstab and network config.

4. **Kernel** (optional) — `kernel/convert.sh` uses lkf to repackage the
   running kernel for the target distro's package format.

## Directory layout

```
pivot.sh                  # main entry point
lib/
  log.sh                  # logging helpers
  arch.sh                 # arch detection + QEMU setup
  manifest.sh             # TOML manifest read/write
  pkgmap.sh               # cross-distro package name translation
  chroot.sh               # chroot helpers
config/
  manifest.schema.toml    # manifest field definitions
  package-map.toml        # canonical → per-distro package name table
extractors/               # per-distro: read system state → manifest
installers/               # per-distro: apply manifest → target rootfs
kernel/
  detect.sh               # kernel version/config detection
  convert.sh              # lkf integration
.github/workflows/
  ci.yml                  # shellcheck + extract + pkgmap + dry-run matrix
```

## Requirements

- Root / sudo
- `bash` 4.4+
- `python3` (for manifest and pkgmap helpers)
- Distro bootstrap tool for the target (installed automatically if missing):
  `debootstrap`, `pacstrap`, `dnf`, `apk`, `xbps-install`, `zypper`, `emerge`
- For cross-arch: `qemu-user-static`, `binfmt-support`

## penguins-pivot

[penguins-pivot](https://github.com/Interested-Deving-1896/penguins-pivot) is
a fork of this project wired into the
[penguins-eggs](https://github.com/pieroproietti/penguins-eggs) all-features
ecosystem, enabling live-ISO-based distro conversion.

## License

MIT
