# Security Policy

## 1. Supported Versions

| Version | Supported |
| :--- | :--- |
| 0.1.x-Beta | Yes |
| < 0.1.0 | No |

---

## 2. Security Architecture & Threat Model

Phantom is designed as a native macOS in-place privacy guard and anti-snooping utility. Understanding its protection boundaries is essential for proper deployment.

### What Phantom Protects Against (In-Scope)
- **Casual Bystander Snooping**: Hides files and folders in-place so they do not appear in Finder directory views.
- **System Search & Index Leakage**: Strips metadata visibility from Spotlight searches, Siri suggestions, and Recent Items.
- **Accidental Exposure**: Prevents inadvertent sharing via AirDrop discovery lists, screen sharing, presentation sessions, or temporary Mac lending.
- **Inadvertent File Alteration**: Sets POSIX permissions to `000` and activates `UF_IMMUTABLE` flags on locked items to block accidental modification or deletion.

### What Phantom Does Not Protect Against (Out-of-Scope)
- **Cryptographic File Payload Encryption**: Phantom does not rewrite or re-encode file contents with block ciphers. File data remains at original physical disk blocks to avoid write-interruption and data loss risks on multi-gigabyte files.
- **Same-User Process or Terminal Access**: Any process or terminal session running under the same macOS user account with appropriate permissions (e.g., executing `chflags` or `chmod`) can read the underlying files.
- **Digital Forensics & Raw Disk Access**: Physical extraction of storage media or forensic block-level inspection tools can read raw file blocks directly from unencrypted partitions.
- **Backup Duplication**: Standard file-based backups (such as Time Machine) may archive hidden files if configured to traverse all user paths.

For high-threat environments requiring defense against physical hardware seizure or hostile forensic inspection, users should combine Phantom with full-disk encryption (FileVault) or specialized cryptographic disk images.

---

## 3. Reporting a Vulnerability

We take the security of Phantom seriously. If you identify a security vulnerability, privilege escalation flaw, or unintended credential exposure:

1. **Do not disclose the issue publicly** in public GitHub issues, pull requests, or discussion forums.
2. Submit your report directly via **GitHub Private Vulnerability Reporting** on the repository, or email `security@meowvia.com`.
3. Include detailed steps to reproduce the issue, macOS version, chip architecture, and any proof-of-concept scripts.

We will acknowledge receipt within 48 hours and provide an estimated timeline for remediation.
