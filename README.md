# Apple UI Engineering Skill

A reusable skill pack for Apple-native and Apple-inspired frontend work. It combines current Apple design guidance with implementation routing for SwiftUI, UIKit, AppKit, Core Animation, graphics/media frameworks, accessibility, and defensive security/privacy practices.

## Install concept

Place the `apple-ui-engineering-skill` directory in your harness's supported skills directory, or copy `SKILL.md` plus the `references/`, `qa/`, `tests/`, and `templates/` folders into an existing skills repository.

## What is included

- Apple design-system reasoning and anti-slop rules
- Liquid Glass usage/implementation constraints
- layout, typography, color, symbols, navigation, input
- SwiftUI/UIKit/AppKit/Core Animation routing
- haptics, Core Graphics/Core Image/Metal, AVKit, MapKit, PencilKit, WebKit, RealityKit/visionOS
- accessibility state matrix
- Keychain, LocalAuthentication, passkeys, CryptoKit/Secure Enclave, data protection
- ATS, Network, App Attest, privacy manifests, sandbox/hardened runtime, signing/notarization
- hard rejection rules, scorecard, and pressure scenarios

## Update policy

Apple's design system and SDKs evolve. Re-check live Apple documentation for high-stakes implementation or after major SDK releases; `references/source-catalog.md` provides the source map.
