# Maintaining this repo

This repo publishes Agent Skills through two routes: [skills.sh](https://skills.sh/rberghuis/skills) (`npx skills add`, editable copies) and a plugin marketplace in `.claude-plugin/` (Claude Code, Copilot CLI, VS Code and Codex, which can update themselves).

## Layout

- One folder per skill: `skills/<name>/SKILL.md`. The folder name equals the frontmatter `name`.
- Each skill also has `agents/openai.yaml` with the display name and short description that Codex shows in its skill picker.
- Keep the layout flat. Claude Code, Copilot CLI and Codex load every `skills/<name>/SKILL.md` by default, so `.claude-plugin/plugin.json` has no `skills` list to keep in sync.
- Every skill gets a row in the `README.md` Skills table, with the name linked to its `SKILL.md`.
- The `README.md` Usage section must match the triggers and off-switches in each `SKILL.md`. Re-check it whenever a `SKILL.md` changes.

## Versions and updates

`.claude-plugin/plugin.json` and `marketplace.json` deliberately have no `version`. Without one, Claude Code uses the commit SHA as the version, so every push reaches plugin users. A pinned `version` keeps Claude Code users on the old copy until someone bumps it. Copilot CLI picks up new commits either way (tested on Copilot CLI 1.0.99, 2026-10-18).

`claude plugin validate .` therefore warns about the missing version. That warning is expected, so don't run it with `--strict`.

## Before pushing

```bash
npx skills@latest add . --list                          # skills.sh discovery: lists every skill
pip install skills-ref && agentskills validate skills/<name>  # Agent Skills spec
npx @anthropic-ai/claude-code@latest plugin validate .  # plugin and marketplace manifests
```

## skills.sh

skills.sh has no submission step. A repo is listed after the first `npx skills add rberghuis/skills` with telemetry on, and install counts come from that telemetry. Installs always fetch the current files from GitHub.

The skill pages render a stored snapshot of each skill folder, not GitHub. A push does not update it. An install refreshes it in the background, but not right after the previous snapshot. To update skills.sh after changing a skill:

1. Push to `main`, then wait at least a day after the previous snapshot.
2. Run `npx skills@latest add rberghuis/skills --skill=<name> -y` with telemetry on (no `DISABLE_TELEMETRY` or `DO_NOT_TRACK`).
3. Check the stored copy: `curl https://skills.sh/api/download/rberghuis/skills/<name>`. The page follows within minutes.

Observed on 2026-10-18 and 2026-10-23: installs within two hours of the previous snapshot changed nothing, and an install five days later refreshed the snapshot within about ten minutes. The security audits (`/tele/audit`) were not re-run by that refresh. Repeat installs from the same machine don't raise the install count.

## Writing

No em dashes in this repo's prose. Rewrite the sentence with a comma, colon, period or parentheses instead.
