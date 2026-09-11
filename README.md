# deepseek-pp-skills

Personal [DeepSeek++](https://github.com/zhu1090093659/deepseek-pp) Skills collection.
Sync across devices via **Skill → GitHub 导入 (GitHub Import)**. No login/token required (public repo).

## Skills

| Trigger | Directory | Description |
|---------|-----------|-------------|
| `/1` | `skills/1` | OPTIMAL EXECUTION PIPELINE (v1) |
| `/q` | `skills/q` | OPTIMAL EXECUTION PIPELINE v2 — improved `/1` with dialectic synthesis |
| `/allthing` | `skills/allthing` | ALLTHING PIPELINE: REASON → DEBATE → EXECUTE → VERIFY |
| `/sisyphus` | `skills/sisyphus` | Autonomous agentic loop for coding / terminal / verification |

## Structure

```
skills/
  1/SKILL.md
  q/SKILL.md
  allthing/SKILL.md
  sisyphus/SKILL.md
```

Each `SKILL.md` carries YAML frontmatter (`name`, `description`) plus the instruction body.
The frontmatter `name` is the trigger: `name: q` → `/q`.

## Usage

In DeepSeek++ sidebar:

1. **Delete existing local custom skills** (to avoid import-collision renaming like `1-2`).
2. Skill → GitHub 导入 → paste `https://github.com/gunlee41/deepseek-pp-skills`
3. Select the skills you want → import (they arrive with clean names: `/1`, `/q`, `/allthing`, `/sisyphus`).
4. Later: Skill → 检查上游更新 (check upstream updates) to pull changes.

## Editing

Server workdir: `/home/gunlee41/deepseek-pp-skills/`. Edit a `SKILL.md`, then:

```bash
git add -A && git commit -m "update" && git push
```
