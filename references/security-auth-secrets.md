# Security: Authentication, Secrets, and Sensitive Local Data

This module is defensive. Its goal is to make Apple-platform frontend work secure by default.

## Trust boundary rule

Do not imitate system trust UI. Let Apple/system frameworks own biometric, passkey, credential, permission, certificate, and other trust-sensitive prompts whenever possible. App-owned UI should explain **why** an action is needed and what will happen, then hand off to the system.

## Authentication

### LocalAuthentication
Use `LAContext` to evaluate device-owner authentication policies with Face ID, Touch ID, Optic ID, passcode/password fallback as supported. The app receives success/failure; it does not receive biometric templates.

Rules:
- provide accurate purpose messaging
- include required usage description keys (for example Face ID where applicable)
- handle unavailable/locked-out/cancelled states
- do not treat biometrics alone as a server identity protocol; combine with your app/server authentication model

### AuthenticationServices
Prefer system authorization flows for:
- passkeys
- Sign in with Apple
- password AutoFill/credential requests

Use system sheets/inline credential UI rather than custom password/passkey pickers.

## Secrets

### Keychain
Use Keychain Services for small secrets such as credentials, tokens, cryptographic keys/identities, and sensitive small values. Do not put secrets in UserDefaults/plain preferences, source code, analytics, crash messages, or normal logs.

Choose accessibility intentionally:
- when unlocked
- after first unlock only when background behavior requires it
- passcode/user-presence/biometric restrictions when the sensitivity warrants it

Use `SecAccessControl` when access should require user presence or stronger conditions.

### CryptoKit / Secure Enclave
Use CryptoKit high-level primitives instead of inventing cryptographic algorithms. Use Secure Enclave-backed keys when the threat model benefits from hardware-bound private-key operations. Store/export key material appropriately; use Keychain for persistent key storage when required.

Never:
- design your own cipher/protocol because it feels simpler
- hardcode encryption keys in the app bundle
- log plaintext secrets or private keys

## File data protection

Use iOS/iPadOS data protection classes appropriate to the file's lifecycle. Prefer the strongest level compatible with the feature; personal/user-created sensitive files generally deserve strong protection. Handle the possibility that protected data becomes unavailable while the device is locked.

## Cross-app sharing

Use App Groups and Keychain Access Groups only when related apps/extensions genuinely need shared data. Keep group membership and shared data minimal.

## Sources

- https://developer.apple.com/documentation/localauthentication
- https://developer.apple.com/documentation/localauthentication/lacontext
- https://developer.apple.com/documentation/authenticationservices
- https://developer.apple.com/documentation/authenticationservices/supporting-passkeys/
- https://developer.apple.com/documentation/security/keychain-services/
- https://developer.apple.com/documentation/security/using-the-keychain-to-manage-user-secrets
- https://developer.apple.com/documentation/security/restricting-keychain-item-accessibility
- https://developer.apple.com/documentation/security/secaccesscontrol
- https://developer.apple.com/documentation/cryptokit
- https://developer.apple.com/documentation/cryptokit/storing-cryptokit-keys-in-the-keychain
- https://developer.apple.com/documentation/uikit/encrypting-your-app-s-files
- https://developer.apple.com/documentation/bundleresources/entitlements/com.apple.security.application-groups
