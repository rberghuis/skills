# Skills

[![skills.sh](https://skills.sh/b/rberghuis/skills)](https://skills.sh/rberghuis/skills)

Agent Skills by Robbert Berghuis. They follow the [Agent Skills specification](https://agentskills.io), so they work in Claude Code, GitHub Copilot, Codex, Cursor and any other agent that reads `SKILL.md`.

## Skills

| Skill | What it does |
| --- | --- |
| [twentse-steadiness](skills/twentse-steadiness/SKILL.md) | Twentse nuchterheid as a persona: calm, understated, deadpan, deeds over words. Risks and bad news are still stated plainly. |

## Install

A plugin install updates itself, or updates with one command. A [skills.sh](https://skills.sh/rberghuis/skills) install copies editable files into your project, and you update them by hand. Pick one route per agent, because installing both gives you every skill twice.

<details>
<summary><strong>GitHub Copilot</strong> (CLI and VS Code)</summary>

```bash
copilot plugin marketplace add rberghuis/skills
copilot plugin install rberghuis-skills@rberghuis
```

To update at every session start, set `autoUpdate` on the marketplace once in `~/.copilot/settings.json`:

```json
{
  "extraKnownMarketplaces": {
    "rberghuis": { "source": { "source": "github", "repo": "rberghuis/skills" }, "autoUpdate": true }
  }
}
```

Without it, run `copilot plugin update rberghuis-skills`. In VS Code, run **Chat: Install Plugin From Source** and enter `https://github.com/rberghuis/skills`.

</details>

<details>
<summary><strong>Claude Code</strong></summary>

```bash
claude plugin install rberghuis-skills --marketplace rberghuis/skills
```

Auto-update is off by default for marketplaces outside Anthropic's own. Turn it on once in `/plugin` under **Marketplaces**, or run `claude plugin update rberghuis-skills@rberghuis`.

</details>

<details>
<summary><strong>Codex</strong></summary>

```bash
codex plugin marketplace add rberghuis/skills
codex plugin add rberghuis-skills@rberghuis
```

To update, run `codex plugin marketplace upgrade rberghuis`.

</details>

<details>
<summary><strong>Any other agent, or editable files</strong> (manual updates)</summary>

```bash
npx skills@latest add rberghuis/skills --skill=twentse-steadiness
```

Add `-a <agent>` (for example `cursor`, `windsurf` or `opencode`) to skip the agent prompt, or `-g` to install for your user instead of the project. To update, run `npx skills@latest update twentse-steadiness`.

</details>

## Usage

Ask your agent to "be nuchter", "use Twentse steadiness" or switch to "Tukker mode". The persona stays on for the rest of the session. Say "drop the persona", "stop Twentse mode" or "persona uit" to switch it off.

The skill switches the persona off for contracts, fixed templates, writing in someone else's voice, verbatim work and sensitive conversations. It tones it down for marketing copy, risk findings, brainstorms, formal audiences and coaching.

## Author

Built by Robbert Berghuis.

## License

MIT. See [LICENSE](LICENSE).
