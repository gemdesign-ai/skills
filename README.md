# skills

A collection of open-source skills for AI agent platforms. Each skill follows the [Agent Skills](https://agentskills.io) open standard (`SKILL.md`) and can be installed into any mainstream AI assistant.

## Available Skills

| Skill | Description |
|-------|-------------|
| [gemdesign-skill](./gemdesign-skill) | Generate high-fidelity, interactive UI prototype demos via the gemdesign CLI. Feed it a PRD and it designs all pages, previews them in real time, and syncs them to the GemDesign platform. |

## Installation

Each skill is a self-contained folder. Pick the one you need and install it via any of the methods below.

### Method 1: Universal installer (recommended, cross-platform)

Use the [skills CLI](https://skills.sh) to install directly from this GitHub repo:

```bash
npx skills add https://github.com/gemdesign-ai/skills --skill gemdesign-skill
```

This lands the skill in `~/.agents/skills/` (or `.agents/skills/` for project-scoped), which is recognized by most platforms.

### Method 2: Manual clone & copy

```bash
git clone https://github.com/gemdesign-ai/skills.git
cp -r skills/gemdesign-skill ~/.agents/skills/
```

### Method 3: Platform-specific directory

Copy the skill folder into your platform's own skills directory:

| Platform | Project path | Global path (macOS/Linux) |
|----------|--------------|---------------------------|
| Agent Skills (standard) | `.agents/skills/` | `~/.agents/skills/` |
| Claude Code | `.claude/skills/` | `~/.claude/skills/` |
| Codex | `.codex/skills/` | `~/.codex/skills/` |
| Cursor | `.cursor/skills/` | `~/.cursor/skills/` |
| TRAE | `.trae/skills/` | `~/.trae-cn/skills/` |
| Qoder | `.qoder/skills/` | `~/.qoder/skills/` |
| OpenClaw | `<workspace>/skills/` | `~/.openclaw/skills/` |
| QClaw | (uses OpenClaw) | `~/.openclaw/skills/` |
| WorkBuddy | — | `~/.workbuddy/skills/` |
| Opencode | `.opencode/skills/` | `~/.config/opencode/skills/` |
| Hermes | — | `~/.hermes/skills/` |

> **Windows global paths**: replace `~/` with `%userprofile%\` (e.g. `%userprofile%\.agents\skills\`). For Opencode, use `%appdata%\opencode\skills\`.
>
> **Notes**:
> - **Claude Code** also supports `/plugin marketplace add <github-org/repo>` to register this repo as a plugin source.
> - **TRAE** requires enabling `.agents/skills/` in *Settings → Skills & Commands → Import settings*; otherwise use `.trae/skills/`.
> - **Codex** requires enabling the experimental skills feature in `~/.codex/config.toml` (`[features] skills = true`).
> - **Hermes** can consume `~/.agents/skills/` by adding it to `external_dirs` in `~/.hermes/config.yaml`.
> - **WorkBuddy / QClaw** are primarily UI-managed; the file paths above are for manual placement. WorkBuddy also supports importing a Git repo URL via its UI.

See each skill's own `README.md` for prerequisites and usage details.

## Adding a New Skill

1. Create a new folder at the repo root, named after the skill (lowercase, hyphen-separated, matching the `name` field in `SKILL.md`).
2. Add a `SKILL.md` with YAML frontmatter (`name`, `description`) + Markdown instructions.
3. Add a skill-specific `README.md` with prerequisites and usage.
4. Add an entry to the table above.

## License

[MIT](./LICENSE)
