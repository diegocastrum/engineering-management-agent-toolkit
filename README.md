# Engineering Management Agent Toolkit

Organization toolkit for reusable agent capabilities focused on engineering management and team leadership.

This repository collects Claude Code and Codex plugins, skills, and supporting metadata that can be shared across projects. Skills are derived from complementary sources: James Stanier's *Become an Effective Software Engineering Manager* (tactical — what to do Monday morning), Camille Fournier's *The Manager's Path* (strategic — career arcs and management progression), and selected pieces from Niels Horeman's *Leadership Essentials* series (cross-cutting disciplines such as agreements vs. expectations). Where multiple sources cover the same topic, their treatments have been synthesized into single skills so you load one skill per topic rather than several.

## Layout

```text
.claude-plugin/
  marketplace.json
.agents/
  plugins/
    marketplace.json
plugins/
  engineering-management/
    .claude-plugin/plugin.json
    .codex-plugin/plugin.json
    assets/kubicum.png
    skills/
      first-week-snapshot/
      manager-toolkit/
      one-on-ones/
      motivation-and-fit/
      feedback-and-reviews/
      hiring-and-interviewing/
      project-breakdown/
      team-health/
      hard-conversations/
      stress-and-pressure/
      information-and-politics/
      letting-go-and-self-care/
      career-growth/
      agreements-not-expectations/
    skill-examples.md
skills.json
README.md
```

## Plugin

| Plugin | Purpose |
| --- | --- |
| `engineering-management` | Skills for engineering managers and team leads — tactical day-to-day mechanics, longer-arc work, and cross-cutting disciplines. Derived from Stanier's *Become an Effective Software Engineering Manager*, Fournier's *The Manager's Path*, and Horeman's *Leadership Essentials* series. |

## Skills Catalog

[skills.json](skills.json) lists the currently available skills and their paths inside this toolkit.

| Skill | When it triggers |
| --- | --- |
| `first-week-snapshot` | First weeks as a new manager: three-view Venn diagram, week-1 action list |
| `manager-toolkit` | Self-organization: calendar, to-do, email, capture; Grove's activity categories and the output equation |
| `one-on-ones` | Contracting with new reports, rolling agenda, the five 1-1 styles, prep/reflect/diagnose modes, Andon Cord, "you are not a therapist" |
| `motivation-and-fit` | Maslow at work, zone of proximal development, skill trees, cathedral-vs-bazaar motivation profiles |
| `feedback-and-reviews` | Continuous feedback and 6-month reviews: in-the-moment delivery, tracker spreadsheet, peer feedback email, bias traps, written-first form, decoupling pay from review, PIPs |
| `hiring-and-interviewing` | Who-to-hire mindset, JD template and gender-neutral writing, 6-stage engineer funnel and 8-step manager loop, take-home rules, debrief and decision, reference checks, culture-fit done right, calibration diagnostics |
| `project-breakdown` | Multi-week project planning, estimation, scope cuts as deadlines approach, premortems |
| `team-health` | Proactive housekeeping (Conway's Law, guilds, lightning talks, five whys, management bugs, ADRs, health checks, DRIs) and reactive debugging (shipping problems, drama, attrition, low energy, brilliant jerk) |
| `hard-conversations` | PIPs, coaching out, saying no upward, behavior correction, bad news at scale |
| `stress-and-pressure` | Eye of Sauron, MoSCoW prioritization, scope/resources/time levers, Brooks's Law, Mount Stupid, imposter syndrome |
| `information-and-politics` | Spies vs gatekeepers, three categories of information, leave-nobody-behind, disagree and commit |
| `letting-go-and-self-care` | Stoic trichotomy of control, internal vs external goals, L-mode/R-mode, 85% capacity, sleep, movement, breathing |
| `career-growth` | Promotions, growth plans, ladder design, IC vs management decisions, plus the once-a-year vision exercise (10-year past/future timeline, vision and plan statements, skills backlog) |
| `agreements-not-expectations` | Turning unspoken expectations into explicit, mutual, voluntary agreements: the five principles, the out-of-agreement script, entry conditions, and the systems-beat-willpower rule |

Each skill loads itself when the agent detects the relevant context in your conversation — you don't have to invoke them by name.

## Install Plugin for Claude Code

Add this repository as a Claude Code plugin marketplace:

```bash
claude plugin marketplace add git@github.com:diegocastrum/engineering-management-agent-toolkit.git
```

Then install `engineering-management` from the added marketplace.

For a home-local plugin install without Git, copy or symlink the plugin under your local Claude plugin directory:

```bash
mkdir -p "$HOME/.claude/plugins"
cp -R plugins/engineering-management "$HOME/.claude/plugins/"
```

## Install Plugin for Codex

Add this repository as a Codex plugin marketplace:

```bash
codex plugin marketplace add git@github.com:diegocastrum/engineering-management-agent-toolkit.git
```

Then install `engineering-management` from the added marketplace.

For a home-local plugin install without Git, copy or symlink the plugin under your local Codex plugin directory:

```bash
mkdir -p "$HOME/plugins"
cp -R plugins/engineering-management "$HOME/plugins/"
```

Then reference it from `~/.agents/plugins/marketplace.json` with:

```json
{
  "plugins": [
    {
      "name": "engineering-management",
      "source": {
        "source": "local",
        "path": "./plugins/engineering-management"
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
cp -R plugins/engineering-management/skills/one-on-ones "$HOME/.claude/skills/"
```

To install every skill manually:

```bash
mkdir -p "$HOME/.claude/skills"
cp -R plugins/engineering-management/skills/* "$HOME/.claude/skills/"
```

Restart Claude Code (or start a new session) and the skills will be available.

### Codex

To install a single skill manually into Codex:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R plugins/engineering-management/skills/one-on-ones "${CODEX_HOME:-$HOME/.codex}/skills/"
```

To install every skill manually:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R plugins/engineering-management/skills/* "${CODEX_HOME:-$HOME/.codex}/skills/"
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

→ Triggers `team-health` (brilliant jerk pattern) and `hard-conversations` (behavior correction).

You can also be direct: "Use the project-breakdown skill to break down the speakseeproxy auth refactor."

See [plugins/engineering-management/skill-examples.md](plugins/engineering-management/skill-examples.md) for more trigger examples per skill.

## Validate

Validate JSON metadata:

```bash
python3 -m json.tool .claude-plugin/marketplace.json
python3 -m json.tool .agents/plugins/marketplace.json
python3 -m json.tool plugins/engineering-management/.claude-plugin/plugin.json
python3 -m json.tool plugins/engineering-management/.codex-plugin/plugin.json
python3 -m json.tool skills.json
```

## Iterating

These skills are first drafts. After a week or two of real use, you'll notice:

- Skills that under-trigger (the agent doesn't use them when you wanted) → tighten the `description` line, add more trigger phrases
- Skills that over-trigger (the agent pulls them in for unrelated things) → narrow the `description`
- Patterns that aren't covered → add a new section to the relevant skill, or split out a new skill
- Forcing functions that aren't pushing back enough → strengthen the "if X, then push back" rules in the skill body

Edit the `SKILL.md` files directly, reload the agent, and you're done. No build step.

## Sources

The skills are grounded in a few sources, often within a single skill:

- *Become an Effective Software Engineering Manager: How to Be the Leader Your Development Team Needs* by James Stanier (Pragmatic Bookshelf, 2020) — which in turn draws on Andy Grove's *High Output Management*, Maslow, Vygotsky, Raymond's *The Cathedral and the Bazaar*, Scott's *Radical Candor*, the Spotify engineering blog (squads/tribes/chapters/guilds), Apple (DRIs), Stoic philosophy (Epictetus, Irvine), Kabat-Zinn (mindfulness), Hunt's *Pragmatic Thinking and Learning* (L-mode/R-mode), Walker's *Why We Sleep*, Brooks's *The Mythical Man-Month*, and Csíkszentmihályi (flow).
- *The Manager's Path: A Guide for Tech Leaders Navigating Growth and Change* by Camille Fournier (O'Reilly, 2017).
- *Leadership Essentials* series by Niels Horeman, including *From Assumptions to Agreements* and the companion *Playbook — Creating and Honoring Agreements*.

Section references and inline attributions are in the body of each skill so you can cross-check against the source when you want to.
