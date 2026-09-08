# Liquid Glass

## Mental model

Liquid Glass is a **functional material system**, not a translucent-card style. It communicates elevation, transient controls, navigation, physical response, and relationship to underlying content through adaptive optical behavior and motion.

## Usage policy

1. Identify the content layer first.
2. Identify the navigation/control layer second.
3. Reserve Liquid Glass primarily for the second layer.
4. Prefer system-provided glass on bars, toolbars, sheets, controls, and other standard components.
5. Use custom glass only when a custom functional element genuinely needs it.

## Hard rules from Apple's current guidance

- Do **not** glass the content layer just because it looks modern.
- Avoid **glass on glass**.
- Do not mix Regular and Clear variants in one competing material system.
- **Regular** is the normal, adaptive choice and should be the default assumption.
- **Clear** is specialized: use it only over media-rich content, where dimming the underlying content is acceptable, and where foreground content is bold/legible enough.
- Tint selectively for important actions or meaning. Do not tint every control.
- Small glass controls/glyphs may adapt strongly to the content beneath them; larger glass regions require calmer adaptation so the surface does not become distracting.
- Preserve the sense of a singular floating control plane when controls transform between states.

## Behavior, not CSS imitation

A credible glass system considers:
- background interaction
- blur/material diffusion
- lensing/refraction cues
- adaptive tint and dynamic range
- edge highlights and shadow/elevation
- foreground vibrancy and legibility
- scale-dependent material behavior
- press/hover/focus response
- morphing between related shapes/states
- accessibility alternatives
- rendering/performance cost

Reject a design whose entire material model is only `rgba + backdrop-filter + border + shadow`.

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

In non-native mode, treat CSS backdrop blur as an approximation only. Add:
- background-aware contrast strategy
- semantic elevation
- restrained tint
- press/focus feedback
- adaptive borders/highlights
- `prefers-reduced-motion`
- `prefers-contrast` where supported
- opaque fallback when transparency harms legibility

Do not imply the web effect is Apple's actual Liquid Glass renderer.

## Sources

- https://developer.apple.com/documentation/TechnologyOverviews/adopting-liquid-glass
- https://developer.apple.com/videos/play/wwdc2025/219/
- https://developer.apple.com/documentation/swiftui/glass
- https://developer.apple.com/documentation/swiftui/glasseffectcontainer
- https://developer.apple.com/documentation/swiftui/landmarks-building-an-app-with-liquid-glass
