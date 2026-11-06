# Clarity, UX and performance audit

Audited version 2.0.0 at `41526c7` on 2026-11-06. Version 2.1.0 addresses the findings below. This is an audit of design instructions, not a performance audit of a running application.

| Area | Finding and consequence | Change |
| --- | --- | --- |
| Visual direction | Removal rules and neutral-surface guidance dominated; an agent could produce a correct but generic interface | Make eye-catching, product-specific character explicit; choose a focal point and coordinated type/color/imagery/motion while honoring quieter briefs |
| Scope clarity | “Ask when a new material choice is needed” could be read as approval for every glass or color decision | Choose routine visual treatments within the brief; ask only for unresolved consequential product decisions or expanded scope |
| UX | Control semantics were covered better than the path from action to result | Trace the primary task; distinguish empty/no-results/error states; preserve context and provide honest feedback and supported recovery |
| Performance | “Measure when affected” lacked a comparison method or actionable rendering guidance | Add baseline conditions, profiling, input feedback, media priority, collection updates, idle work and native Instruments guidance |
| Acceptance | The review favored removing decoration without checking whether the requested visual character survived | Evaluate task clarity and visual impact separately; distinguish defects, friction and design opportunities |

## Visual direction

The default aims for a memorable interface. Its expression depends on the product: a media browser may use strong previews, a data workspace may use clear information graphics, and a small utility may get its character from alignment, accent and responsive controls. These examples are options, not features to add automatically.

Rich color, gradients, imagery and deliberate display typography are available tools. Reading areas remain stable and reduced effects retain hierarchy and character. Native control behavior, existing brand identity, meaningful object boundaries, and specific quieter briefs remain intact.

## Performance scope

The browser guidance covers animation properties, selective layer promotion, prompt input rendering, image loading, collection updates and optional idle effects. Technical guidance was checked against primary sources: [animation rendering](https://web.dev/articles/animations-guide), [interaction latency](https://web.dev/articles/optimize-inp), and [LCP optimization](https://web.dev/articles/optimize-lcp).

The native guidance points to [Apple's Instruments walkthrough](https://developer.apple.com/videos/play/wwdc2025/306/) to distinguish expensive view updates from rendering hitches. Optimization follows measured work; no universal effect limit or frame-rate promise is introduced.

## Verification boundary

Metadata, links, reference routing and installation consistency are checked for this package. Scenario review covers an expressive media app, a quiet utility, a dense table, a slow search interaction and review-only scope. These are manual instruction walkthroughs, not agent benchmarks or rendered UI tests. See [validation](validation.md) for the recorded scope and limitations.
