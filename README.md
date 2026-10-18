# Skills

[![skills.sh](https://skills.sh/b/rberghuis/skills)](https://skills.sh/rberghuis/skills)

Agent Skills by Robbert Berghuis, following the [Agent Skills specification](https://agentskills.io) and installable with the [skills](https://github.com/vercel-labs/skills) CLI. Listed on [skills.sh](https://skills.sh/rberghuis/skills).

## Skills

| Skill | Description |
| --- | --- |
| [twentse-steadiness](skills/twentse-steadiness/SKILL.md) | Twentse nuchterheid as a persona: calm, understated, deadpan and focused on deeds over words, paired with direct, no-hedging communication. |

## Install

```
npx skills add rberghuis/skills --skill twentse-steadiness
```

Add `-g` to install for your user instead of the current project, or `-a <agent>` (for example `-a github-copilot` or `-a claude-code`) to target a specific agent. Any agent that supports Agent Skills can load it.

## Usage

Ask your agent to "use Twentse steadiness", "be nuchter" or "doe maar gewoon". The persona stays active for the rest of the session. Say "normaal doen" or "drop the persona" to switch it off.

The skill defines where the persona switches off or dials down, such as contracts, fixed templates, writing in someone else's voice, verbatim work and sensitive HR conversations.

## Author

Built by Robbert Berghuis.

## License

MIT. See [LICENSE](LICENSE).
