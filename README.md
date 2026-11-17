# rz releases

Builds of rz, a keyboard-first window manager layer for Windows and macOS. The source lives in a private repo; this one holds the releases, which installed copies of rz check for updates.

## Install

### macOS (Intel and Apple Silicon)

With [Homebrew](https://brew.sh):

```bash
brew install rinkans/rz/rz
brew services start rz
```

Then allow rz to place windows: **System Settings > Privacy & Security > Accessibility**, switch on **rz**. Update with `brew upgrade rz`. The tap is [rinkans/homebrew-rz](https://github.com/rinkans/homebrew-rz).

Without Homebrew (rz then updates itself):

```bash
curl -fsSL https://github.com/rinkans/rz-releases/releases/latest/download/install.sh | sh
```

### Windows (PowerShell)

```powershell
irm https://github.com/rinkans/rz-releases/releases/latest/download/install.ps1 | iex
```

### Test builds

Test builds come on the `mac-test` channel: a prerelease, replaced by each new build. Copies installed from it update to each new test build.

```bash
curl -fsSL https://github.com/rinkans/rz-releases/releases/download/mac-test/install.sh | sh
```

## Updates

Installed copies update themselves (Homebrew's through `brew upgrade`). Each release's `manifest.json` is signed with minisign. rz installs a download only if that signature checks out against the key built into rz, and the download's size and SHA-256 match the manifest. If a new version doesn't start properly, rz puts the previous one back.
