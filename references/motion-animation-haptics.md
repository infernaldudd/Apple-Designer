# Motion, Animation, and Haptics

## Motion hierarchy

Use motion for one of these jobs:
1. **State change** — show what changed.
2. **Spatial continuity** — preserve where something came from/went.
3. **Causality** — connect input to result.
4. **Hierarchy** — communicate elevation/presentation/dismissal.
5. **Progress/status** — show ongoing work or changing value.
6. **Confirmation** — brief visual/haptic acknowledgement.

If an animation does none of these, remove it.

## Timing and physics

- Avoid one universal easing curve.
- Linear motion often feels mechanical; use it mainly when constant-rate motion is semantically correct.
- Use springs for physical settling/interactive movement, not as a branding gimmick.
- Tune damping/stiffness/response to component mass and travel distance.
- Small state changes should generally finish sooner than large spatial transitions.
- Related properties should coordinate as one transition.
- Avoid gratuitous overshoot and bounce.

## Interactivity

- Interactive animations should respond immediately, track input, and remain interruptible/reversible when the gesture can reverse.
- Preserve the apparent identity of controls during morphs.
- Menus/popovers should appear causally connected to the control that opened them.
- Prefer system transitions where they already encode platform behavior.

## SwiftUI

Use the simplest adequate level:
- state-driven `Animation` / `withAnimation`
- transitions/content transitions
- matched geometry where identity continuity is needed
- phase animators for discrete staged sequences
- keyframe animators for coordinated per-frame values/timing
- symbol effects for SF Symbols
- Liquid Glass transitions/IDs for glass morphing

Do not use keyframes when a normal state transition communicates the same thing more clearly.

## UIKit / Core Animation

- `UIViewPropertyAnimator`: interactive, pausable, interruptible view animations.
- `UISpringTimingParameters`: spring timing for view animations.
- `CALayer`: visual geometry/content layer model.
- `CABasicAnimation`: basic property animation.
- `CAKeyframeAnimation`: keyframed property paths/timing.
- `CASpringAnimation`: physically based spring with damping/stiffness.
- `CAAnimationGroup`: coordinate animations.
- `CATransaction`: group layer-tree changes atomically and control implicit animation behavior.
- `CAMediaTimingFunction`: pacing curves.

Prefer view-level APIs unless layer-level control is actually required.

## Haptics

Use system-provided feedback when standard controls already provide it. Use Core Haptics for custom patterns only when tactile feedback improves understanding or feel.

Good uses:
- meaningful toggle/selection/threshold
- successful completion or warning where platform guidance supports it
- tactile correspondence with a continuous control or physical simulation

Bad uses:
- every tap
- decorative vibration during passive animation
- long or intense patterns that compete with content

Check hardware capability and degrade gracefully.

## Accessibility

When Reduce Motion is enabled:
- avoid large zooms, 3D sweeps, parallax, intense lensing, and unnecessary travel
- prefer opacity, subtle crossfade, direct state replacement, or shorter transforms
- never remove essential state feedback

Also respect settings related to animated images/flashing content when relevant.

## Sources

- https://developer.apple.com/design/human-interface-guidelines/motion
- https://developer.apple.com/documentation/swiftui/animation
- https://developer.apple.com/documentation/SwiftUI/Controlling-the-timing-and-movements-of-your-animations
- https://developer.apple.com/documentation/quartzcore
- https://developer.apple.com/documentation/quartzcore/calayer
- https://developer.apple.com/documentation/quartzcore/caspringanimation
- https://developer.apple.com/documentation/quartzcore/catransaction
- https://developer.apple.com/documentation/corehaptics
- https://developer.apple.com/documentation/symbols
