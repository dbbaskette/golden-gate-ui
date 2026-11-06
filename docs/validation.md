# Version 2.0.0 validation

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
