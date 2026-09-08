# Apple Design System

## Source priority

When sources conflict, use this order:
1. Current Apple Human Interface Guidelines and current platform-specific guidance.
2. Current Apple technology overviews (including Liquid Glass adoption guidance).
3. Current framework documentation (SwiftUI/UIKit/AppKit/etc.).
4. Current WWDC design and implementation sessions.
5. This skill's translation rules.

## Design principles

Use Apple's current high-level design principles as a decision filter:
- **Purpose:** every screen and control serves a real user goal.
- **Agency:** people understand and control what happens.
- **Responsibility:** protect attention, privacy, safety, and data.
- **Familiarity:** reuse learned platform conventions when possible.
- **Flexibility:** adapt across devices, sizes, input methods, and user settings.
- **Simplicity:** remove unnecessary complexity; simplicity is not emptiness.
- **Craft:** refine alignment, behavior, type, motion, materials, loading, and edge cases.
- **Delight:** earn delight through responsiveness and thoughtful details, not decoration.

## Hierarchy

Work from these layers:
1. **Content** — the information or object the person came for.
2. **Navigation** — movement between major locations and hierarchy levels.
3. **Actions/controls** — commands that affect content or state.
4. **Status/feedback** — progress, selection, validation, confirmation, warnings.
5. **Decoration** — only after the above are clear.

Reject a design where decoration competes with content or where visual similarity hides different semantics.

## Native-first rule

On Apple platforms, standard components inherit platform changes, accessibility behavior, input behavior, materials, and visual updates. Prefer them unless a product requirement truly cannot be met. Custom controls must recreate all required states: default, pressed, focused, hovered/pointer, selected, disabled, loading where relevant, keyboard focus, accessibility, contrast, motion reduction, and localization.

## Familiar patterns

- Tab bars: top-level destinations.
- Navigation stacks/split views: hierarchical navigation.
- Toolbars: context-relevant actions and navigation-level commands.
- Sidebars: larger information hierarchies, especially iPad/macOS.
- Sheets/popovers/menus: transient tasks and contextual choices.
- Search: use platform search placements and behavior where possible.
- Context menus: secondary/contextual actions, not primary discovery.

## Apple-inspired non-native mode

For React/web/Electron/Tauri/Windows:
- Keep semantic hierarchy, spacing discipline, adaptive layout, restrained material, meaningful motion, system-like hit targets, and accessibility.
- Use the host platform's real system dialogs for security-sensitive actions where possible.
- Never label a custom web dialog as a real Apple system sheet.
- Avoid pixel-for-pixel copying of private/system-only screens when that could mislead users about trust or authorization.

## Sources

- https://developer.apple.com/design/human-interface-guidelines/
- https://developer.apple.com/design/human-interface-guidelines/design-principles
- https://developer.apple.com/design/human-interface-guidelines/technologies
- https://developer.apple.com/documentation/swiftui
- https://developer.apple.com/documentation/uikit
- https://developer.apple.com/documentation/appkit
