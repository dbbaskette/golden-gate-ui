# SwiftUI and AppKit

Use real native structure where the app already uses SwiftUI/AppKit. Do not replace the framework's standard behavior with a hand-drawn browser-style shell.

- SwiftUI: begin with the application's existing scenes, `NavigationSplitView`, `List`, `Table`, `Form`, toolbar, search, inspector and standard presentations as appropriate to the task.
- AppKit: preserve standard windows, split views, toolbars, source lists/outline views, tables, menus and sheets.
- Use native semantic colors, typography, materials and state handling. Let the OS own control metrics, focus, inactive-window adaptation and supported personalization.
- A custom glass effect is for a real custom control or surface the standard components cannot express. Keep long-form content and data regions stable.

Consult installed SDK declarations and official docs for the exact Liquid Glass API and availability. Guard newer APIs and use a readable standard material/opaque fallback when supporting earlier systems. Building with a newer SDK does not itself authorize raising the deployment target. Do not guess an API based on a screenshot or hard-code measurements from a Figma reference as universal system dimensions.

## Custom Liquid Glass, only where needed

After choosing standard components, use these checks for a genuinely custom control. Verify signatures and platform availability in [Apple's custom-view guide](https://developer.apple.com/documentation/swiftui/applying-liquid-glass-to-custom-views) and the installed SDK.

- Prefer supported glass button styles for buttons. A visual effect on `Text` or `Image` does not create button semantics or an action.
- Apply `glassEffect` after the padding, size, and appearance modifiers that define its visible content. Choose a shape that fits the control, rather than accepting a capsule everywhere.
- Group related custom glass views with `GlassEffectContainer` for coordinated rendering. Its spacing affects when nearby shapes blend; too much spacing can merge controls at rest. Do not wrap every row in its own container.
- Use interactive glass only on actionable controls. Tint communicates emphasis; it should not color every surface.
- Use stable `glassEffectID` values and a namespace for intentional morphing across hierarchy changes. A state change must remain understandable with reduced motion.
- Gate the API for the actual target OS and deployment minimum. An iOS availability check copied from a tutorial is insufficient for macOS. Keep the same action and accessible label in the fallback.
- For AppKit, inspect `NSGlassEffectView` and related available APIs only when standard components do not cover the surface. `NSVisualEffectView` material and Liquid Glass are different implementations; label fallbacks accurately.

These are implementation decision points, not a requirement to retrofit custom glass into system toolbars. Inspect SDK declarations before writing a version-specific example; do not invent a “Golden Gate” API.

Keep sidebar/inspector collapse and resize behavior, toolbar overflow, native menu commands, VoiceOver and keyboard navigation. Verify light/dark, active/inactive, compact/default/wide, Reduce Transparency, Increase Contrast and Reduce Motion to the degree relevant to the changed surface. Report untested combinations rather than treating one static preview as native acceptance.
