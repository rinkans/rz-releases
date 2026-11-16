# rz releases

Builds of rz, a keyboard-first window manager layer for Windows and macOS. The source lives in a private repo; this one holds the releases, which installed copies of rz check for updates.

## Install

Windows (PowerShell):

```powershell
irm https://github.com/rinkans/rz-releases/releases/latest/download/install.ps1 | iex
```

macOS (Terminal):

```bash
curl -fsSL https://github.com/rinkans/rz-releases/releases/latest/download/install.sh | sh
```

Test builds follow the `mac-test` channel:
- **macOS:** add `-s -- --channel mac-test` after `sh`.
- **Windows:** run `$env:RZ_CHANNEL = 'mac-test'` first.

## Updates

Installed copies update themselves. Each release's `manifest.json` is signed with minisign. rz installs a download only if that signature checks out against the key built into rz, and the download's size and SHA-256 match the manifest. If a new version doesn't start properly, rz puts the previous one back.
