# Components, Navigation, Input, and Feedback

## Choose semantics before appearance

Ask what the element **does**, then choose a platform component. Never choose a tab bar, sidebar, toolbar, menu, sheet, or popover only because its shape looks right.

## Navigation

- **Tab bar:** a small set of peer top-level destinations.
- **Navigation stack:** drill-down hierarchy with reversible movement.
- **Split view/sidebar:** broader persistent hierarchy on larger displays.
- **Toolbar:** commands related to current content or navigation level.
- **Search:** use system placements/behaviors where possible.
- **Menu/context menu:** secondary or contextual commands.
- **Sheet:** focused transient task/content.
- **Popover:** context-attached transient choices/details where platform/space supports it.

Avoid duplicated navigation (for example, custom pills plus a real tab bar for the same destinations).

## Controls

Prefer platform buttons, toggles, sliders, pickers, text fields, date controls, lists, forms, tables, collection views, menus, and standard playback controls. Custom components must include full interaction and accessibility states.

## Input

Support relevant modalities:
- touch and gestures
- keyboard shortcuts and focus
- pointer/hover
- drag and drop
- Apple Pencil/Scribble where useful
- remote/game controller focus on tvOS
- gaze/gesture and spatial placement on visionOS

Do not hide essential actions behind hover-only behavior.

## Tips and onboarding

Use contextual education sparingly. Prefer TipKit/system-like contextual tips for nonobvious or newly introduced features. Do not show tips on every launch or use them to explain a fundamentally unclear interface.

## Media and pickers

Prefer system surfaces for sensitive or complex content selection:
- PhotosPicker/PhotosUI for photo selection.
- AVKit for standard media playback controls/Picture in Picture.
- AuthenticationServices/LocalAuthentication for identity.
- system share sheet for sharing.

## Maps and drawing

Use MapKit for platform-consistent maps, annotations, overlays, directions, controls, and Look Around integration. Use PencilKit for low-latency Apple Pencil/finger drawing rather than reimplementing the entire drawing stack.

## Web content

Use WebKit (`WKWebView` or WebKit for SwiftUI) for embedded web content. Keep navigation policy explicit and expose native UI for native actions. Avoid old/deprecated web views.

## Sources

- https://developer.apple.com/documentation/uikit/views-and-controls
- https://developer.apple.com/documentation/uikit/drag-and-drop
- https://developer.apple.com/documentation/tipkit
- https://developer.apple.com/documentation/photosui/photospicker
- https://developer.apple.com/documentation/avkit
- https://developer.apple.com/documentation/mapkit/mapkit-for-swiftui
- https://developer.apple.com/documentation/pencilkit
- https://developer.apple.com/documentation/webkit
