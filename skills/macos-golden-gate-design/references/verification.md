# Verify the changed surface

Choose checks based on the requested deliverable and changed behavior. A review needs evidence for its findings; a mockup needs visual checks; an implementation needs rendered and functional checks. Do not require a new test framework or an exhaustive platform matrix for a small style change.

## Representative acceptance checks

| Check | Evidence of success |
| --- | --- |
| Structure | Navigation, selection, commands and content remain obvious with blur disabled; retained frames have semantic purpose |
| Visual character | The intended focal point and product identity are apparent; supporting regions remain useful; a quieter brief or exact reference is respected |
| Task flow | The primary action is discoverable, its result is clear, and failure/no-results states offer an honest next step; decoration does not delay access |
| Real content | A populated screen with long labels and realistic data remains readable; empty/loading/error states retain stable controls |
| Layout | Narrow, typical and wide layouts retain access to commands and panes; overlays and focus are not clipped |
| Appearance | Required light/dark modes preserve text, boundaries and selected/disabled states; native inactive windows remain coherent |
| Keyboard | Main task can be completed without a pointer; focus differs from selection; dialogs dismiss and restore focus appropriately |
| Assistive technology | Changed controls expose correct role, name and state; reading order follows the task; important status changes are announced where appropriate |
| Reduced effects | Opaque/high-contrast treatment preserves hierarchy; reduced motion still communicates state; web forced-colors retains essential boundaries |
| Behavior | Existing actions, filtering, sorting, navigation and data remain intact; relevant project checks pass |
| Performance | When affected, comparable before/after traces cover the changed interaction, scrolling or loading; project budgets are met or deviations are reported; costly effects and idle work are justified |

On the web, include text enlargement/zoom and supported browser differences. On native macOS, include changed menu shortcuts, toolbar overflow, window activation and pane resizing. Do not count an emulated CSS preference as proof of OS integration or a screenshot as proof of VoiceOver behavior.

## Evidence and reporting

Inspect the running UI when feasible. Record the screen, appearance, size, and meaningful states observed; capture before/after images when useful for comparison. Run existing targeted checks after a coherent slice, then the project's required full verification before completion. Reuse valid evidence for an unchanged tree/environment.

Critique visual impact and task clarity separately: a readable screen can still feel generic, and a striking screenshot can still hide the main action. When the result misses the chosen direction, revise the relevant composition, type, content or emphasis and inspect it again. Use representative content and the same viewport for comparisons.

For a performance claim, record the scenario, build, data size, device/runtime, metric and before/after result. Repeat enough to distinguish a meaningful change from measurement noise. If no baseline is available, report a current observation rather than an improvement. Use existing budgets or agree on a target when a performance requirement is unresolved; do not invent one global effect count or frame-rate promise.

Separate tested, inferred, and unavailable results. If the app cannot run or the accessibility setting cannot be exercised, state the exact limitation and complete the checks still available. Do not call a design verified solely because code compiles or the CSS contains a media query.

When reviewing, prioritize broken access, task completion, and measured responsiveness problems, then clarity and the requested visual impact. State whether a finding is a defect, usability friction, or a design opportunity. Tie it to a location, consequence, and practical correction; do not present taste as a functional defect. Report applicable findings without a checklist of hypothetical problems.
