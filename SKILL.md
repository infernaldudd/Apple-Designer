---
name: apple-ui-engineering
description: Use when designing, reviewing, or implementing Apple-platform or Apple-inspired interfaces, including SwiftUI, UIKit, AppKit, Liquid Glass, motion, haptics, accessibility, responsive layout, and security/privacy-sensitive frontend flows.
---

# Apple UI Engineering

## Core principle

Apple-like UI is not a blur recipe. Build from **purpose, platform conventions, content hierarchy, native interaction semantics, adaptive layout, restrained materials, meaningful motion, accessibility, and secure system flows**. Visual polish comes after those foundations.

## Choose the operating mode

1. **APPLE_NATIVE** — SwiftUI, UIKit, AppKit, visionOS. Prefer Apple system components and framework behavior before custom recreation.
2. **APPLE_DESIGN_LANGUAGE** — web, React, Electron, Tauri, Windows, cross-platform. Translate Apple principles; do not pretend non-Apple UI is native system UI.
3. **APPLE_SPATIAL** — visionOS or spatial UI. Add depth, gaze/gesture ergonomics, windows/volumes/spaces, and RealityKit guidance.

## Load the right references

For every UI task, read:
- `references/design-system.md`
- `references/layout-typography-color.md`
- `references/components-navigation-input.md`
- `references/accessibility.md`

If glass/materials appear, also read `references/liquid-glass.md`.
If anything animates or reacts physically, read `references/motion-animation-haptics.md`.
If rendering, media, maps, drawing, web content, symbols, or 3D/spatial content matter, read `references/graphics-media-spatial.md` and `references/frontend-framework-router.md`.
If the feature touches authentication, secrets, permissions, personal data, networking, web views/extensions, entitlements, app integrity, signing, or distribution, read both security references.

## Build order

1. State the user task and primary action.
2. Identify platform, input methods, window/screen behavior, and accessibility constraints.
3. Establish information hierarchy and navigation semantics.
4. Prefer standard components; customize only where the product genuinely needs it.
5. Establish responsive layout, typography, semantic color, and iconography.
6. Add material only where it communicates elevation/function.
7. Add motion/haptics only where they explain state, continuity, causality, or confirmation.
8. Verify accessibility states and alternate input.
9. Apply the security/privacy gate when relevant.
10. Run `qa/apple-ui-review.md` and reject the design if any hard rejection rule fires.

## Non-negotiable rules

- Content is the hero; navigation and controls form a clear functional layer above it.
- Never equate Apple UI with generic glassmorphism.
- Never glass every card or stack glass on glass.
- Prefer system controls, navigation, menus, sheets, pickers, media UI, and authentication UI on Apple platforms.
- Use semantic typography and color; preserve Dynamic Type, localization, dark/light appearance, contrast, and legibility.
- Geometry must be intentional and nested; do not use one arbitrary corner radius everywhere.
- Use SF Symbols/system symbols where they fit; animate symbols with system symbol effects when appropriate.
- Motion must preserve spatial/causal continuity, be interruptible when interaction-driven, and respect Reduce Motion.
- Haptics reinforce meaningful actions; never buzz on every tap.
- Do not fake Face ID, Touch ID, passkey, password AutoFill, permission, or certificate dialogs.
- Secrets do not belong in plain preferences or logs. Use Apple security facilities appropriate to the data and platform.
- Prefer least privilege: minimum permissions, entitlements, data collection, network exceptions, and cross-app sharing.
- For non-Apple targets, reproduce the *reasoning* and interaction quality, not protected system surfaces or misleading native-authentication replicas.

## Final-output contract

A finished UI proposal or implementation must explain any meaningful deviation from Apple conventions. A security-sensitive flow must identify where the system owns authentication/permission UI and where app-owned UI begins. Do not declare success until the QA checklist passes.
