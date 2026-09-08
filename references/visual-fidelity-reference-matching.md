# Apple Visual Fidelity and Reference Matching

This module exists to prevent a common failure mode: an interface can be semantically clean yet still look like generic Windows, Tkinter, WinForms, Bootstrap, Material, or SaaS UI. In Apple design mode, visual identity is a first-class requirement.

## Default target

When the user explicitly asks for **Apple UI**, **Apple style**, **iOS/macOS-style UI**, **Apple Designer**, **Liquid Glass**, or provides an Apple UI reference, default to the **current Apple visual language** unless they explicitly request a legacy/classic era.

Current-Apple mode means:
- content-first composition
- restrained chrome
- current Liquid Glass/material behavior on appropriate functional surfaces
- deliberate concentric geometry
- strong typography and alignment
- system-like spacing rhythm
- responsive hover/press/focus states
- smooth state continuity and morphing where appropriate
- platform-aware accessibility and contrast

Do not interpret "Apple style" as merely "dark mode + rounded rectangles".

## Reference-first rule

If the user supplies a screenshot/mockup/reference, inspect it before designing. Treat it as a primary visual constraint unless the user says it is only loose inspiration.

Match in this order:
1. overall silhouette and aspect ratio
2. major regions and content hierarchy
3. control count and placement
4. relative control sizes
5. shape language: circles, capsules, rounded rectangles, nested corners
6. spacing rhythm and edge insets
7. typography scale, weight, alignment, and number formatting
8. accent placement and visual emphasis
9. material, blur, translucency, tint, shadow, lensing, and highlights
10. motion and interaction behavior

Do not replace a supplied Apple reference with a generic "modern" layout.

## Cross-platform rendering rule

In **APPLE_DESIGN_LANGUAGE** mode, host-platform defaults are not the target. If stock controls visibly look like Tkinter, Win32, WinForms, unstyled Qt, Bootstrap, or another unrelated design system, do not ship them as the final UI.

Choose a rendering path that can achieve the target fidelity:
- native custom drawing / compositing
- SwiftUI/UIKit/AppKit on Apple platforms
- WinUI 3/custom composition on Windows where appropriate
- styled Qt/PySide with custom delegates/effects
- web/Electron/Tauri with custom CSS/canvas/WebGL where appropriate
- another toolkit capable of custom control geometry, material, animation, and state rendering

Framework convenience is secondary to visual fidelity when the user explicitly asks for Apple-quality UI.

## Mandatory visual pass

Before completion, compare the result against the requested Apple target/reference and reject if any of these are obvious:
- default OS widgets remain visible
- square or lightly-rounded generic buttons replace circular/capsule Apple controls
- a large white/flat content panel breaks the requested dark composition
- spacing is mechanically uniform rather than visually balanced
- typography looks like an unstyled desktop form
- operators, primary actions, or selected states lack clear emphasis
- title bar/chrome dominates the product surface
- material is flat when current Apple/Liquid Glass was requested
- no hover/press/focus response exists in a pointer-driven app
- the result reads as "generic desktop calculator/dashboard" before it reads as Apple-inspired

## Calculator-specific pattern

For an Apple-style calculator or keypad-like tool, unless the reference says otherwise:
- use a clean dark or reference-matched content canvas
- place the expression/result area prominently near the top, usually right-aligned
- make numeric controls strongly circular or concentrically rounded
- distinguish operators/primary actions with restrained semantic accent
- preserve consistent row/column rhythm
- allow zero or similar special controls to span/capsule only when the reference/pattern calls for it
- apply Liquid Glass/material response to the functional control layer in current-Apple mode
- use subtle hover/press illumination, scale, lensing, or material response rather than abrupt flat color swaps
- never fall back to stock rectangular desktop buttons merely because the executable target is Windows

## Fidelity vs. native authenticity

For non-Apple platforms, reproduce the visual reasoning and interaction quality without falsely presenting custom UI as an actual Apple system security or permission surface. Visual fidelity does not override trust-boundary rules.
