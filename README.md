# Golden Gate UI

One design skill for integrated layouts, calm content, and restrained Liquid Glass across web, Electron/Tauri, SwiftUI, and AppKit. It preserves the application's stack, behavior, and product identity.

The skill is **`macos-golden-gate-design`**, version **2.0.0**. [Read the skill](skills/macos-golden-gate-design/SKILL.md) or the [comparison and design decisions](docs/comparison.md).

## What changed

- Kept the original cross-platform scope and meaningful-card exceptions.
- Added concrete sidebar, toolbar, table, form, inspector, and dialog patterns.
- Made selection, focus, keyboard access, overflow, and responsive behavior explicit.
- Expanded web guidance for semantic controls, forced colors, contrast, hit targets, overlay clipping, and reduced effects.
- Added native custom-glass checks, with SDK-aware availability and accurate container-spacing guidance.
- Added focused typography and interface-copy guidance, plus proportionate verification.
- Kept one concise entry point with references loaded only when relevant.

## Install or replace the Codex skill

Clone this repository into `~/Projects/golden-gate-ui`. The commands below move any existing installation outside skill discovery and link this checkout as the single active version. Review local changes before updating a linked checkout.

```bash
git clone https://github.com/dbbaskette/golden-gate-ui.git ~/Projects/golden-gate-ui
```

Run the following with Bash (skip cloning if this checkout already exists):

```bash
set -e
skill_source="$HOME/Projects/golden-gate-ui/skills/macos-golden-gate-design"
skill_target="${CODEX_HOME:-$HOME/.codex}/skills/macos-golden-gate-design"
skill_backups="${CODEX_HOME:-$HOME/.codex}/skill-backups"
test -f "$skill_source/SKILL.md"
mkdir -p "$(dirname "$skill_target")" "$skill_backups"
if [ -e "$skill_target" ] || [ -L "$skill_target" ]; then
  skill_backup_dir="$(mktemp -d "$skill_backups/golden-gate.XXXXXX")"
  mv "$skill_target" "$skill_backup_dir/macos-golden-gate-design"
  echo "Previous installation: $skill_backup_dir/macos-golden-gate-design"
fi
ln -s "$skill_source" "$skill_target"
```

The symlink keeps installation and checkout in sync. Restart or begin a new agent session if its skill catalog was already loaded. Other agents can install the self-contained `skills/macos-golden-gate-design` folder in their supported skill directory; no companion skills are required.

## Use

- “Use $macos-golden-gate-design to restyle this React app. Keep its existing navigation and branding.”
- “Review this SwiftUI window for Golden Gate design issues; do not modify code.”
- “Make this Electron interface feel integrated and less boxed. Preserve shortcuts and window controls.”
- “Create a Golden Gate-inspired mockup from this screenshot.”

Browser effects are described as Golden Gate-inspired. Native system material claims require the actual OS implementation.

## Maintenance and verification

Keep the name stable so existing invocations continue to work. Change shared design guidance in `SKILL.md` and `references/design-language.md`; keep framework-specific details in their references. Record comparison revisions and official references in [sources](skills/macos-golden-gate-design/references/sources.md).

For a documentation-only update, validate skill metadata, local links, reference reachability, and representative routing scenarios. The Codex skill-creator validator can check the package when installed:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/macos-golden-gate-design
```

This repository has no application runtime or application test suite. Skill validation does not prove the visual quality of every interface an agent later creates. [Verification notes](docs/validation.md) record the checks performed for this release.

## License and attribution

MIT. Adapted from GitHub's `macos-golden-gate-design`; its notice is retained in both [the repository license](LICENSE) and the independently installable skill. Additional comparison sources and decisions are documented with pinned revisions. Apple assets and third-party skill bundles are not included.
