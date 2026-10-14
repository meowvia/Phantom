# Privacy Policy

**Effective Date: October 2026**

Phantom ("the Application") is built with a strict local-first, privacy-by-design architecture. This Privacy Policy details how data is handled when you use the Application.

---

## 1. Zero Network Transmission (100% Offline)

- **No Network Capabilities**: The Application binary does not request or include network entitlements (`com.apple.security.network.client` or `com.apple.security.network.server`).
- **Zero Outbound Connections**: The Application never opens outbound sockets, initiates HTTP requests, or communicates with external servers.
- **Verification**: You may verify network isolation using macOS Console (`Console.app`), LuLu, Little Snitch, or by inspecting application code signatures and entitlements via `codesign -d --entitlements :- /Applications/Phantom.app`.

---

## 2. Zero Telemetry & Data Collection

- **No Analytics**: We do not collect, aggregate, or transmit analytics, telemetry, user behavioral patterns, crash reports, or diagnostic information.
- **No Identifiers**: We do not generate or track hardware identifiers (UDID, MAC addresses, serial numbers) or user identities.
- **No Third-Party SDKs**: The Application contains zero third-party tracking, advertising, analytics, or monitoring frameworks.

---

## 3. Storage of Credentials & Metadata

- **Master Credentials**: Your master password hash is salted and derived locally using PBKDF2-HMAC-SHA256 (100,000 iterations). Authentication tokens are retained within the local macOS System Keychain (`kSecClassGenericPassword` with `kSecAttrAccessibleAfterFirstUnlockThisDeviceOnly`), restricted to your local machine.
- **Recovery Key**: The high-entropy Recovery Key generated during onboarding is displayed strictly on-screen for local archiving. It is never transmitted or written to unencrypted shared logs.
- **Vault Metadata**: Managed file paths and display preferences are stored exclusively on your local storage drive under `~/Library/Application Support/Phantom/`.

---

## 4. File Content Integrity

The Application alters only standard macOS filesystem attributes (`UF_HIDDEN`, `UF_IMMUTABLE`, POSIX permissions, and extended attributes `xattr`). It never copies, uploads, or alters the interior byte payload of your managed files.

---

## 5. Contact

For privacy-related inquiries or technical verification queries, please contact: `privacy@meowvia.com`.
