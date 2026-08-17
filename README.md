# Awesome Agent Skills

<p align="center">
  <img src="assets/logo.png" alt="Awesome Agent Skills" width="700" />
</p>

<p align="center">
  <a href="https://awesome.re">
    <img src="https://awesome.re/badge.svg" alt="Awesome" />
  </a>
  <a href="CONTRIBUTING.md">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" alt="PRs Welcome" />
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square" alt="License: MIT" />
  </a>
</p>

<p align="center">
  <a href="README.md">English</a> | <a href="README_ZH.md">繁體中文</a>
</p>

A curated directory of externally maintained Agent Skills, skill collections, and supporting tools for AI-agent workflows.

> [!IMPORTANT]
> This is a links-only directory. Skills stay in their source repositories. Listing pull requests must not add `SKILL.md`, scripts, copied skill folders, or platform-specific indexes to this repository.

## Scope

This directory includes:

- **Agent Skills** — directly usable, reusable instruction packages with a public implementation.
- **Skill Collections** — repositories containing multiple usable Agent Skills.
- **Tooling & Integrations** — plugins, CLIs, MCP integrations, and related projects built for agent workflows.

This repository is not a package registry, a host for community skill files, a security audit, or an endorsement of the linked projects. Each entry remains maintained and licensed by its upstream owner.

## Browse

### Agent Skills

#### Development & Code

- [UIZZE anti-ui-slop](https://github.com/uizze/uizze/tree/main/skills/anti-ui-slop) — Builds a product-specific UI design contract and applies a pre-ship finish gate using real interface references. `Type: Skill` · `Platforms: Cross-platform`

#### Data & Analysis

- [credit-risk-model](https://github.com/W-Y-P/credit-risk-model) — Guides credit-risk model development, validation, reporting, and strategy analysis. `Type: Skill` · `Platforms: Cross-platform`
- [Xquik x-twitter-scraper](https://github.com/Xquik-dev/x-twitter-scraper) — Routes X research, extraction, monitoring, and confirmation-gated publishing through REST, MCP, SDK, or webhook workflows. `Type: Skill` · `Platforms: Cross-platform`

#### Communication & Writing

- [essay-writer](https://github.com/shimellism-eng/essay-writer-editor/tree/main/skills/essay-writer) — Plans, drafts, researches, edits, and reviews essays while preserving voice, evidence, and uncertainty. `Type: Skill` · `Platforms: Codex, Agent Skills-compatible agents`

#### Creative & Media

- [runapi-cli-skill](https://github.com/runapi-ai/cli-skill) — Teaches agents to run image, video, audio, and language-model jobs through the RunAPI CLI. `Type: Skill` · `Platforms: Cross-platform`

#### Productivity & Organization

- [wiki](https://github.com/plasma-ai/wiki/tree/main/wiki/skills/wiki) — Creates and queries indexed Markdown knowledge bases with deterministic CLI support for agents. `Type: Skill` · `Platforms: Codex, Claude Code`

### Skill Collections

- [Code2Skill](https://github.com/leechen298/Code2Skill) — Turns authorized application source code into runnable Function, MCP tool, workflow Skill, and offline-test packages, with separate flow and source review skills. `Type: Collection` · `Platforms: Codex, Claude Code, Kimi Code`
- [OrkasVideoStudio](https://github.com/Orkas-AI/Orkas-VideoStudio/tree/main/packages/skills) — Routes coding agents through 14 skills for planning, composing, editing, generating, and assembling videos. `Type: Collection` · `Platforms: Codex, Claude Code`
- [Suede Creator Skills](https://github.com/JasonColapietro/suede-creator-skills) — A multi-domain collection covering agent orchestration, code review, evaluation, product, design, and growth workflows. `Type: Collection` · `Platforms: Cross-platform`

### Tooling & Integrations

- [Agent QA](https://github.com/vostride/agent-qa) — Runs natural-language web and mobile QA workflows through a CLI, MCP server, and three evidence-oriented Agent Skills. `Type: CLI + MCP + Collection` · `Platforms: Codex, Agent Skills-compatible agents`
- [TweetClaw](https://github.com/Xquik-dev/tweetclaw) — Provides supervised X research, publishing, media, follower export, giveaway, and monitoring workflows. `Type: Plugin + Skill` · `Platforms: OpenClaw, Agent Skills-compatible agents`

## Using a Listed Project

1. Open the linked canonical source and read its current documentation.
2. Review its `SKILL.md`, scripts, dependencies, requested permissions, and external services before use.
3. Follow the upstream installation instructions for your agent platform.
4. Confirm that its license, platform support, data handling, and security assumptions fit your environment.

Compatibility and availability can change; the upstream repository is the source of truth.

## Contributing

For a normal listing pull request:

1. Add or update one upstream project in the appropriate section.
2. Edit **both** `README.md` and `README_ZH.md`, keeping the name, URL, type, and platform metadata in sync.
3. Change only those two files; do not vendor the upstream skill into this repository.

Entry format:

```markdown
- [Project name](canonical public source) — One concise, factual description. `Type: Skill` · `Platforms: Cross-platform`
```

Read [CONTRIBUTING.md](CONTRIBUTING.md) for eligibility, ordering, disclosure, pull-request scope, and commit-signing requirements.

## References

- [Agent Skills specification](https://agentskills.io/)
- [Build skills with Codex](https://learn.chatgpt.com/docs/build-skills)
- [Extend Claude with skills](https://code.claude.com/docs/en/skills)

## License and Disclaimer

The documentation and assets in this repository are available under the [MIT License](LICENSE). Linked projects use their own licenses and terms. Inclusion does not imply endorsement, compatibility guarantees, or security review.
