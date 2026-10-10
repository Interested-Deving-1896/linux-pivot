[update-readmes]   Mode: rewrite — migrating to template structure...
# linux-pivot

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/linux-pivot) [![KDE Eco](https://img.shields.io/badge/KDE%20Eco-certified-brightgreen?logo=kde&logoColor=white&style=flat-square)](https://eco.kde.org/) [![Blue Angel](https://img.shields.io/badge/Blue%20Angel-DE--UZ%20215-0055a4?style=flat-square)](https://www.blauer-engel.de/en/certification/criteria)



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
| Contributor | Commits |
|---|---|
| [@Interested-Deving-1896](https://github.com/Interested-Deving-1896) | 101 |
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream influences recorded._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

## Accessibility

<!-- AI:start:accessibility -->
This repo uses automated accessibility auditing via `check-accessibility.yml`.

Checks include: CODEOWNERS ownership coverage, README screen-reader compatibility,
WCAG 2.1 AA HTML compliance, audio overview (espeak-ng), and Braille output (liblouis).




Run the [Check Accessibility](https://github.com/Interested-Deving-1896/linux-pivot/actions/workflows/check-accessibility.yml)
workflow to generate the first report and accessibility artifacts.
See the [W3C Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/)
for the underlying accessibility reference.
<!-- AI:end:accessibility -->

## License

<!-- AI:start:license -->
[GPL-3.0](https://github.com/Interested-Deving-1896/linux-pivot/blob/main/LICENSE) © 2026 [Interested-Deving-1896](https://github.com/Interested-Deving-1896)
<!-- AI:end:license -->
