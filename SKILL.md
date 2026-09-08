---
name: apple-ui-engineering
description: Use when designing, reviewing, or implementing Apple-platform or Apple-inspired interfaces, including SwiftUI, UIKit, AppKit, Liquid Glass, motion, haptics, accessibility, responsive layout, reference matching, and security/privacy-sensitive frontend flows.
---

# Apple UI Engineering

## Core principle

Apple-like UI is not a blur recipe and not a generic rounded desktop theme. Build from **purpose, platform conventions, content hierarchy, native interaction semantics, adaptive layout, current Apple materials, deliberate geometry, meaningful motion, accessibility, and secure system flows**. Visual fidelity is part of correctness when the user explicitly asks for Apple UI.

## Mandatory current-Apple styling trigger

If the user asks for **Apple UI**, **Apple style**, **iOS/macOS-style UI**, **Apple Designer**, **Liquid Glass**, or supplies a current Apple UI reference, assume the **current Apple design language** unless the user explicitly requests a legacy/classic era.

For those requests:

- **Liquid Glass is mandatory on appropriate functional surfaces** such as navigation, toolbars, floating controls, sheets, popovers, segmented controls, prominent control groups, and other elevated interactive chrome. Do not omit it merely because the target platform is Windows/web/Linux.
- Liquid Glass must be expressed as a material/interaction system: translucency, background-aware contrast, restrained tint, depth, edge response, press/hover/focus feedback, and morphing/continuity where appropriate. A flat dark rectangle with rounded corners is not enough.
- Do **not** glass the entire content layer or stack decorative glass on glass. Current Apple styling means visible Liquid Glass where functionally appropriate, not glass everywhere.
- Use **concentric/circular/capsule geometry** where the Apple pattern or supplied reference calls for it. Do not replace circular Apple controls with lightly rounded generic rectangles.
- Typography, spacing, alignment, accent placement, and interaction states must visibly support the Apple target. "Dark mode + rounded buttons" does not satisfy this skill.
- If a supplied reference and generic platform defaults conflict, the **reference/Apple target wins** except for security/trust surfaces and explicit platform constraints.

## Choose the operating mode

1. **APPLE_NATIVE** — SwiftUI, UIKit, AppKit, visionOS. Prefer Apple system components and framework behavior before custom recreation.
2. **APPLE_DESIGN_LANGUAGE** — web, React, Electron, Tauri, Windows, cross-platform. Recreate the current Apple visual/interaction language with custom rendering where needed; do not let host-platform default widgets define the final look.
3. **APPLE_SPATIAL** — visionOS or spatial UI. Add depth, gaze/gesture ergonomics, windows/volumes/spaces, and RealityKit guidance.

## Load the right references

For **every** UI task, read:
- `references/design-system.md`
- `references/visual-fidelity-reference-matching.md`
- `references/layout-typography-color.md`
- `references/components-navigation-input.md`
- `references/accessibility.md`

For every explicit Apple-style/current-Apple request, also read:
- `references/liquid-glass.md`
- `references/motion-animation-haptics.md`

If rendering, media, maps, drawing, web content, symbols, or 3D/spatial content matter, read `references/graphics-media-spatial.md` and `references/frontend-framework-router.md`.
If the feature touches authentication, secrets, permissions, personal data, networking, web views/extensions, entitlements, app integrity, signing, or distribution, read both security references.

## Reference-image rule

When the user supplies a screenshot/mockup/reference image:

1. Inspect it before implementation.
2. Treat it as a primary visual constraint unless the user explicitly says it is loose inspiration.
3. Match macro-layout, control count, proportions, spacing rhythm, geometry, typography hierarchy, accent placement, and dark/light balance before adding your own styling.
4. Then apply the requested current Apple/Liquid Glass treatment to the appropriate functional layer.
5. Compare the finished result against the reference before declaring completion.

Do not silently reinterpret an Apple Calculator reference into a generic Windows calculator, SaaS dashboard, or Material-style app.

## Framework fidelity rule

In `APPLE_DESIGN_LANGUAGE`, **stock host-platform controls are not acceptable as the final visual result when they visibly conflict with the Apple target**.

Examples of unacceptable final output for an explicit Apple-style request:
- default Tkinter buttons/entries
- classic Win32 controls
- default WinForms button grids
- unstyled Qt widgets
- Bootstrap/Material defaults
- giant flat white content panels in a dark Apple reference
- generic rectangular dark buttons with small corner radii pretending to be Apple UI

If the chosen toolkit cannot reproduce the requested geometry, materials, states, and animation quality, use custom drawing/compositing or choose a more capable frontend path.

## Build order

1. State the user task and primary action.
2. Identify platform, input methods, window/screen behavior, accessibility constraints, and whether current Apple styling is explicitly requested.
3. If a reference exists, extract its visual structure first.
4. Establish information hierarchy and navigation semantics.
5. Prefer standard components on Apple platforms; on non-Apple platforms use controls/rendering capable of matching the Apple target.
6. Establish responsive layout, typography, semantic color, accent hierarchy, and Apple-appropriate geometry.
7. Apply Liquid Glass to the functional control/navigation layer when current Apple styling is requested.
8. Add motion/haptics that explain state, continuity, causality, hover/press/focus, or confirmation.
9. Verify accessibility states and alternate input.
10. Apply the security/privacy gate when relevant.
11. Compare against the requested reference/Apple target.
12. Run `qa/apple-ui-review.md` and `qa/rejection-rules.md`; redesign if any relevant hard rejection fires.

## Non-negotiable visual rules

- Content is the hero; navigation and controls form a clear functional layer above it.
- Explicit current Apple-style requests must visibly use Liquid Glass on appropriate functional surfaces.
- Never equate Apple UI with generic glassmorphism.
- Never equate Apple UI with generic dark rounded rectangles.
- Never glass every card or stack glass on glass.
- Preserve reference geometry and composition when the user supplies an Apple reference.
- Prefer circular/concentric/capsule control geometry where the Apple pattern calls for it.
- Use semantic typography and color; preserve Dynamic Type/localization where relevant, dark/light appearance, contrast, and legibility.
- Geometry must be intentional and nested; do not use one arbitrary corner radius everywhere.
- Use SF Symbols/system symbols where they fit on Apple platforms; on non-Apple platforms use appropriately weighted, legally usable equivalents rather than mismatched glyphs.
- Motion must preserve spatial/causal continuity, be interruptible when interaction-driven, and respect Reduce Motion.
- Pointer-driven Apple-inspired interfaces need deliberate hover, press, focus, selected, and disabled states.
- Haptics reinforce meaningful actions; never buzz on every tap.

## Non-negotiable security rules

- Do not fake Face ID, Touch ID, passkey, password AutoFill, permission, certificate, or other trusted system dialogs.
- Secrets do not belong in plain preferences or logs. Use security facilities appropriate to the data and platform.
- Prefer least privilege: minimum permissions, entitlements, data collection, network exceptions, and cross-app sharing.
- For non-Apple targets, reproduce Apple visual reasoning and interaction quality without misleading people into believing custom trust UI is system-owned.

## Final-output contract

A finished Apple-style UI must pass both **semantic correctness** and **visual-fidelity correctness**. If the result still reads as generic Windows/Tkinter/WinForms/Material/SaaS before it reads as the requested Apple design, it is not finished.

A security-sensitive flow must identify where the system owns authentication/permission UI and where app-owned UI begins. Do not declare success until the QA checklist passes and, when a reference was provided, the result has been compared against that reference.
