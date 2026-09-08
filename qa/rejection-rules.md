# Hard Rejection Rules

Reject and redesign if any relevant rule fires.

## Apple visual-fidelity rejection
- The user explicitly requested current Apple/Apple Designer/Liquid Glass styling, but no appropriate functional surface visibly uses Liquid Glass/material response.
- The result reads primarily as generic Windows, Tkinter, WinForms, Material, Bootstrap, SaaS, or unstyled Qt UI instead of the requested Apple visual language.
- Stock host-platform controls remain visually dominant when a custom Apple-style presentation was requested.
- A supplied Apple reference is ignored in macro-layout, control count, proportions, geometry, spacing, typography hierarchy, or accent placement without a stated reason.
- Circular/capsule Apple controls in the reference are replaced by generic lightly-rounded rectangles.
- A large flat white/default content panel breaks a dark/reference-matched Apple composition.
- "Apple style" is reduced to dark mode + rounded rectangles + one accent color.
- The chosen frontend toolkit visibly cannot reproduce the requested material, geometry, states, or animation quality, yet the implementation ships without custom rendering or a better rendering path.

## Visual / hierarchy rejection
- Glass is used as the default surface for most cards/content.
- Glass is stacked on glass without a clear functional reason.
- Clear and Regular Liquid Glass variants are mixed as competing materials.
- Giant blurry floating panels dominate ordinary content.
- Random neon/purple-blue gradients substitute for hierarchy.
- Every action is tinted or equally prominent.
- Every container uses the same large corner radius.
- Excessive pills/capsules erase component semantics.
- Decorative borders/glows/shadows are doing the job that layout/hierarchy should do.
- Tiny low-contrast text is used to look "premium."
- The screen resembles a generic SaaS/AI dashboard despite a different task.

## Liquid Glass rejection
- The entire effect is only opacity/blur/border/shadow with no background-aware contrast, optical response, interaction state, or semantic elevation.
- Liquid Glass is treated as static decoration rather than functional interactive chrome.
- A current Apple-style request uses only flat gray/black button fills with no meaningful material response.
- Glass is applied indiscriminately to content instead of appropriate controls/navigation.
- Hover/press/focus states do not change the material or perceived physical response in a pointer-driven interface.

## Interaction rejection
- Essential actions are hover-only.
- Custom controls omit pressed/focus/disabled/selected states.
- Animation is added to every hover/tap without semantic purpose.
- The interface uses gratuitous bounce/overshoot.
- Navigation components are chosen for shape instead of navigation semantics.
- Multiple navigation systems compete for the same destinations.
- A pointer-driven Apple-inspired desktop UI has no deliberate hover/press/focus feedback.

## Accessibility rejection
- Large text clips or overlaps.
- Focus order does not match task order.
- Critical meaning depends on color only.
- Reduce Motion still produces major spatial/3D motion.
- Reduce Transparency leaves unreadable translucent backgrounds.
- Keyboard/pointer/focus behavior is missing where the platform expects it.

## Security/privacy rejection
- Fake Face ID/Touch ID/passkey/password/permission/certificate system UI.
- Plaintext secrets in UserDefaults/preferences/localStorage/logs.
- Broad ATS/arbitrary-load exception without a documented necessity.
- App asks for sensitive permissions at launch without context when they are not immediately needed.
- App collects data unrelated to the feature's purpose.
- App grants broad entitlements/extension host permissions for convenience.
- Sensitive server access trusts a client-side boolean/self-check as proof of app integrity.
- Custom cryptography is invented instead of using vetted platform primitives.
