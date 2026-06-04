[update-readmes]   Mode: rewrite — migrating to template structure...
# linux-pivot

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/linux-pivot)

<!-- AI:start:what-it-does -->
_Description pending._
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
_Architecture documentation pending._
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/linux-pivot.git
cd linux-pivot
```

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

## Configuration

<!-- Document configuration options here. This section is yours — the AI will not modify it. -->

## CI

<!-- AI:start:ci -->
_CI documentation pending._
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/linux-pivot`](https://github.com/Interested-Deving-1896/linux-pivot) and mirrored through:

```
Interested-Deving-1896/linux-pivot  ──►  OpenOS-Project-OSP/linux-pivot  ──►  OpenOS-Project-Ecosystem-OOC/linux-pivot
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
_Contributors pending._
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream fork._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

## License

<!-- AI:start:license -->
<!-- License not detected — add a LICENSE file to this repo. -->
<!-- AI:end:license -->
