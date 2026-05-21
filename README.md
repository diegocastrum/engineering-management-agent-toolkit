# Engineering Leadership Agent Toolkit

Organization toolkit for reusable agent capabilities focused on engineering team leadership.

This repository collects Claude Code and Codex plugins, skills, and supporting metadata that can be shared across projects. Skills are derived from two complementary sources: Camille Fournier's *The Manager's Path* (strategic — career arcs and management progression) and James Stanier's *Become an Effective Software Engineering Manager* (tactical — what to do Monday morning). They overlap on a few topics (1-1s, hiring, reviews) but emphasize different things — install both and they cover different muscle groups.

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
  effective-manager/
    .claude-plugin/plugin.json
    .codex-plugin/plugin.json
    assets/kubicum.png
    skills/
      career-vision-exercise/
      first-week-snapshot/
      hiring-stanier/
      information-and-politics/
      letting-go-and-self-care/
      manager-toolkit/
      motivation-and-fit/
      one-to-ones-stanier/
      performance-reviews-stanier/
      stress-and-pressure/
      team-housekeeping/
    skill-examples.md
skills.json
README.md
```

## Plugins

| Plugin | Purpose |
| --- | --- |
| `engineering-leadership` | 1-1s, feedback and reviews, project breakdown, team health, hard conversations, hiring, and career growth. Derived from Fournier's *The Manager's Path*. |
| `effective-manager` | First-week snapshot, manager toolkit, 1-1s with contracting, performance reviews, hiring funnels, motivation and fit, stress and pressure, information and politics, self-care, team housekeeping, and the 10-year career vision exercise. Derived from Stanier's *Become an Effective Software Engineering Manager*. |

## Skills Catalog

[skills.json](skills.json) lists the currently available skills and their paths inside this toolkit.

### `engineering-leadership` (Fournier)

| Skill | When it triggers |
| --- | --- |
| `one-on-ones` | Prepping 1-1s, reflecting on them, diagnosing when they feel off, onboarding new reports |
| `feedback-and-reviews` | Giving feedback (in the moment or written), performance reviews, the no-surprises rule |
| `project-breakdown` | Multi-week project planning, estimation, scope cuts as deadlines approach, premortems |
| `team-health-debugger` | Team feels off, shipping problems, drama, attrition, low energy, conflict |
| `hard-conversations` | PIPs, coaching out, saying no upward, behavior correction, bad news at scale |
| `hiring-and-interviewing` | Loop design, JDs, debriefs, references, calibration, culture fit done right |
| `career-growth` | Promotions, growth plans, ladder design, IC vs management decisions |

### `effective-manager` (Stanier)

| Skill | When it triggers |
| --- | --- |
| `first-week-snapshot` | First weeks as a new manager: three-view Venn diagram, week-1 action list |
| `manager-toolkit` | Self-organization: calendar, to-do, email, capture; Grove's activity categories and the output equation |
| `one-to-ones-stanier` | Contracting with new reports, rolling agenda, 70% rule, silence, Andon Cord, "you are not a therapist" |
| `motivation-and-fit` | Maslow at work, zone of proximal development, skill trees, cathedral-vs-bazaar motivation profiles |
| `performance-reviews-stanier` | 6-month cadence, tracker spreadsheet, peer feedback email, written-first form, decoupling pay from review |
| `hiring-stanier` | Who-to-hire mindset, JD template, gender-neutral writing, 6-stage funnel, take-home rules |
| `stress-and-pressure` | Eye of Sauron, MoSCoW prioritization, scope/resources/time levers, Brooks's Law, Mount Stupid, imposter syndrome |
| `information-and-politics` | Spies vs gatekeepers, three categories of information, leave-nobody-behind, disagree and commit |
| `letting-go-and-self-care` | Stoic trichotomy of control, internal vs external goals, L-mode/R-mode, 85% capacity, sleep, movement, breathing |
| `team-housekeeping` | Conway's Law, guilds, lightning talks, five whys, management bugs, ADRs, team health checks, DRIs |
| `career-vision-exercise` | 10-year past/future timeline, vision statement, plan statement, skills backlog — delivered as coaching sessions |

Each skill loads itself when the agent detects the relevant context in your conversation — you don't have to invoke them by name.

## Install Plugin for Claude Code

Add this repository as a Claude Code plugin marketplace:

```bash
claude plugin marketplace add git@github.com:diegocastrum/engineering-leadership-agent-toolkit.git
```

Then install `engineering-leadership` and/or `effective-manager` from the added marketplace.

For a home-local plugin install without Git, copy or symlink the plugins under your local Claude plugin directory:

```bash
mkdir -p "$HOME/.claude/plugins"
cp -R plugins/engineering-leadership "$HOME/.claude/plugins/"
cp -R plugins/effective-manager "$HOME/.claude/plugins/"
```

## Install Plugin for Codex

Add this repository as a Codex plugin marketplace:

```bash
codex plugin marketplace add git@github.com:diegocastrum/engineering-leadership-agent-toolkit.git
```

Then install `engineering-leadership` and/or `effective-manager` from the added marketplace.

For a home-local plugin install without Git, copy or symlink the plugins under your local Codex plugin directory:

```bash
mkdir -p "$HOME/plugins"
cp -R plugins/engineering-leadership "$HOME/plugins/"
cp -R plugins/effective-manager "$HOME/plugins/"
```

Then reference them from `~/.agents/plugins/marketplace.json` with:

```json
{
  "plugins": [
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
    },
    {
      "name": "effective-manager",
      "source": {
        "source": "local",
        "path": "./plugins/effective-manager"
      },
      "policy": {
        "installation": "AVAILABLE",
        "authentication": "ON_INSTALL"
      },
      "category": "Productivity"
    }
  ]
}
```

## Install Individual Skills

### Claude Code

To install a single skill manually into Claude Code:

```bash
mkdir -p "$HOME/.claude/skills"
cp -R plugins/engineering-leadership/skills/one-on-ones "$HOME/.claude/skills/"
```

To install every skill manually (from both plugins):

```bash
mkdir -p "$HOME/.claude/skills"
cp -R plugins/engineering-leadership/skills/* "$HOME/.claude/skills/"
cp -R plugins/effective-manager/skills/* "$HOME/.claude/skills/"
```

Restart Claude Code (or start a new session) and the skills will be available.

### Codex

To install a single skill manually into Codex:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R plugins/engineering-leadership/skills/one-on-ones "${CODEX_HOME:-$HOME/.codex}/skills/"
```

To install every skill manually (from both plugins):

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R plugins/engineering-leadership/skills/* "${CODEX_HOME:-$HOME/.codex}/skills/"
cp -R plugins/effective-manager/skills/* "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Restart Codex if newly copied skills do not appear.

## How to use the skills

The skills support three modes:

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

See [plugins/engineering-leadership/skill-examples.md](plugins/engineering-leadership/skill-examples.md) and [plugins/effective-manager/skill-examples.md](plugins/effective-manager/skill-examples.md) for more trigger examples per skill.

## Validate

Validate JSON metadata:

```bash
python3 -m json.tool .claude-plugin/marketplace.json
python3 -m json.tool .agents/plugins/marketplace.json
python3 -m json.tool plugins/engineering-leadership/.claude-plugin/plugin.json
python3 -m json.tool plugins/engineering-leadership/.codex-plugin/plugin.json
python3 -m json.tool plugins/effective-manager/.claude-plugin/plugin.json
python3 -m json.tool plugins/effective-manager/.codex-plugin/plugin.json
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

The `engineering-leadership` skills are grounded in *The Manager's Path: A Guide for Tech Leaders Navigating Growth and Change* by Camille Fournier (O'Reilly, 2017).

The `effective-manager` skills are grounded in *Become an Effective Software Engineering Manager: How to Be the Leader Your Development Team Needs* by James Stanier (Pragmatic Bookshelf, 2020), which in turn draws on Andy Grove's *High Output Management*, Maslow, Vygotsky, Raymond's *The Cathedral and the Bazaar*, Scott's *Radical Candor*, the Spotify engineering blog (squads/tribes/chapters/guilds), Apple (DRIs), Stoic philosophy (Epictetus, Irvine), Kabat-Zinn (mindfulness), Hunt's *Pragmatic Thinking and Learning* (L-mode/R-mode), Walker's *Why We Sleep*, Brooks's *The Mythical Man-Month*, and Csíkszentmihályi (flow).

Section references are in the body of each skill so you can cross-check against the source when you want to.
