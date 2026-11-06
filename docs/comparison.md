# Comparison and synthesis

Reviewed 2026-11-05. The installed 1.0.0 skill was already an adaptation of the GitHub skill listed in Skills Directory. The useful outcome is a stronger replacement, not another parallel installation.

| Source | Strengths | Decision in 2.0.0 |
| --- | --- | --- |
| Existing installed skill, 1.0.0 | Cross-platform translation, preserved product identity, meaningful card exceptions, CSS fallback, hybrid-shell constraints, flexible outputs | Retain as the foundation |
| [GitHub Golden Gate](https://github.com/github/awesome-copilot/tree/96543145e9cb97711020b57b9d88f968062c4fc7/skills/macos-golden-gate-design) | Specific pane and component patterns, clear material allocation, exact-source inspection, broad state checks | Add component decisions and evidence guidance; keep native-only details conditional |
| [Dimillian Liquid Glass](https://github.com/Dimillian/Skills/tree/05ba982bfeb0d77d3c97d4542b0ee15034d05f84/swiftui-liquid-glass) | Practical modifier, grouping, interactivity, transition and availability review points | Add concise native checks, verified against Apple; do not copy iOS-only availability guards or decorative interactive text examples |
| [R Shankras design collection](https://github.com/rshankras/claude-code-apple-skills/tree/eb2ddbc8962c1e21f2b0290d9cdb4c825ef85a23/skills/design) | Typography, interface copy and platform-specific behavior complement material guidance | Add focused text/icon/copy guidance; omit the broader animation, haptic and game-feel workflows |

## Keep the useful differences

The GitHub skill is explicitly native macOS-focused. This skill also serves existing websites and hybrid apps. It therefore keeps framework choice, routing, branding, native-window controls, and behavior intact unless the task asks to change them.

“Start without decorative frames” is useful for structural panes; “delete every card” is not. Cards remain appropriate for discrete objects, previews and interaction boundaries. A Kanban board should not lose its draggable cards merely to look more Mac-like.

The upstream Figma node map is reference-specific. Here the agent inspects the exact supplied node and its states, with available tools, and treats measurements as observations. There are no mandatory tool names, fixed node IDs, fixed output templates, or Figma prerequisite.

## New practical detail

The web reference now covers focus versus selection, semantic controls, forced colors, target size, contrast on composed backgrounds, overlay stacking/clipping and access after pane collapse. The original opaque-first CSS fallback remains; browser preference support is not equated with native OS integration. Thresholds and exceptions link to W3C guidance in [sources](../skills/macos-golden-gate-design/references/sources.md).

The native reference keeps standard components first and adds custom-glass review points. Apple's documentation explains that a container's spacing controls blending proximity: a larger value can merge shapes at rest. A blanket instruction to increase spacing would be misleading. Availability must match the actual OS, SDK and deployment target. [Apple custom-view documentation](https://developer.apple.com/documentation/swiftui/applying-liquid-glass-to-custom-views).

Verification is organized around observable outcomes and the changed surface. It explicitly separates screenshots, functional behavior, assistive-technology checks and performance evidence, while avoiding an exhaustive test mandate for every small visual edit.

## Scope and provenance

This is one self-contained replacement named `macos-golden-gate-design`, with the same implicit invocation policy. The repository adds human-facing installation and comparison documentation outside the installed skill. Source revisions and the original GitHub MIT attribution are retained. Other skills informed the comparison; their files, snippets, dependencies and process instructions were not copied into the package.
