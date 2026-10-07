# FXMP.org Tools Releases

This public repository distributes signed Windows update bundles, update manifests, and Windows installers for FXMP.org Tools.

The application source remains in the private [`fxmp-tools` repository](https://github.com/Mesrine67/fxmp-tools). This repository contains release artifacts only; it does not contain application source code.

## Downloads

Use the latest release below for the standard Windows installer. The application updater reads the signed `latest.json` manifest attached to each release.

- [Latest FXMP.org Tools release](https://github.com/Mesrine67/fxmp-tools-releases/releases/latest)
- [Private application source and issue tracking](https://github.com/Mesrine67/fxmp-tools)

## Verification

Updater packages are signed with Tauri's updater signing key. The public verification key is embedded in the application. Never replace signed release assets or publish a manifest without the matching Tauri-generated signatures.

Windows Authenticode signing is a separate process and is not implied by the updater signature.
