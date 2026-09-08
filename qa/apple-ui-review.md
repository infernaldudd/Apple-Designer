# Apple UI Review

Score each relevant category 0–2:
- **0** = fails / contradicts Apple-platform expectations
- **1** = workable but incomplete or custom without sufficient reason
- **2** = strong, adaptive, platform-coherent

## Scorecard

| Category | Score | Review question |
|---|---:|---|
| Purpose |  | Is the primary task immediately clear? |
| Hierarchy |  | Does content dominate controls/decorations appropriately? |
| Navigation semantics |  | Are tabs/stacks/sidebars/toolbars/sheets used for the correct jobs? |
| Native-component use |  | Did we avoid needless custom recreation? |
| Layout |  | Does it adapt across sizes/safe areas/windows? |
| Geometry |  | Are radii/shapes nested and role-based rather than arbitrary? |
| Typography |  | Is semantic type readable and Dynamic-Type-safe? |
| Color |  | Are colors semantic, restrained, adaptive, and non-color-dependent for meaning? |
| Material |  | Is glass/material functional, restrained, and legible? |
| Motion |  | Does animation communicate state/space/causality and remain interruptible where needed? |
| Haptics |  | Are haptics meaningful and restrained? |
| Symbols |  | Are symbols familiar, optically consistent, and animated only when useful? |
| Accessibility |  | Does the UI survive VoiceOver, large text, contrast, reduced motion/transparency, alternate input? |
| Platform fit |  | Does iPhone/iPad/Mac/TV/Watch/Vision behavior fit the actual platform? |
| Security UI |  | Are trust-sensitive prompts owned by the system and clearly explained? |
| Secrets/data |  | Are secrets, local files, networking, and sharing protected appropriately? |
| Privacy |  | Is data/permission scope minimal and transparent? |
| AI-slop risk |  | Does the UI look purpose-built rather than generated from fashionable defaults? |

## Pass rule

- No hard rejection rule may fire.
- No applicable category may score 0.
- Purpose, hierarchy, accessibility, and security-sensitive categories (when relevant) must score 2.
- For Apple-native shipping UI, target at least 90% of the maximum applicable score.

If the design fails, revise the weakest category first; do not hide the problem with more polish.
