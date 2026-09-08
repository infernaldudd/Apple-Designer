# Accessibility

Accessibility is a design input, not a final audit.

## Required states

Test at minimum:
- VoiceOver / screen reader semantics
- Dynamic Type / large text
- Bold Text where applicable
- Increase Contrast
- Reduce Transparency
- Reduce Motion
- Differentiate Without Color
- light and dark appearance
- keyboard/focus navigation where applicable
- pointer/hover where applicable
- sufficient hit target and spacing
- localization expansion

## Semantic structure

- Every actionable element needs a meaningful accessible name/label.
- Group related content logically; do not expose decorative layers as separate noise.
- Keep focus order aligned with visual/task order.
- Convey state (`selected`, `expanded`, `disabled`, progress, value) semantically, not only visually.
- Do not encode critical meaning only in color, animation, or haptics.

## Dynamic Type

- Use semantic text styles on Apple platforms.
- Let controls grow/reflow rather than clipping.
- Avoid fixed-height text containers that break at accessibility sizes.
- Check long strings and localization.

## Motion and transparency

SwiftUI provides environment values such as `accessibilityReduceMotion` and `accessibilityReduceTransparency`.
- Reduce Motion: avoid large spatial/3D motion and unnecessary animation.
- Reduce Transparency: use sufficiently opaque backgrounds instead of relying on translucent material.
- Increase Contrast: reinforce edges, text/icon contrast, and state distinction.

## Spatial accessibility

For visionOS/spatial interfaces:
- avoid requiring precise gaze or tiny targets
- avoid excessive head/eye movement
- keep depth/scale understandable
- provide alternatives to motion-heavy or immersion-heavy interactions

## Sources

- https://developer.apple.com/design/human-interface-guidelines/accessibility
- https://developer.apple.com/documentation/swiftui/environmentvalues/accessibilityReduceMotion
- https://developer.apple.com/documentation/swiftui/environmentvalues/accessibilityReduceTransparency
- https://developer.apple.com/documentation/uikit/accessibility-for-uikit
