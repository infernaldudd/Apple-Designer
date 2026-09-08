# Apple UI Review

Score each relevant category 0–2:
- **0** = fails / contradicts the requested Apple target
- **1** = workable but incomplete, generic, or custom without sufficient fidelity
- **2** = strong, adaptive, visually convincing, and platform-coherent

## Scorecard

| Category | Score | Review question |
|---|---:|---|
| Purpose |  | Is the primary task immediately clear? |
| Reference fidelity |  | If a reference was supplied, does the result match its macro-layout, proportions, control geometry, spacing rhythm, typography hierarchy, and accent placement? |
| Apple visual identity |  | Does the result visibly read as the requested current Apple design before it reads as generic Windows/Tkinter/Material/SaaS UI? |
| Hierarchy |  | Does content dominate controls/decorations appropriately? |
| Navigation semantics |  | Are tabs/stacks/sidebars/toolbars/sheets used for the correct jobs? |
| Native/component fidelity |  | On Apple platforms, did we prefer system components? On non-Apple platforms, did we avoid visibly wrong stock controls and custom-render where needed? |
| Layout |  | Does it adapt across sizes/safe areas/windows? |
| Geometry |  | Are circles/capsules/radii nested and role-based rather than arbitrary? Does the geometry match the Apple pattern/reference? |
| Typography |  | Is type hierarchy readable, aligned, semantically appropriate, and scaling-safe where relevant? |
| Color |  | Are colors semantic, restrained, adaptive, and non-color-dependent for meaning? |
| Liquid Glass / material |  | For current Apple-style requests, is Liquid Glass visibly present on appropriate functional surfaces and expressed through depth, background response, edge/highlight behavior, and interaction rather than flat rounded fills? |
| Motion |  | Does animation communicate state/space/causality and remain interruptible where needed? |
| Interaction states |  | Are hover, press, focus, selected, disabled, and pointer/keyboard states deliberate where the platform expects them? |
| Haptics |  | Are haptics meaningful and restrained? |
| Symbols |  | Are symbols familiar, optically consistent, and animated only when useful? |
| Accessibility |  | Does the UI survive VoiceOver, large text, contrast, reduced motion/transparency, and alternate input? |
| Platform fit |  | Does iPhone/iPad/Mac/TV/Watch/Vision/desktop behavior fit the actual host while preserving the requested Apple design language? |
| Security UI |  | Are trust-sensitive prompts owned by the system and clearly explained? |
| Secrets/data |  | Are secrets, local files, networking, and sharing protected appropriately? |
| Privacy |  | Is data/permission scope minimal and transparent? |
| AI-slop risk |  | Does the UI look purpose-built rather than generated from fashionable/default components? |

## Mandatory visual gate for explicit Apple-style requests

Before scoring, answer all applicable questions:

- Is current Apple styling explicitly requested?
- If yes, is there an appropriate functional layer using visible Liquid Glass/material behavior?
- If a reference exists, was the finished UI compared against it?
- Are stock Tkinter/WinForms/Win32/unstyled Qt/Bootstrap/Material controls absent from the final visual result unless they genuinely match the target?
- Does the control geometry match the reference/pattern rather than defaulting to generic rounded rectangles?
- Are typography, spacing, accent placement, dark/light balance, and interaction states visibly intentional?

Any **No** where the answer should be Yes fires a hard rejection and requires redesign before completion.

## Pass rule

- No hard rejection rule may fire.
- No applicable category may score 0.
- Purpose, reference fidelity (when applicable), Apple visual identity, accessibility, and security-sensitive categories (when relevant) must score 2.
- For an explicit current Apple-style request, `Liquid Glass / material` must score 2.
- For Apple-native shipping UI, target at least 90% of the maximum applicable score.
- For Apple-inspired non-native UI with a supplied reference, target at least 90% and require a visual comparison pass.

If the design fails, revise the weakest category first; do not hide the problem with more polish.
