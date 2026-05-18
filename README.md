# CloudGuard — Downloads

Public installer downloads for **CloudGuard**, an autonomous quality, security and performance scanner for Salesforce orgs. Connect any org, run a scan, get prioritized findings with AI insights — no Salesforce CLI, Java or Python required on the host. Everything is bundled in the installer.

> Source code lives in a private repo. This repo only hosts release binaries.

## Latest release

See the [Releases page](https://github.com/delbruck/cloudguard-downloads/releases/latest) for direct download links.

| Platform | File | Notes |
| --- | --- | --- |
| macOS (Apple Silicon + Intel, universal) | `CloudGuard_*_universal.dmg` | Mount, drag CloudGuard.app to Applications |
| Windows 10/11 (x64) | `CloudGuard_*_x64-setup.exe` | NSIS installer (recommended) |
| Windows 10/11 (x64) | `CloudGuard_*_x64_en-US.msi` | MSI for managed deployments |

## First-run notes — unsigned builds

These builds are not code-signed yet, so each OS will warn you on first launch. The app itself is safe; the warnings are just because Apple/Microsoft don't recognize the publisher.

### macOS — Gatekeeper

After dragging CloudGuard.app to Applications, the first launch will be blocked with **"CloudGuard.app cannot be opened because the developer cannot be verified"**.

- Open **System Settings → Privacy & Security**, scroll to the bottom, click **Open Anyway** next to the CloudGuard message.
- Or run once from Terminal to clear the quarantine bit:
  ```
  xattr -dr com.apple.quarantine /Applications/CloudGuard.app
  ```

### Windows — SmartScreen

The installer will show **"Windows protected your PC"**.

- Click **More info → Run anyway**.

## What's inside the bundle

Each installer is ~120–140 MB because it ships a self-contained runtime tree so end users don't need anything pre-installed:

- Salesforce CLI (`sf`) + `code-analyzer` plugin
- Temurin JRE 11
- CPython 3.11
- Accenture Apex PMD ruleset (default rule selector)

Bundles are extracted on first launch to your app data directory and reused on subsequent runs.

## Issues / feedback

For now, please reach the maintainer directly. A public issue tracker may be opened later.
