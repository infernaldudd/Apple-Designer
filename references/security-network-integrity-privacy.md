# Security: Network, App Integrity, Privacy, Entitlements, and Distribution

## Networking

### App Transport Security (ATS)
Keep ATS protections enabled. Prefer HTTPS/TLS with valid trust configuration. Do not add broad arbitrary-load exceptions as a convenience workaround. If an exception is unavoidable, scope it narrowly and document why.

For custom low-level protocols, use Network framework/TLS appropriately; for ordinary HTTP(S), prefer URLSession/high-level APIs.

## App integrity / anti-fraud

Use DeviceCheck/App Attest when a server needs higher confidence that sensitive requests originate from a legitimate instance of your app on an Apple device.

Rules:
- treat attestation as one signal in risk assessment, not magic proof
- server verifies attestations/assertions
- protect sensitive resources at the server boundary; do not rely on client self-checks
- handle unsupported devices gracefully

## Privacy

Collect the minimum data needed for the feature. Ask for protected-resource permissions contextually, after the person understands the value.

### Privacy manifests
Maintain a valid `PrivacyInfo.xcprivacy` where required. Accurately declare:
- data types collected
- whether data is linked to identity
- tracking use
- collection purposes
- required-reason API usage
- tracking domains when applicable

Never invent an approved reason to justify fingerprinting or unrelated data collection.

## App Sandbox and entitlements

Use App Sandbox on macOS where required/appropriate. Grant only the capabilities the app actually needs. Treat entitlements as security permissions, not switches to enable casually.

For Hardened Runtime:
- keep protections enabled
- add exceptions only for genuine requirements
- avoid broad runtime exceptions

For shared containers/App Groups/keychain groups, keep membership minimal and validate data crossing process boundaries.

## Signing and distribution

- Sign code correctly so the system can verify origin and detect tampering.
- For direct macOS distribution, follow current Developer ID, Hardened Runtime, timestamp, and notarization requirements.
- Verify entitlements and signatures in release builds, not only debug builds.
- Treat notarization as an additional distribution security check, not as a substitute for secure code.

## Web views and web extensions

- Use WKWebView, not deprecated UIWebView.
- Restrict navigation and custom schemes to intended destinations.
- Disable or avoid powerful web capabilities when the content does not need them.
- For Safari web extensions, request the smallest host/API permission set; use optional permissions for optional features when possible.

## Security UI rules

- Explain sensitive actions before triggering system authorization.
- Show exact scope: what data/action is being requested and why.
- Do not guilt users for denying a permission.
- Provide a functional degraded path when feasible.
- Never fake system security alerts, permission sheets, biometric prompts, or certificate dialogs.

## Sources

- https://developer.apple.com/documentation/bundleresources/information-property-list/nsapptransportsecurity
- https://developer.apple.com/documentation/Security/preventing-insecure-network-connections
- https://developer.apple.com/documentation/network
- https://developer.apple.com/documentation/devicecheck
- https://developer.apple.com/documentation/DeviceCheck/establishing-your-app-s-integrity
- https://developer.apple.com/documentation/security/certificate-key-and-trust-services
- https://developer.apple.com/documentation/security/app_sandbox
- https://developer.apple.com/documentation/security/hardened-runtime
- https://developer.apple.com/documentation/bundleresources/security-entitlements
- https://developer.apple.com/documentation/bundleresources/adding-a-privacy-manifest-to-your-app-or-third-party-sdk
- https://developer.apple.com/documentation/bundleresources/describing-data-use-in-privacy-manifests
- https://developer.apple.com/documentation/bundleresources/describing-use-of-required-reason-api
- https://developer.apple.com/documentation/xcode/using-the-latest-code-signature-format
- https://developer.apple.com/documentation/Security/notarizing-macos-software-before-distribution
- https://developer.apple.com/documentation/safariservices/managing-safari-web-extension-permissions
