---
name: macos-golden-gate-design
description: Design, restyle, or review distinctive, eye-catching interfaces in the macOS Golden Gate / restrained Liquid Glass style. Use for Golden Gate styling, integrated Mac-like layouts, or reducing excessive cards and glass in web, Electron, SwiftUI, or AppKit interfaces while preserving the existing stack.
license: MIT
metadata:
  version: "2.1.0"
---

# Golden Gate UI design

Create a distinctive, eye-catching interface through deliberate composition, expressive focal points, and polished interaction. Translate Golden Gate into integrated panes, readable content, compact commands, and selective material using the existing stack and product identity. Restraint governs competing effects; visual character is part of the goal. Honor quieter briefs and precise reference matching. The skill name does not establish SDK availability or require a native rewrite.

## Recognize the intent

"Make this look like Golden Gate", "macOS Golden Gate style", and "Golden Gate Liquid Glass" are sufficient direction. Infer the stack and product from the supplied context. Use the existing implementation and interaction model unless the user requests a structural change. A review asks for findings; a mockup asks for a preview; implementation asks for code. Do not silently escalate between them or publish/install/restart anything without authorization.

## The recognizable style

- **An integrated composition.** Title, navigation and commands belong to the application structure. Panes share boundaries; the window is not surrounded by another decorative app-shaped container.
- **A memorable visual direction.** Choose a focal point or recurring treatment rooted in the product: compelling imagery, a distinctive accent, expressive display type, an informative visualization, or a well-judged interaction. Scale its emphasis to the screen's job; a dense utility need not acquire a hero section.
- **Quiet content, expressive controls.** Put carefully diffused material on navigation, toolbar controls, search and transient surfaces. Keep meeting lists, documents, dense data, forms and reading regions visually stable.
- **Depth with restraint.** A subtle light-catching edge, darker material boundary and small shadow can communicate a real elevated control. Do not distribute blur, capsules and shadows across every row.
- **Hierarchy before effects.** Use alignment, system-like typography, spacing, selection and semantic surface changes. A selected item can have a rounded highlight without making every neighboring item a card.
- **Color with a job.** Build a coherent palette around the product's identity. Rich accents, gradients and imagery can establish character while reading surfaces remain stable. Preserve semantic status colors and contrast; a specific hue, wallpaper gradient or traffic lights are not requirements.
- **A coherent opaque version.** Reduced transparency, stronger contrast, inactive states and narrow layouts must retain the same hierarchy and functionality.

Read [the visual language and component patterns](references/design-language.md) when making or reviewing a design. Then select only the relevant implementation reference:

- HTML/CSS, React, Vue, Electron, Tauri or another web-rendered shell: [web and cross-platform](references/web-and-cross-platform.md).
- SwiftUI/AppKit: [Apple-native implementation](references/apple-native.md).
- Other frameworks: apply the visual language using their real layout, material and accessibility primitives. Do not invent APIs or require a rewrite.
- Platform claims, SDK availability or an exact current component reference: consult [sources and provenance](references/sources.md). Check official documentation before promising platform behavior; the style should still work when that API is unavailable.

## Work from the actual product

1. Identify the audience, primary task and existing screen structure. Trace the relevant path from entry through action to feedback and recovery. A short map is enough, for example `group list → select meeting → inspect detail → join or resolve error`. Do not add a sidebar just because a reference app has one.
2. Audit containers. Keep boundaries that explain selection, drag/drop, discrete objects, pane ownership or transient UI. Replace redundant wrappers with spacing, headings or separators. Preserve existing useful cards when their boundaries genuinely communicate object identity.
3. State the visual direction briefly: what should draw attention, why it fits this product, and how supporting regions stay readable. Choose semantic tokens for surfaces, text, accent, states, typography, spacing and motion; include required appearances. Keep material tokens separate from content tokens. Use [visual direction](references/design-language.md#visual-direction) to avoid generic styling.
4. Define a material map. Name the few surfaces receiving diffusion/elevation and the regions staying opaque. Use one material layer where possible; glass-on-glass is not a contrast strategy.
5. Resolve component behavior before effects: selection versus focus, toolbar overflow, pane collapse, scroll ownership, feedback, recovery, and overlay dismissal. Use real controls with accessible names. Preserve menu commands, shortcuts, and useful object boundaries. Follow [task flow](references/design-language.md#task-flow-and-feedback) for the changed surface.
6. Apply the style in coherent slices. Shared shell and tokens first, then representative content and controls, then other screens and error/empty/loading states. Do not change data, workflow or information architecture for a cosmetic refresh.
7. Inspect the rendered result for visual character as well as usability, and exercise real controls. For changed motion, large datasets, heavy media or reported slowness, compare representative performance before and after using the stack reference. Use [verification](references/verification.md); distinguish observations from untested states and reuse valid evidence.

Scale the process to the request. Choose routine visual treatments within the brief without another approval pause. A small visual adjustment does not need a design interview. Existing approval of a mockup authorizes its requested implementation; ask only when a consequential product decision or scope expansion remains unresolved.

When a screenshot or Figma node is supplied, inspect that exact target, its relevant states, and available variables using the tools actually present. Record the source and distinguish observed measurements from inferred behavior. Use Apple design resources for native reference; never turn one kit's dimensions into universal tokens. Missing Figma access need not block work supported by supplied screenshots or code, but disclose the limitation.

## Review questions

- Can someone identify navigation, current selection, primary action and primary content without the blur?
- What makes this interface recognizable, and does its focal point support the primary task? Does it still have character with motion and transparency reduced?
- Does the composition feel integrated, rather than a set of floating dashboard panels?
- Are the few rounded/material controls grouped by task, with readable edges and text?
- Are labels, important commands, status and keyboard focus visible in all required appearances?
- Does the layout remain usable with reduced transparency/motion, strong contrast, long labels and resizing?
- Do actions respond promptly, communicate honest progress or completion, and provide a usable recovery path? Were performance claims measured on representative content?
- Are claims accurate: **native system material** only when using the OS implementation, **Golden Gate-inspired** for a browser approximation?

For a review, prioritize concrete findings with location, consequence, and correction. For implementation, report the changed direction, stack-specific translation, verification, and meaningful limits. Keep mockup-only results distinct from app changes. A short pane/material map is useful when structure changes; do not force a fixed report template.

## Provenance

Adapted from GitHub's MIT-licensed `macos-golden-gate-design`, broadened to stack-neutral design and existing-product constraints. Copyright and permission notice are in [LICENSE](LICENSE); original source, revision and adaptation notes are in [sources](references/sources.md).
