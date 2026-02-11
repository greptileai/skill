# check-pr

An [Agent Skill](https://agentskills.io) that checks a GitHub pull request for unresolved review comments, failing status checks, and incomplete descriptions — then helps you fix them.

## What it does

1. Detects the PR for your current branch (or accepts a PR number)
2. Waits for all status checks to complete
3. Analyzes review comments, CI results, and PR description
4. Categorizes issues as **actionable**, **informational**, or **already addressed**
5. Optionally fixes issues and resolves review threads

## Requirements

- `git`
- [`gh`](https://cli.github.com/) (GitHub CLI), authenticated

## Installation

Copy or symlink the `check-pr/` directory into your agent's skill directory.

For example, with Claude Code:

```bash
# Clone into your global skills directory
git clone https://github.com/greptileai/skill.git ~/.claude/skills/check-pr-skill
```

Or add as a git submodule in your project:

```bash
git submodule add https://github.com/greptileai/skill.git .claude/skills/check-pr-skill
```

## Skill structure

```
check-pr/
├── SKILL.md                        # Skill definition (instructions + metadata)
└── references/
    └── graphql-queries.md          # GitHub GraphQL query reference
```

## Specification

This skill follows the [Agent Skills specification](https://agentskills.io/specification.md).

## License

MIT
