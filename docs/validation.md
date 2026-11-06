# Skill validation

## Version 2.1.0 — 2026-11-06

This revision changes instructions and UI metadata. The prior installation commands, CSS examples and implicit invocation policy are unchanged; their successful 2.0.0 evidence is reused.

Checks for 2.1.0:

- Skill-creator validation and parsed YAML metadata, including the new version and invocation prompt.
- Local Markdown targets and fragment anchors; reachability of every bundled reference.
- Git whitespace/diff review and installed-symlink identity against the checkout.
- Manual walkthroughs for the scenarios below, checking that all selected references give consistent direction.

| Request | Reviewed behavior |
| --- | --- |
| Eye-catching media workspace | Select a product-specific visual treatment; use real previews and responsive controls; preserve task access and reduced-effects appearance |
| Quiet native settings utility | Honor the restrained brief, keep standard controls, avoid a forced hero, animation or new font dependency |
| Dense data table with strong visual character | Keep meaningful rows/columns, selection and virtualization; use hierarchy and accent without inventing decorative data |
| Search input becomes slow after a visual refresh | Compare equivalent traces, preserve immediate input feedback, investigate expensive work before speculative caching or renderer replacement |
| Review only | Return located findings and improvements without editing the target app; distinguish defects from subjective design opportunities |
| Cosmetic refresh with missing retry support | Identify the recovery gap without inventing a backend capability or making unsupported success claims |

These are package checks and manual instruction reviews. No speedup or downstream visual-quality improvement has been measured in an application. The tested source is the version 2.1.0 tree in the PR introducing this section; publication and merge do not change that evidence when file contents remain identical.

## Version 2.0.0 — retained evidence

This release changes skill documentation and packaging. It does not ship a UI application or an SDK integration. Validation runs locally on macOS; no VM or hosted CI is needed for these documentation checks.

## Checks

- Codex skill-creator validator: frontmatter, name and scaffold checks.
- YAML metadata: stable skill name, version 2.0.0, implicit invocation enabled, valid default invocation prompt.
- All local Markdown links resolve; every bundled reference is reachable from the skill entry point.
- The independently installable folder retains its MIT license, matching the repository license.
- README replacement commands exercised against disposable directories: fresh install, replacement of an existing directory, and replacement of an existing symlink. Prior installs remain in backups outside the discovery directory.
- Git whitespace check and tracked-file review before publication.

The system Homebrew Python lacked PyYAML; validation used the existing Python 3.13.5 environment with PyYAML 6.0.3. No packages or system settings were changed.

## Manual instruction review

These are scenario walkthroughs of the instructions, not independent agent executions or rendered app tests.

| Representative request | Expected routing and scope checked |
| --- | --- |
| Restyle a React app with inline navigation | Shared visual language + web reference; retain stack, navigation and brand; no invented sidebar |
| Review a SwiftUI utility window | Shared visual language + native reference; findings only, actual SDK availability, no automatic deployment-target increase |
| Improve a Kanban app's excessive glass | Keep meaningful draggable cards; concentrate material on navigation/commands/transient surfaces |
| Make an Electron UI feel native | Preserve window hit targets, shortcuts and security settings; CSS approximation does not imply OS glass integration |
| Match a supplied Figma node | Inspect that target with available tools; report unavailable access and distinguish observed values from inference |
| Fix readability in forced colors | Use system colors, borders and focus indicators; preserve semantics; check composed contrast and reduced effects |
| Produce a screenshot-based mockup | Preview scope only; do not claim app implementation or verified interaction behavior |

## Limits

No visual output, VoiceOver behavior, native SDK build, browser rendering, or downstream agent quality benchmark is claimed by these packaging checks. The skill instructs future implementation tasks to verify their actual changed UI and report untested conditions.
