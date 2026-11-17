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

### Test builds

Test builds come on the `mac-test` channel: a prerelease, replaced by each new build. Copies installed from it update to each new test build.

macOS (Terminal):

```bash
curl -fsSL https://github.com/rinkans/rz-releases/releases/download/mac-test/install.sh | sh -s -- --channel mac-test
```

Windows (PowerShell):

```powershell
$env:RZ_CHANNEL = 'mac-test'; irm https://github.com/rinkans/rz-releases/releases/download/mac-test/install.ps1 | iex
```

## Updates

Installed copies update themselves. Each release's `manifest.json` is signed with minisign. rz installs a download only if that signature checks out against the key built into rz, and the download's size and SHA-256 match the manifest. If a new version doesn't start properly, rz puts the previous one back.
