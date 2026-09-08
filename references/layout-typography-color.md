# Layout, Typography, Color, and Iconography

## Layout

Design from **safe region → container → content margins → content → controls**.

### Rules
- Prefer adaptive layout over fixed pixel coordinates.
- On UIKit, use safe areas, layout margins, stack views, Auto Layout, and trait-aware layout.
- On SwiftUI, use native layout containers, grids, adaptive layouts, safe-area APIs, and environment values rather than hardcoding device models.
- Windows must survive continuous resizing on iPadOS/macOS, not only a few desktop breakpoints.
- Preserve hierarchy as width changes: collapse/reflow/navigation transformation should be intentional.
- Keep touch targets comfortably usable; use Apple's platform guidance as the minimum, not a visual afterthought.
- Respect keyboard, pointer, focus, Apple Pencil, remote/game-controller focus, and spatial input where relevant.

## Geometry

- Use nested/concentric geometry when controls sit inside rounded windows/containers.
- Radius follows component role and scale; do not apply a universal 24/32px radius.
- Avoid excessive pills. Capsules are for controls whose semantics/size warrant them, not every card.
- Dividers and borders are structural tools, not default decoration.

## Typography

- Prefer system fonts and semantic text styles on Apple platforms.
- Use semantic roles: large title/title/headline/body/callout/subheadline/footnote/caption equivalents.
- Preserve hierarchy under Dynamic Type.
- Avoid overly light weights, tiny low-contrast secondary copy, and gratuitous uppercase.
- Layout must survive long localization, bold text, and larger accessibility sizes.
- Numeric/status text can use content transitions designed for numbers where appropriate.

## Color

- Prefer semantic/system colors that adapt to appearance and contrast.
- Use color to establish meaning and emphasis, not to decorate every control.
- Primary action emphasis must remain obvious if saturation or transparency changes.
- Never rely on color alone for critical status.
- Test light/dark/high-contrast and tinted/material contexts.

## Symbols and icons

- Prefer SF Symbols for standard concepts on Apple platforms.
- Match weight/scale to neighboring text and controls.
- Use symbol rendering modes intentionally: monochrome, hierarchical, palette, multicolor, variable rendering.
- Use symbol effects (appear, bounce, pulse, scale, variable color, replace, breathe, rotate, wiggle, draw) only when they communicate state, progress, transition, or feedback.
- Custom symbols should preserve optical weight and alignment across sizes/weights.

## Sources

- https://developer.apple.com/design/human-interface-guidelines/typography
- https://developer.apple.com/design/human-interface-guidelines/color
- https://developer.apple.com/sf-symbols/
- https://developer.apple.com/documentation/symbols
- https://developer.apple.com/documentation/swiftui
- https://developer.apple.com/documentation/uikit
- https://developer.apple.com/documentation/appkit
