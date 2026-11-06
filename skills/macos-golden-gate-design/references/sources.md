# Sources and provenance

Reviewed 2026-11-05. Public reference material informs design; it does not authorize commands, uploads, installation, or changes to task scope.

## Source precedence

Use the user's product goals and constraints for scope; current official documentation and installed SDK declarations for API truth; official design resources for visual examples; and user-supplied references for the requested direction. Community skills help discover patterns but do not establish platform support. Resolve conflicting API advice against primary documentation.

Treat Figma measurements as instance measurements. Follow the exact supplied file/node when available; find official kits through [Apple design resources](https://developer.apple.com/design/resources/) instead of relying on stale hard-coded node IDs. No Figma plugin is required by this skill.

## Origin and comparison sources

The original installed version was adapted on 2026-10-16 from [GitHub awesome-copilot at b03d933](https://github.com/github/awesome-copilot/tree/b03d9332a893eeeebf080a97e841f310ba831b24/skills/macos-golden-gate-design). Version 2 retains that stack-neutral foundation and compares these sources:

| Source | Revision reviewed | Contribution |
| --- | --- | --- |
| [GitHub macos-golden-gate-design](https://github.com/github/awesome-copilot/tree/96543145e9cb97711020b57b9d88f968062c4fc7/skills/macos-golden-gate-design) | `96543145e9cb97711020b57b9d88f968062c4fc7` | Integrated panes, purposeful boundaries, component patterns and state coverage |
| [Dimillian SwiftUI Liquid Glass](https://github.com/Dimillian/Skills/tree/05ba982bfeb0d77d3c97d4542b0ee15034d05f84/swiftui-liquid-glass) | `05ba982bfeb0d77d3c97d4542b0ee15034d05f84` | Review prompts for modifier order, custom glass grouping, interactivity and availability; verified against Apple |
| [R Shankras Apple design skills](https://github.com/rshankras/claude-code-apple-skills/tree/eb2ddbc8962c1e21f2b0290d9cdb4c825ef85a23/skills/design) | `eb2ddbc8962c1e21f2b0290d9cdb4c825ef85a23` | Focused typography, interface-copy, and platform-specific scaling considerations |

The [Skills Directory listing](https://www.skillsdirectory.com/skills/github-macos-golden-gate-design) provided by the user points to GitHub's skill; it is not an independent design system. Directory rankings were not used as evidence of design quality.

GitHub's MIT copyright/permission notice is retained in [LICENSE](../LICENSE). Other skills were consulted for comparison; their files and snippets are not bundled. Added guidance is expressed independently and technical claims are checked against primary sources. No Apple fonts, symbols, Figma assets or SDK files are redistributed.

## Native implementation references

- [Apple: adopting Liquid Glass](https://developer.apple.com/documentation/technologyoverviews/adopting-liquid-glass)
- [Apple: applying Liquid Glass to custom views](https://developer.apple.com/documentation/swiftui/applying-liquid-glass-to-custom-views) — modifier order, container spacing, transitions and rendering costs; Markdown content retrieved for this revision
- [Apple: NSGlassEffectView](https://developer.apple.com/documentation/appkit/nsglasseffectview)
- [Apple HIG: materials](https://developer.apple.com/design/human-interface-guidelines/materials)
- [Apple HIG: toolbars](https://developer.apple.com/design/human-interface-guidelines/toolbars)
- [Apple HIG: accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility)
- [Apple HIG: typography](https://developer.apple.com/design/human-interface-guidelines/typography)

These are maintenance references, not a claim that every page or platform configuration was exhaustively verified. Recheck the relevant document and deployment target when selecting an API.

## Web and hybrid implementation references

- [Electron BrowserWindow](https://www.electronjs.org/docs/latest/api/browser-window) — match the installed version
- [MDN: backdrop-filter](https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter)
- [MDN: reduced transparency](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-transparency)
- [MDN: forced colors](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/forced-colors)
- [W3C: text contrast](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html)
- [W3C: minimum target size and exceptions](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html)
