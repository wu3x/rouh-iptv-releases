# ROUH IPTV — Public Downloads

This repository contains **only public release binaries and version metadata** for the ROUH IPTV apps. Application source code stays in the private repositories.

## Latest builds

- [Android signed APK](https://github.com/wu3x/rouh-iptv-releases/releases/download/android-latest/ROUH-IPTV-Android.apk)
- [iOS unsigned IPA](https://github.com/wu3x/rouh-iptv-releases/releases/download/ios-latest/ROUH-IPTV-iOS-unsigned.ipa)

The links become available after the first successful publication. The iOS IPA requires external signing and provisioning before installation.

## How publishing works

Each private application's GitHub Actions build publishes to its own **rolling prerelease** in this repository:
- Android: `android-latest`
- iOS: `ios-latest`

A fine-grained GitHub token with **Contents: Read and write** permission for **this repository only** is stored as an Actions secret named `RELEASES_PUBLISH_TOKEN` in each private app repository. Never put this token in source code.

Version check APIs:
- Android: https://api.github.com/repos/wu3x/rouh-iptv-releases/releases/tags/android-latest
- iOS: https://api.github.com/repos/wu3x/rouh-iptv-releases/releases/tags/ios-latest

These are development builds, not independently audited or store-distributed releases.
