# Hard Rejection Rules

Reject and redesign if any relevant rule fires.

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

## Interaction rejection
- Essential actions are hover-only.
- Custom controls omit pressed/focus/disabled/selected states.
- Animation is added to every hover/tap without semantic purpose.
- The interface uses gratuitous bounce/overshoot.
- Navigation components are chosen for shape instead of navigation semantics.
- Multiple navigation systems compete for the same destinations.

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
