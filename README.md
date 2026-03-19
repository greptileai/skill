# greptile skills

[Agent Skills](https://agentskills.io) for automated PR review workflows. Requires `git` + `gh` CLI.

## Skills

| Skill | Description |
|-------|-------------|
| [`check-pr`](check-pr/) | Check a PR for unresolved comments, failing checks, incomplete description. Fix and resolve. |
| [`greploop`](greploop/) | Loop: trigger Greptile review, fix comments, re-review — until 5/5 confidence and zero comments. |

## Install

```bash
git clone https://github.com/greptileai/skills.git ~/.claude/skills/greptile
cd ~/.claude/skills
ln -s greptile/check-pr check-pr
ln -s greptile/greploop greploop
```

For Codex, use the same layout under `~/.agents/skills`:

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/greptileai/skills.git ~/.agents/skills/greptile
cd ~/.agents/skills
ln -s greptile/check-pr check-pr
ln -s greptile/greploop greploop
```

Or as a submodule:

```bash
git submodule add https://github.com/greptileai/skills.git .skills/greptile
mkdir -p ~/.claude/skills && cd ~/.claude/skills
ln -s /path/to/.skills/greptile/check-pr check-pr
ln -s /path/to/.skills/greptile/greploop greploop

mkdir -p ~/.agents/skills && cd ~/.agents/skills
ln -s /path/to/.skills/greptile/check-pr check-pr
ln -s /path/to/.skills/greptile/greploop greploop
```

Agents discover skills at `~/.claude/skills/<skill-name>/SKILL.md` and `~/.agents/skills/<skill-name>/SKILL.md`. Since this is a multi-skill repo, symlinks are needed to expose each sub-skill at the expected depth.

## Usage

Invoke by name in your agent (e.g. `/check-pr 123` or `/greploop`). If no PR number is given, both skills auto-detect the PR for the current branch.

## License

MIT
