# Codex Skills (Scaffold)

Category-first folder layout and conventions for writing **OpenAI Codex** skills.

## Quick Start (Create a Skill)

1. Pick a category folder (for example `development_code_tools/`)
2. Create a new skill folder (for example `deployment_automation/`)
3. Add `SKILL.md` (required) and optional `scripts/`, `references/`, `assets/`
4. Install the skill into Codex by copying the skill folder into a skills directory Codex loads
5. Invoke it explicitly as `$skill-name`

Minimal `SKILL.md` example (no YAML frontmatter for Codex):

```markdown
# Deployment Automation

## What this skill does
Automate deploy/rollback steps for a service.

## Instructions
- Ask for environment, service name, and rollout strategy.
- Print an exact command plan before executing.
- Verify the deployment and summarize results.
```

## Directory Layout

Skills should live under a category folder:

```
skills/codex/
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

## Installing Into Codex

Codex loads skills from multiple locations (highest precedence first):

| Scope | Location | Use Case |
|-------|----------|----------|
| REPO | `$CWD/.codex/skills` | Task-specific for current directory |
| REPO | `$CWD/../.codex/skills` | Shared for nested repositories |
| REPO | `$REPO_ROOT/.codex/skills` | Organization-wide skills |
| USER | `$CODEX_HOME/skills` | Personal cross-project skills |
| ADMIN | `/etc/codex/skills` | System-level for all users |
| SYSTEM | Bundled | Default skills |

Example installs (run from `skills/codex/`):

```bash
# User-level (recommended for trying things out)
cp -r ./development_code_tools/my_skill "$CODEX_HOME/skills/"

# Repo-level (commit to a project)
mkdir -p "$REPO_ROOT/.codex/skills"
cp -r ./development_code_tools/my_skill "$REPO_ROOT/.codex/skills/"
```

## Contributing

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for repository conventions and quality guidelines.

## Official Docs

- Codex Skills Guide: https://developers.openai.com/codex/skills
- Creating Codex Skills: https://developers.openai.com/codex/skills/create-skill
- Main repo README: [README.md](../../README.md)

## Security Note

Only use skills from trusted sources. Skills can run commands and access local files—review `SKILL.md` and any `scripts/` before installing.
