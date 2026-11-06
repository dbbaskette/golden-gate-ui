# Verify the changed surface

Choose checks based on the requested deliverable and changed behavior. A review needs evidence for its findings; a mockup needs visual checks; an implementation needs rendered and functional checks. Do not require a new test framework or an exhaustive platform matrix for a small style change.

## Representative acceptance checks

| Check | Evidence of success |
| --- | --- |
| Structure | Navigation, selection, commands and content remain obvious with blur disabled; retained frames have semantic purpose |
| Real content | A populated screen with long labels and realistic data remains readable; empty/loading/error states retain stable controls |
| Layout | Narrow, typical and wide layouts retain access to commands and panes; overlays and focus are not clipped |
| Appearance | Required light/dark modes preserve text, boundaries and selected/disabled states; native inactive windows remain coherent |
| Keyboard | Main task can be completed without a pointer; focus differs from selection; dialogs dismiss and restore focus appropriately |
| Assistive technology | Changed controls expose correct role, name and state; reading order follows the task; important status changes are announced where appropriate |
| Reduced effects | Opaque/high-contrast treatment preserves hierarchy; reduced motion still communicates state; web forced-colors retains essential boundaries |
| Behavior | Existing actions, filtering, sorting, navigation and data remain intact; relevant project checks pass |
| Performance | When affected, representative scrolling/resizing/animation has no demonstrated regression; no blur per row or unnecessary continuous effects |

On the web, include text enlargement/zoom and supported browser differences. On native macOS, include changed menu shortcuts, toolbar overflow, window activation and pane resizing. Do not count an emulated CSS preference as proof of OS integration or a screenshot as proof of VoiceOver behavior.

## Evidence and reporting

Inspect the running UI when feasible. Record the screen, appearance, size, and meaningful states observed; capture before/after images when useful for comparison. Run existing targeted checks after a coherent slice, then the project's required full verification before completion. Reuse valid evidence for an unchanged tree/environment.

Separate tested, inferred, and unavailable results. If the app cannot run or the accessibility setting cannot be exercised, state the exact limitation and complete the checks still available. Do not call a design verified solely because code compiles or the CSS contains a media query.

When reviewing, prioritize broken access and behavior first, readability and hierarchy second, and decorative consistency last. Tie each finding to a location, user-visible consequence, and practical correction. Report only applicable findings, not a completed checklist of hypothetical problems.
