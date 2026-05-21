# Engineering Leadership Agent Toolkit

Organization toolkit for reusable agent capabilities focused on engineering team leadership.

This repository collects Claude Code and Codex plugins, skills, and supporting metadata that can be shared across projects. Skills are derived from Camille Fournier's *The Manager's Path* — they capture the non-obvious patterns and forcing functions of the book so the agent responds in Fournier's frame rather than generic management mush.

## Layout

```text
.claude-plugin/
  marketplace.json
.agents/
  plugins/
    marketplace.json
plugins/
  engineering-leadership/
    .claude-plugin/plugin.json
    .codex-plugin/plugin.json
    assets/kubicum.png
    skills/
      career-growth/
      feedback-and-reviews/
      hard-conversations/
      hiring-and-interviewing/
      one-on-ones/
      project-breakdown/
      team-health-debugger/
    skill-examples.md
skills.json
README.md
```

## Plugins

| Plugin | Purpose |
| --- | --- |
| `engineering-leadership` | 1-1s, feedback and reviews, project breakdown, team health, hard conversations, hiring, and career growth. |

## Skills Catalog

[skills.json](skills.json) lists the currently available skills and their paths inside this toolkit.

| Skill | When it triggers |
| --- | --- |
| `one-on-ones` | Prepping 1-1s, reflecting on them, diagnosing when they feel off, onboarding new reports |
| `feedback-and-reviews` | Giving feedback (in the moment or written), performance reviews, the no-surprises rule |
| `project-breakdown` | Multi-week project planning, estimation, scope cuts as deadlines approach, premortems |
| `team-health-debugger` | Team feels off, shipping problems, drama, attrition, low energy, conflict |
| `hard-conversations` | PIPs, coaching out, saying no upward, behavior correction, bad news at scale |
| `hiring-and-interviewing` | Loop design, JDs, debriefs, references, calibration, culture fit done right |
| `career-growth` | Promotions, growth plans, ladder design, IC vs management decisions |

Each skill loads itself when the agent detects the relevant context in your conversation — you don't have to invoke them by name.

## Install Plugin for Claude Code

Add this repository as a Claude Code plugin marketplace:

```bash
claude plugin marketplace add git@github.com:diegocastrum/engineering-leadership-agent-toolkit.git
```

Then install `engineering-leadership` from the added marketplace.

For a home-local plugin install without Git, copy or symlink this plugin under your local Claude plugin directory:

```bash
mkdir -p "$HOME/.claude/plugins"
cp -R plugins/engineering-leadership "$HOME/.claude/plugins/"
```

## Install Plugin for Codex

Add this repository as a Codex plugin marketplace:

```bash
codex plugin marketplace add git@github.com:diegocastrum/engineering-leadership-agent-toolkit.git
```

Then install `engineering-leadership` from the added marketplace.

For a home-local plugin install without Git, copy or symlink this plugin under your local Codex plugin directory:

```bash
mkdir -p "$HOME/plugins"
cp -R plugins/engineering-leadership "$HOME/plugins/"
```

Then reference it from `~/.agents/plugins/marketplace.json` with:

```json
{
  "name": "engineering-leadership",
  "source": {
    "source": "local",
    "path": "./plugins/engineering-leadership"
  },
  "policy": {
    "installation": "AVAILABLE",
    "authentication": "ON_INSTALL"
  },
  "category": "Productivity"
}
```

## Install Individual Skills

### Claude Code

To install a single skill manually into Claude Code:

```bash
mkdir -p "$HOME/.claude/skills"
cp -R plugins/engineering-leadership/skills/one-on-ones "$HOME/.claude/skills/"
```

To install every skill manually:

```bash
mkdir -p "$HOME/.claude/skills"
cp -R plugins/engineering-leadership/skills/* "$HOME/.claude/skills/"
```

Restart Claude Code (or start a new session) and the skills will be available.

### Codex

To install a single skill manually into Codex:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R plugins/engineering-leadership/skills/one-on-ones "${CODEX_HOME:-$HOME/.codex}/skills/"
```

To install every skill manually:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R plugins/engineering-leadership/skills/* "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Restart Codex if newly copied skills do not appear.

## How to use the skills

The skills support three modes Fournier-style:

**Prep before a meeting**

```
> I have a 1-1 with Sarah tomorrow. She's been quiet in standups for two weeks. Help me prep.
```

→ Triggers `one-on-ones`, walks through prep mode, surfaces the warning signs.

**Reflect after a meeting**

```
> Just finished my 1-1 with Sarah. Notes below — what should I follow up on?
  [notes]
```

→ Triggers `one-on-ones` in reflect mode, extracts action items, flags patterns.

**On-demand coaching**

```
> I have a senior engineer who keeps railroading discussions in design reviews. Other engineers are going quiet. What do I do?
```

→ Triggers `team-health-debugger` (brilliant jerk pattern) and `hard-conversations` (behavior correction).

You can also be direct: "Use the project-breakdown skill to break down the speakseeproxy auth refactor."

See [plugins/engineering-leadership/skill-examples.md](plugins/engineering-leadership/skill-examples.md) for more trigger examples per skill.

## Validate

Validate JSON metadata:

```bash
python3 -m json.tool .claude-plugin/marketplace.json
python3 -m json.tool .agents/plugins/marketplace.json
python3 -m json.tool plugins/engineering-leadership/.claude-plugin/plugin.json
python3 -m json.tool plugins/engineering-leadership/.codex-plugin/plugin.json
python3 -m json.tool skills.json
```

## Iterating

These skills are first drafts. After a week or two of real use, you'll notice:

- Skills that under-trigger (the agent doesn't use them when you wanted) → tighten the `description` line, add more trigger phrases
- Skills that over-trigger (the agent pulls them in for unrelated things) → narrow the `description`
- Patterns that aren't covered → add a new section to the relevant skill, or split out a new skill
- Forcing functions that aren't pushing back enough → strengthen the "if X, then push back" rules in the skill body

Edit the `SKILL.md` files directly, reload the agent, and you're done. No build step.

## Source

All seven skills are grounded in *The Manager's Path: A Guide for Tech Leaders Navigating Growth and Change* by Camille Fournier (O'Reilly, 2017). Section references are in the body of each skill so you can cross-check against the source when you want to.
