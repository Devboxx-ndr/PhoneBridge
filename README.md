# PhoneBridge

[فارسی](README_FA.md) · [Privacy](PRIVACY.md) · [Usage terms](DISCLAIMER.md)

A free Android-to-browser companion for your own devices. Install one Android APK and use Safari on iPhone over the same Wi-Fi or hotspot. No iPhone App Store app or dedicated server is required. Application source remains private; this repository contains distribution documentation only.

[Download latest APK](https://github.com/Devboxx-ndr/PhoneBridge/releases/latest/download/PhoneBridge.apk) · [Releases](https://github.com/Devboxx-ndr/PhoneBridge/releases)

Current publication: **2.7.1**, versionCode **15**, package **local.phonebridge**, Android **8.0+**.

## Features

- Real SMS conversations, contacts, replies and user-initiated sending through Android's SIM. Multiple recipients receive separate SMS; carrier charges may apply.
- Recent calls and live call status, available SIM filters/custom names; unidentified records remain in All.
- Separate Android-selected shared folders, upload/download, progress and download history. Unshare folders without deleting their files. Streaming limits memory; resume depends on the browser, provider and valid authentication.
- Manual local Chat for text/links, Copy, Android battery display, themes and three font sizes.
- Permission-dependent navigation. PhoneBridge-local read marking does not change Android's SMS database.
- Foreground PWA alerts/quick replies while open. This version has no closed-PWA Web Push, remote call answer/end or call audio forwarding.

## Install and connect

1. Download the signed APK and SHA256SUMS.txt from Releases. Verify the checksum. Allow installation from your downloading app only if you trust the file; keep Play Protect enabled.
2. Open PhoneBridge on Android, allow only the optional access you need, select shared folders through Android's picker and start the bridge. Its running notification stays visible.
3. Connect both devices to the same Wi-Fi or hotspot. Guest-network isolation, VPN/firewall settings or changed IP addresses can prevent access. No brand allowlist is applied; universal device/carrier compatibility is not guaranteed.
4. Open the exact setup address shown by Android. Setup uses HTTP; private traffic uses local HTTPS, normally port 8080. Do not guess the scheme or port.
5. On iPhone, install the certificate-only profile from your own Android and enable full trust at Settings → General → About → Certificate Trust Settings. Compare its identity with Android. A profile's Not Signed label differs from TLS trust; do not routinely bypass certificate mismatch warnings.
6. Scan Android's private pairing QR, or use Scan QR/Paste Pairing Link on the pairing page. In Safari choose Share → Add to Home Screen. Use a recent Safari and keep Android's bridge running.

Brief outages may reconnect while the same bridge, session and origin survive. Changed IPs, expired sessions, updates or service restarts may need the current address/new pairing. Sessions normally last 12 hours; authorized transfers can renew access. Avoid Internet exposure/port forwarding.

## Updates and support

Install updates over the existing app with the same package/signer. Do not uninstall or clear storage to force an update. Old debug-signed copies need separate consideration; see [release notes](RELEASE_NOTES.md). Play Protect clearance and physical migration testing are not claimed.

[Report a bug](https://github.com/Devboxx-ndr/PhoneBridge/issues/new?template=bug_report.yml) · [Suggest a feature](https://github.com/Devboxx-ndr/PhoneBridge/issues/new?template=feature_request.yml)

Issues are public. Never include real SMS, phone numbers, pairing QR/links, credentials, private keys or personal files. See [release process/statistics](RELEASING.md), [changelog](CHANGELOG.md) and [screenshots](screenshots/README.md).
