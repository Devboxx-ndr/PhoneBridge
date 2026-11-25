# Privacy policy — PhoneBridge 2.7.1

Effective upon publication. Scope: local.phonebridge, versionCode 15.

PhoneBridge processes permitted SMS content/addresses/times, contact names/numbers, call history/status, SIM information, selected shared files/transfer metadata, Android battery state and manually submitted Chat text. Private data goes to the authenticated paired browser over the local network. This version has no developer-operated relay, advertising/analytics SDK or closed-app Web Push. SMS content/recipients are also processed by the user's carrier and may incur charges.

## Android permissions

| Permission | Purpose |
|---|---|
| INTERNET | Local web server; user-selected external links |
| ACCESS_NETWORK_STATE | Local Wi-Fi/hotspot addressing |
| READ_SMS / SEND_SMS | Read conversations / explicitly send composed SMS |
| READ_CONTACTS | Names and recipient selection |
| READ_CALL_LOG | Recent calls |
| READ_PHONE_STATE | Call state and available SIM information |
| POST_NOTIFICATIONS | Visible bridge notification where required |
| FOREGROUND_SERVICE / FOREGROUND_SERVICE_SPECIAL_USE | User-started bridge while Android activity is closed |

SMS/contact/call permissions are optional and revocable in Android Settings. Files use user-selected Storage Access Framework grants, not all-files permission. This release requests no root, Accessibility, device administration, microphone, location or APK-install permission. Web QR scanning uses browser camera permission. Copy may use the browser clipboard; no continuous clipboard monitoring occurs.

## Storage, retention and deletion

Android retains preferences, selected-folder grants and TLS identity; the private CA key is held in Android Keystore. Sessions, message/call snapshots and bounded Chat history are in service memory. Stopping the service ends sessions and clears Chat. Upload staging/metadata may persist in private app storage; completed destination files remain in selected folders. Browser storage holds interface preferences, local read markers, SIM names and download history; secure cookies authenticate sessions. Browser/device controls govern their storage and deletion and any downloaded files. The service-worker cache holds app-shell assets, not an intentional offline SMS/call database.

Stop the bridge, log out, revoke folder shares/Android permissions and clear site data as appropriate. Uninstalling removes app-managed data/identity subject to Android behavior, but does not delete original SMS/call records or exported files. Remove the iPhone certificate profile separately when no longer needed. PhoneBridge read markers do not change Android's SMS database.

## Security and third parties

Private requests use local TLS and pairing authentication. HTTP setup serves certificate/setup diagnostics, not the SMS API. Pairing links and session credentials are private. Install only the certificate from your own Android: a trusted CA permits certificates it signs. This build does not install MDM or an interception proxy. Downloading the APK from GitHub itself needs no PhoneBridge certificate installation.

GitHub handles repository visits, downloads and public Issues under its own policy. Do not post personal records in Issues. The developer profile/donation information intentionally visible in the APK remains with the owner's permission; it is not telemetry. External profile/payment providers have their own policies. PhoneBridge does not process payments itself.

For privacy questions, open an Issue without sensitive information to request an appropriate contact route. Review/redact logs before sharing them.
