# Liquid Glass

## Mental model

Liquid Glass is a **functional material system**, not a translucent-card style. It communicates elevation, transient controls, navigation, physical response, and relationship to underlying content through adaptive optical behavior and motion.

## Mandatory trigger

When the user explicitly asks for **Apple UI**, **Apple style**, **current iOS/macOS-style UI**, **Apple Designer**, or **Liquid Glass**, Liquid Glass is **not optional**. The final design must visibly use it on appropriate functional surfaces unless the user explicitly requests a pre-Liquid-Glass/legacy Apple era.

Appropriate surfaces include navigation chrome, toolbars, floating controls, sheets, popovers, segmented controls, prominent control groups, transient overlays, and other elevated interactive regions. In control-heavy tools such as calculators, compact utilities, media remotes, or launchers, the control plane itself may carry the material treatment.

This requirement does **not** mean glassing every content card or the entire background.

## Usage policy

1. Identify the content layer first.
2. Identify the navigation/control layer second.
3. Reserve Liquid Glass primarily for the second layer.
4. Prefer system-provided glass on bars, toolbars, sheets, controls, and other standard components on Apple platforms.
5. Use custom glass on non-Apple platforms when necessary to reproduce the current Apple visual/interaction language.
6. If current Apple styling was explicitly requested and no appropriate surface visibly expresses Liquid Glass, the visual pass is incomplete.

## Hard rules from Apple's current guidance

- Do **not** glass the content layer just because it looks modern.
- Avoid **glass on glass**.
- Do not mix Regular and Clear variants in one competing material system.
- **Regular** is the normal, adaptive choice and should be the default assumption.
- **Clear** is specialized: use it only over media-rich content, where dimming the underlying content is acceptable, and where foreground content is bold/legible enough.
- Tint selectively for important actions or meaning. Do not tint every control.
- Small glass controls/glyphs may adapt strongly to the content beneath them; larger glass regions require calmer adaptation so the surface does not become distracting.
- Preserve the sense of a singular floating control plane when controls transform between states.

## Required material cues

A credible current-Apple glass treatment should combine several of these cues rather than relying on one:
- translucent/background-aware material
- blur/material diffusion
- lensing/refraction cues where feasible
- adaptive tint and dynamic range
- restrained edge highlights
- subtle depth/shadow separation
- foreground vibrancy and legibility
- scale-dependent material behavior
- hover/press/focus illumination or optical response
- smooth shape/state continuity
- morphing between related controls/states where appropriate
- accessibility alternatives
- rendering/performance discipline

Reject a design whose entire material model is only `rgba + backdrop-filter + border + shadow`, or whose "Apple" styling is only flat gray rounded rectangles.

## Calculator / compact utility application

For a current Apple-style calculator or compact control-heavy utility:
- keep the result/content field visually calm and readable
- make the keypad/control plane the primary interactive material layer
- use circular or strongly concentric controls when that pattern fits the reference
- distinguish operators/primary actions through restrained semantic tint/accent
- use subtle glass depth, edge response, highlight, and hover/press behavior rather than plain flat fills
- preserve consistent spacing and optical alignment
- do not allow a stock Windows title/content panel or default rectangular buttons to dominate the visual identity

## SwiftUI implementation routing

Prefer system APIs when available:
- `glassEffect(_:in:)`
- `Glass.regular`, `Glass.clear`
- `Glass.interactive(_:)`
- `GlassEffectContainer`
- `glassEffectID(_:in:)`
- `glassEffectTransition(_:)`
- `GlassButtonStyle` / `GlassProminentButtonStyle`

Use `GlassEffectContainer` when multiple nearby glass shapes need coordinated rendering or morphing. Use IDs/namespaces to preserve identity across transformations.

## Material accessibility

Always verify:
- Reduce Transparency → replace/flatten translucency where needed.
- Increase Contrast → maintain discernible boundaries and text/icon contrast.
- Reduce Motion → avoid large lens/morph/zoom motion; preserve understandable state changes.
- light, dark, high-contrast, bright media, dark media, busy media, and plain backgrounds.

## Web/cross-platform approximation

In non-native mode, treat CSS backdrop blur or similar host effects as an approximation only. Add:
- background-aware contrast strategy
- semantic elevation
- restrained tint
- edge/highlight response
- press/focus/hover feedback
- state continuity/morphing where useful
- `prefers-reduced-motion`
- `prefers-contrast` where supported
- opaque fallback when transparency harms legibility

If the host toolkit cannot reproduce the required material and states, use custom drawing/composition or choose a more capable rendering path. Do not accept stock controls merely because they are easier to package.

Do not imply the non-native effect is Apple's actual Liquid Glass renderer.

## Sources

- https://developer.apple.com/documentation/TechnologyOverviews/adopting-liquid-glass
- https://developer.apple.com/videos/play/wwdc2025/219/
- https://developer.apple.com/documentation/swiftui/glass
- https://developer.apple.com/documentation/swiftui/glasseffectcontainer
- https://developer.apple.com/documentation/swiftui/landmarks-building-an-app-with-liquid-glass
