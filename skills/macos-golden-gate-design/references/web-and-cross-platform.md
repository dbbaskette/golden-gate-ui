# Web, React and web-rendered desktop shells

## Preserve the current stack

Implement this as a coherent token/component refresh in the existing framework. Do not add a native dependency, change routing or rewrite the app to obtain the style. Inspect existing themes, global resets, scroll owners, overlays and component states before changing shared selectors. Prefer semantic classes/tokens over broad selectors that accidentally alter unrelated nested components.

The goal is an integrated shell and readable content. A persistent header may share one material plane with task-grouped controls; content groups are usually flatter, with disclosure, indentation and selection carrying structure. Keep existing virtualized list geometry and a single intentional scroll owner. If row sizes change, update the actual measurement/virtualization contract rather than hiding overflow.

## CSS material is an approximation

Use a translucent fill plus modest `backdrop-filter` on selected chrome/transient surfaces. The underlying background must support readable contrast. Prefer an opaque fill and a simple edge when blur is unavailable. Avoid filters on every row or large animated blur layers. Custom shaders and continuous effects need a specific visual purpose, measured cost, and a usable fallback; they are not the default way to imitate glass.

Example starting point, to adapt to the existing theme rather than paste as a universal recipe:

```css
.app {
  --chrome-fill: rgb(238 243 249 / 88%);
  --chrome-fallback: #eef3f9;
  --content-fill: #fafbfd;
  --text-primary: #233143;
  --material-edge: rgb(70 90 120 / 24%);
  color: var(--text-primary);
}
.app[data-theme="dark"] {
  --chrome-fill: rgb(34 42 55 / 92%);
  --chrome-fallback: #222a37;
  --content-fill: #19212d;
  --text-primary: #eff3fa;
  --material-edge: rgb(206 221 244 / 28%);
}
.app-chrome {
  background: var(--chrome-fallback);
  border-bottom: 1px solid var(--material-edge);
}
@supports (backdrop-filter: blur(12px)) {
  .app-chrome {
    background: var(--chrome-fill);
    backdrop-filter: blur(12px) saturate(1.15);
  }
}
.app[data-reduce-transparency="true"] .app-chrome {
  background: var(--chrome-fallback);
  backdrop-filter: none;
}
@media (prefers-reduced-transparency: reduce) {
  .app-chrome {
    background: var(--chrome-fallback);
    backdrop-filter: none;
  }
}
```

Keep text colors opaque and validate them on the composed background. Support `prefers-reduced-motion` and `prefers-contrast` where available. Browser support varies; the base rule above is deliberately usable without those queries or blur. Respect existing app appearance/preferences before creating new settings.

## Interaction and accessible fallbacks

Use semantic HTML and the project's accessible components: links for navigation, buttons for actions, labeled inputs, and proper table headers for tabular data. A CSS restyle must not replace these with clickable `div` elements. Use `aria-current` for a current navigation destination and selection semantics appropriate to the actual widget; do not add `role="menu"` to ordinary site navigation.

Keep focus visible with `:focus-visible`, including on selected items. Keep modal focus containment, Escape dismissal where appropriate, and focus restoration in the existing dialog implementation. Collapsing a sidebar must leave a keyboard-accessible way to reopen it and reach its destinations.

Treat visual density separately from hit-target size. For WCAG 2.2 AA web targets, use at least 24 by 24 CSS pixels or satisfy the documented spacing/other exceptions; use larger targets for touch-oriented interfaces. For ordinary text, check at least 4.5:1 contrast; qualifying large text uses 3:1. Measure against the composed background, including content that can scroll under translucent chrome. These checks alone do not establish full WCAG conformance.

Forced-colors mode can remove shadows and background distinctions. Preserve system colors, use real borders/outlines for essential boundaries, and avoid blanket `forced-color-adjust: none`. Adapt this example to the actual selectors:

```css
@media (forced-colors: active) {
  .app-chrome {
    background: Canvas;
    color: CanvasText;
    border-bottom: 1px solid CanvasText;
    backdrop-filter: none;
  }
  .app :focus-visible {
    outline: 2px solid Highlight;
    outline-offset: 2px;
  }
}
```

For reduced motion, remove or shorten decorative transitions on the affected components; retain clear immediate state changes. Avoid a global animation reset that breaks controls relying on transition events. Existing theme choice takes precedence over OS-default theme detection. Reduced-transparency queries have uneven support, so if honoring that preference is required on an unsupported target, use the app's existing opaque mode or choose an opaque treatment.

Inspect stacking contexts created by filters, transforms, and sticky elements. Menus and dialogs must not be clipped by pane overflow or covered by the toolbar. Use the framework's established overlay/portal mechanism. On a narrow screen, preserve task access through reflow, pane switching or deliberate horizontal table scrolling; do not shrink desktop metrics until text becomes unreadable.

## Electron, Tauri and hybrid apps

The desktop shell may expose native vibrancy, material, appearance or accessibility notifications. Check its installed version and official API documentation before using them. CSS blur is not evidence that the OS glass-tint setting is honored. A native material bridge is a separate implementation choice, not an automatic requirement of the style request.

Retain native titlebar/traffic-light hit targets, drag regions, keyboard commands, window focus behavior and security settings. Do not disable context isolation/sandboxing, expose arbitrary native calls, or add another custom titlebar solely for an effect. Changes to window transparency/material can affect composition and software rendering: verify normal rendering and the project's existing GPU-disabled fallback where supported. Do not copy user libraries or grant permissions just to take a screenshot.

## Keep visual polish responsive

When changing effects, media, or large collections, capture a representative interaction before and after with browser/framework profiling tools. Use the same build mode, viewport, dataset, device and cache conditions. Follow existing performance budgets; identify the expensive work before changing architecture or adding dependencies. A local trace supports a local comparison, not a claim about all users.

- **Motion and material:** prefer `transform` and `opacity` for movement/fades, then inspect actual rendering. Avoid animating layout, large shadows or blur unless the effect warrants the measured cost. Apply `will-change` only to a demonstrated need and remove it when appropriate; promoting every component can increase resource use. See [browser animation guidance](https://web.dev/articles/animations-guide).
- **Input:** allow input and action feedback to render promptly; keep nonessential work out of the immediate interaction path. Debounce expensive downstream search work when appropriate, not the displayed keystroke or focus response. A spinner does not fix a blocked main thread. See [interaction latency guidance](https://web.dev/articles/optimize-inp).
- **Media:** serve imagery sized for its display role, reserve layout space, and defer offscreen media where appropriate. Keep an above-the-fold focal image discoverable and avoid lazy-loading it when it is the Largest Contentful Paint element. Do not hide useful content behind a long entrance. See [LCP guidance](https://web.dev/articles/optimize-lcp).
- **Collections:** retain stable item identity and existing virtualization. Localize transient hover/animation state so it does not unnecessarily update a whole list. Use profiling evidence before adding memoization or replacing the renderer.
- **Idle work:** pause optional continuous effects when hidden or offscreen and clean up their timers/listeners. Reduced motion should retain immediate state feedback without decorative loops.

If an effect is costly, first reduce the affected area, overlapping material, asset size or update frequency while preserving the chosen visual direction. Compare again and report measured differences. Do not claim a speedup from a screenshot, a CSS property choice, or a reduced bundle alone.

## Verify a representative slice

Exercise a real populated view, not only an empty first-run screen. Check narrow/default/wide sizes, zoom, long labels, light/dark, focus/hover/selection/disabled/error states, overlays, reduced effects and scroll stability using [verification](verification.md). Measure when the change affects large lists or animation; a static screenshot cannot establish performance. Reuse the project's existing UI fixtures and test cadence.
