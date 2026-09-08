# Graphics, Media, Web, Maps, Drawing, and Spatial UI

## Graphics stack

### Core Graphics
Use for lightweight high-fidelity 2D rendering: paths, transformations, gradients, images, masks, offscreen contexts, color management, and PDFs.

### Core Image
Use for image filtering/effects pipelines. Reuse expensive rendering contexts; let Core Image optimize chained operations rather than prematurely rendering each intermediate stage.

### Metal
Use when custom GPU rendering, advanced shaders, high-throughput compute, HDR presentation, or lower-level performance control is genuinely required. Do not jump to Metal for ordinary interface polish that SwiftUI/UIKit/Core Animation can handle.

## Media

Use AVKit when you want standard Apple playback UI, transport controls, chapters, subtitles/captions, and Picture in Picture. Standard playback UI generally beats a decorative custom player unless the product has specialized requirements.

## Symbols

SF Symbols/Symbols framework can communicate status and state with system-coherent animations. Choose effect behavior based on meaning:
- discrete for a one-time response
- indefinite for ongoing state
- transition for appearance/disappearance
- content transition for symbol-to-symbol/configuration continuity

## Maps

Use MapKit/MapKit for SwiftUI for map-centric UI, map styles, annotations, overlays, map controls, directions, points of interest, and Look Around. Preserve familiar map gestures and avoid covering the map with excessive custom chrome.

## Drawing

Use PencilKit for low-latency Pencil/finger drawing and built-in drawing tools. Keep app chrome secondary to the canvas while drawing.

## Web content

Use WKWebView/WebKit for SwiftUI. Keep browser navigation policy explicit, especially for authentication, downloads, external navigation, custom schemes, and untrusted content. Prefer native UI around the web view rather than recreating an entire browser chrome unnecessarily.

## Spatial UI / visionOS

Start from windows. Add volumes when 3D content benefits from being viewable from multiple angles. Use immersive spaces only when immersion itself serves the task.

Spatial rules:
- add depth to clarify, not decorate
- avoid tiny controls and excessive gaze precision
- use hover/gaze response for affordance, not constant visual noise
- ornaments can host frequent tools outside the main content plane
- preserve real-world grounding unless full immersion is purposeful
- RealityKit handles 3D entities, materials, animations, audio, and scene content; SwiftUI remains useful for app structure and 2D controls

## Sources

- https://developer.apple.com/documentation/coregraphics
- https://developer.apple.com/documentation/coreimage
- https://developer.apple.com/documentation/Metal
- https://developer.apple.com/documentation/symbols
- https://developer.apple.com/documentation/AVKit
- https://developer.apple.com/documentation/mapkit/mapkit-for-swiftui
- https://developer.apple.com/documentation/pencilkit
- https://developer.apple.com/documentation/webkit
- https://developer.apple.com/documentation/realitykit
- https://developer.apple.com/visionos/get-started/
