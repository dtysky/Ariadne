# Ariadne Agents Guide

## 1. Canonical Source Directories

- `skills/`: all Ariadne skill prompts (single source of truth)
- `rules/`: all Ariadne project rules (single source of truth)
- `knowledge/`: shared theory and report templates

## 2. Compatibility Links

- `.cursor/skills -> ../skills`
- `.cursor/rules -> ../rules`
- `.codex/skills -> ../skills`
- `.codex/rules -> ../rules`

These links keep Cursor/Codex workspace conventions compatible while avoiding duplicated prompt files.

## 3. Suggested Agent Workflow

1. Interview phase: load `skills/interview.skill.md` as the system prompt.
2. Report phase: load `skills/report.skill.md` and provide full interview transcript.
3. Match phase: load `skills/match.skill.md` and provide two generated reports.

## 4. Shared Knowledge Inputs

All agents should use:

- `knowledge/framework.md`
- `knowledge/dimensions.md`
- `knowledge/report-template.md`

## 5. Output Conventions

- Personal report: `output/report-{name}.md`
- Match report: `output/match-{A}-{B}.md`
