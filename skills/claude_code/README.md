# Claude Code Skills (Scaffold)

Category-first folder layout and conventions for writing **Claude Code** Agent Skills.

## Quick Start (Create a Skill)

1. Pick a category folder (for example `document_processing/`)
2. Create a new skill folder (for example `pdf_to_markdown_converter/`)
3. Add `SKILL.md` (required) and optional `scripts/`, `references/`, `assets/`
4. Install the skill into Claude Code (copy the skill folder)
5. Verify with `claude --list-skills`

Minimal `SKILL.md` example (YAML frontmatter is required by Claude Code):

```yaml
---
name: pdf-to-markdown-converter
description: Convert a PDF into clean Markdown while preserving headings and lists.
---

# PDF to Markdown Converter

## Instructions
- Ask for the input PDF path and the desired output path.
- Convert and validate output (headings, lists, code blocks).
- Explain any lossy conversions and limitations.
```

## Directory Layout

Skills should live under a category folder:

```
skills/claude_code/
├── business_marketing/
├── collaboration_project_management/
├── communication_writing/
├── creative_media/
├── data_analysis/
├── development_code_tools/
├── document_processing/
├── productivity_organization/
└── security_systems/
```

Suggested naming convention:
- Skill folder: `snake_case` (example: `pdf_to_markdown_converter`)
- YAML `name`: `kebab-case` (example: `pdf-to-markdown-converter`)

## Installing Into Claude Code

Common locations (may vary by OS/version; adjust to your Claude Code setup):

### User-Level (Global)

```bash
mkdir -p ~/.config/claude-code/skills/
cp -r ./document_processing/my_skill ~/.config/claude-code/skills/
claude --list-skills
```

### Project-Level (Local)

```bash
mkdir -p .claude/skills/
cp -r ./document_processing/my_skill .claude/skills/
```

## Progressive Loading (Why Skills Stay Small)

Claude Code typically uses a “progressive disclosure” approach:
- Loads lightweight metadata first (to decide relevance)
- Loads `SKILL.md` instructions when the skill is triggered
- Loads optional files from `references/`, `assets/`, `scripts/` only when needed

## Contributing

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for repository conventions and quality guidelines.

## Official Docs

- Claude Agent Skills Overview: https://platform.claude.com/docs/zh-TW/agents-and-tools/agent-skills/overview
- Claude Skills Quickstart: https://platform.claude.com/docs/zh-TW/agents-and-tools/agent-skills/quickstart
- Claude Skills Best Practices: https://platform.claude.com/docs/zh-TW/agents-and-tools/agent-skills/best-practices
- Main repo README: [README.md](../../README.md)

## Security Note

Only use skills from trusted sources. Skills can run commands and access local files—review `SKILL.md` and any `scripts/` before installing.
