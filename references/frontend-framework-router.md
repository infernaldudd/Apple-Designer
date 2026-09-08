# Frontend Framework Router

Use this file to decide which Apple framework documentation matters before implementing.

| Need | Prefer / inspect |
|---|---|
| Cross-platform declarative Apple UI | SwiftUI |
| iOS/iPadOS/tvOS/visionOS view-controller UI or deep platform control | UIKit |
| macOS-native windows, menus, toolbars, views | AppKit |
| Layer compositing and low-level 2D animation | QuartzCore / Core Animation |
| 2D vector/path/gradient/image rendering | Core Graphics |
| Image filtering/effects/render pipelines | Core Image |
| GPU rendering/custom shaders/high-performance graphics | Metal / MetalKit |
| SF Symbol animation | Symbols |
| Custom tactile/audio haptic patterns | Core Haptics |
| Embedded web content | WebKit / WebKit for SwiftUI |
| Contextual feature education | TipKit |
| Maps/annotations/overlays/Look Around | MapKit |
| Apple Pencil/finger drawing | PencilKit |
| Photo/video library picker UI | PhotosUI / PhotosPicker |
| Standard media playback UI | AVKit |
| Complex text layout/rendering/editing | TextKit |
| 3D/spatial content | RealityKit + SwiftUI / visionOS |
| High-level 3D/immersive rendering | RealityKit; Metal when lower-level control is required |

## SwiftUI routing

Before hand-building UI, inspect SwiftUI categories for:
- views and controls
- layout containers and custom layout
- navigation and presentation
- lists/tables/forms
- text/images/symbols/shapes
- gestures/focus/drag-and-drop
- animation/transitions/keyframes/phases
- drawing/graphics/visual effects
- accessibility environment
- scene/window management
- Liquid Glass

## UIKit routing

Inspect:
- views and controls
- view layout / Auto Layout / safe areas
- appearance and Liquid Glass
- animation and haptics
- navigation/presentation/window/scene controllers
- gestures, drag/drop, pointer, focus, keyboard, Pencil
- accessibility
- text, images, drawing, printing

## AppKit routing

Inspect:
- windows/panels/screens
- views and controls
- view management/layout/Auto Layout
- menus/toolbars/sidebars
- animation
- appearance/vibrancy/material
- document/text systems
- keyboard/mouse/drag-drop/accessibility

## Web mode

If implementing Apple-inspired UI in web tech:
- use semantic HTML first
- map Apple semantic hierarchy to accessible web controls
- preserve focus-visible and keyboard behavior
- use CSS media queries for color scheme, reduced motion, and contrast support
- treat CSS blur as an approximation of material, not a literal Liquid Glass implementation
- prefer WebAuthn/passkeys and browser/system permission surfaces for trust-sensitive flows rather than fake native dialogs

## Sources

- https://developer.apple.com/documentation/swiftui
- https://developer.apple.com/documentation/uikit
- https://developer.apple.com/documentation/appkit
- https://developer.apple.com/documentation/quartzcore
- https://developer.apple.com/documentation/coregraphics
- https://developer.apple.com/documentation/coreimage
- https://developer.apple.com/documentation/Metal
- https://developer.apple.com/documentation/webkit
- https://developer.apple.com/documentation/TipKit
- https://developer.apple.com/documentation/mapkit
- https://developer.apple.com/documentation/pencilkit
- https://developer.apple.com/documentation/AVKit
- https://developer.apple.com/documentation/appkit/textkit
- https://developer.apple.com/documentation/realitykit
