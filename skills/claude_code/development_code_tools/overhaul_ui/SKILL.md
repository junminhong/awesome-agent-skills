---
name: overhaul-ui
description: Frontend design skill with 28 commands, WCAG 2.2/OKLCH/motion scripts, and coordination logic that detects and defers to specialist design skills. Use for UI audits, redesigns, accessibility checks, and anti-AI-slop craft.
---

# overhaul-ui

**Platforms:** Claude Code | Codex | Cursor | Antigravity | Gemini CLI | Windsurf | OpenCode | Cline | Roo | Amp
**Tags:** frontend-design, ui-ux, anti-slop, wcag-2-2, oklch-color, motion-linting, design-systems
**Use cases:** UI redesigns, accessibility hardening, design system tokens, anti-AI-slop audits, multi-skill coordination

## Objective

Give AI coding agents comprehensive frontend design judgment and real measurement tools (WCAG 2.2 contrast in OKLCH, motion anti-pattern linting, 35 AI-slop rules), while automatically detecting and deferring to installed specialist design skills.

## Inputs

- **Task/Prompt**: UI design, redesign, token creation, or audit request.
- **Codebase**: React, Vue, Svelte, Astro, React Native, HTML/CSS frontend code.
- **Installed Skills**: Auto-detected companion design skills (e.g. animation, taste skills).

## Outputs

- **Redesigned/Styled UI**: Component code adhering to anti-slop craft and hard visual boundaries.
- **Design Tokens**: Structured token definitions (OKLCH color ramps, spacing scales, typography scales).
- **Audit Reports**: Real computed metrics for WCAG 2.2 contrast, motion anti-patterns, and slop rules.

## Workflow

1. **Stack & Companion Detection**: Identifies framework/CSS setup and checks for existing specialist skills.
2. **Command Routing**: Maps user request to 1 of 28 specialized command workflows.
3. **Execution & Measurement**: Runs zero-dependency Node scripts for contrast, color math, and static linting.
4. **Specialist Deferral**: Hands off specific sub-tasks (e.g. specialized motion philosophy) if companion skills are present.
5. **Quality Gating**: Evaluates output against a pre-delivery checklist before presenting to the user.

## Constraints & Guardrails

- **Scope**: Frontend only — strictly out of scope for backend APIs, database schemas, or infrastructure.
- **Dependencies**: Zero runtime dependencies. Runs offline.
- **Honest Metrics**: Reports static a11y coverage limits (~30-40% of real WCAG criteria) explicitly without overclaiming compliance.

## Examples

### Example 1: UI Slop Audit

**Input:**
```bash
overhaul-ui scan
```

**Expected Output:**
```text
[overhaul-ui] Audit summary:
- 3 WCAG 2.2 AA contrast failures detected (computed in OKLCH)
- 2 motion anti-patterns flagged (ease-in transition on entrance element)
- 4 AI-slop visual patterns identified (untinted neutral grey #888, purple-blue gradient header)
```

## Evaluation Checklist

- [x] **Correctness**: Computes exact contrast ratios using OKLCH color math
- [x] **Completeness**: Covers 17 reference disciplines and 8 surface playbooks
- [x] **Safety**: Zero external runtime network calls; runs fully offline
- [x] **Reproducibility**: Identical linting output across all 13 supported AI coding agents
- [x] **Documentation**: Complete reference chapters and command specs included

## References

- [overhaul-ui Repository](https://github.com/ShadowFull12/overhaul-ui)
- [W3C WCAG 2.2 Guidelines](https://www.w3.org/TR/WCAG22/)
- [OKLCH Color Space Specification](https://oklch.com/)

## Version History

- **v1.0.0** (2026-07-28): Initial release with 28 commands, 17 reference domains, and 7 offline measurement scripts.
