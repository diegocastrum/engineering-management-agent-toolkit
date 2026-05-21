---
name: project-breakdown
description: Use whenever the user is planning a multi-week engineering project, breaking down a big initiative into deliverables, estimating timelines for leadership, deciding what to cut as a deadline approaches, or running a premortem. Triggers on phrases like "estimate this project", "break this down", "project plan", "how long will X take", "we have a deadline", "what should we cut", "premortem", "scope cut", "milestone", "deliverable", "Q1/Q2/Q3/Q4 planning". Also use when the user mentions a project that's slipping and they need to figure out what to do.
---

# Project Breakdown and Estimation

Source: Camille Fournier, *The Manager's Path*, chapters 3 and 5 ("Managing a Project", "Advanced Project Management").

Project planning is tedious and few engineers enjoy it, but Fournier's argument is sharp: the value isn't perfect prediction, it's the *discipline of thinking about the project before diving in*. Plans will be wrong. Plans are still essential.

## When this skill is loaded, identify the situation

- **Fresh planning** — new project, nothing broken down yet.
- **Estimation request** — leadership wants a number; how do we give one we can defend?
- **Mid-flight check** — project is in progress; how are we tracking? what's at risk?
- **Scope-cut mode** — deadline is real and we won't make it as scoped; what comes out?
- **Premortem** — project is launching soon; what could fail?

Ask if it's not clear. Then proceed.

## Fresh planning: the five-step rhythm

Fournier's exact sequence from chapter 3. Don't skip steps, especially not step 2.

### 1. Break down the work

Start with the biggest pieces. Then break those into smaller pieces. Then again. You don't have to do it all yourself — pull in the people who know the system best. But *you* have to drive it; you can't outsource the discipline of thinking the project through.

Help the user produce a hierarchy:
- **Epics / milestones** (deliverables measured in weeks)
- **Tasks** (1–5 days of work each)
- **Ticket-sized work** (what an engineer can pick up and finish)

Identify what can start immediately. Hand those off; don't wait for the full plan.

### 2. Push through the details and unknowns

This is the step everyone wants to skip. It's tedious. Do it anyway.

For every milestone, force these questions:
- What does "done" look like — concretely? What test or demo proves it?
- What does this depend on? (Other teams, other services, external vendors, hardware.)
- What's the riskiest unknown? Can we de-risk it early with a spike?
- What can run in parallel? What absolutely must run in sequence?
- What's the integration / testing / deployment story? (Often the biggest underestimate.)

If you feel stuck or bored — Fournier says push through anyway. Stopping when it gets tedious is how plans become useless.

### 3. Run the project and adjust

Once running:
- Track against milestones, not against hours.
- Communicate slippage early — to your manager, to the product manager, to stakeholders.
- The plan is a baseline for honest status, not a contract.

### 4. Handle requirements changes with the insights from planning

When requirements change mid-flight, don't just absorb the change. Use what you learned during planning to articulate the cost:
- This adds X risk because [dependency]
- This pushes the date by Y because [critical path]
- To absorb this without slipping, we'd need to cut Z

Make the trade-off visible. Don't quietly eat scope.

### 5. Revisit details near completion (premortem)

When the project is close to launch, the tedium returns. Attend to it.

Run a premortem: imagine the launch failed spectacularly — why? Generate a list, then prioritize. Decide where the "good enough" line is, socialize it with the team, commit to it. Cut anything below the line. Make a launch plan. Make a rollback plan.

## Estimation requests

When someone asks "how long will this take?", the answer depends on how settled the project is.

### The doubling rule

For off-the-cuff guesses: take your gut estimate, double it. This is fine for casual conversations and Slack questions.

### The "I need to plan first" rule

For anything that might take more than a couple of weeks, double the estimate **and** make clear you need real planning time before committing. Sometimes long projects take 5x your gut, not 2x, and you need the planning step to know which.

### Per-engineer capacity

**10 productive engineering weeks per engineer per quarter.** Not 13. Account for:
- Vacations, holidays, sick days
- Meetings, planning sessions, review periods
- Production incidents and on-call
- Onboarding new team members
- Interview load

Q1 is usually most productive. Q4 (year-end holidays) is least.

If a stakeholder pushes back on this number, the question isn't "can your team work harder?" — it's "which of these things would you like us to stop doing?"

### Reserve 20% for sustaining engineering

Refactoring, fixing outstanding bugs, language/platform upgrades, ongoing support. If you plan to 100% feature work, feature work slows down within a quarter because the foundation rots. Bake the 20% in from the start.

## Mid-flight check

When checking on a project in progress:

- **Are milestones being hit?** If yes, light touch. If no, where's the slippage?
- **Is there hidden work?** Look at version control, ticket churn, and chat. Bugs piling up that aren't on the plan? Refactoring expanding into a rewrite? Scope creep from product?
- **Is anyone struggling silently?** Use 1-1s, not the project plan. Plans don't tell you when an engineer is stuck.
- **What's the riskiest unfinished part?** Pull that forward. Late risks become late surprises.

## Scope-cut mode

The most important rule: as a deadline approaches, **the manager's job is to say no**.

When the deadline is fixed and the scope won't fit:

1. **List every must-have feature** with the product manager / business stakeholder. Make them order it.
2. **List every technical must-have** with the tech lead. (Required for the feature to ship safely vs. nice-to-have engineering work.)
3. **Find the compromise:**
   - Cut product features that aren't core to the value proposition
   - Push technical nice-to-haves to the next cycle
   - Find hack implementations for must-have features where the proper implementation can wait
4. **Get explicit agreement** on what's in and what's out. In writing. From the people who'll be upset later.

What you give on matters. If you only give on technical quality, you slow down the team after launch. If you only give on product features, you may ship something users don't want. Cut from both sides.

## Premortem template

Run this 2–4 weeks before a planned launch. Get the team in a room (or doc) and generate answers to:

```
Imagine it's [launch date + 2 weeks]. The launch failed.
What are the top 10 reasons it could have failed?
```

Cluster the answers. For each cluster:
- **How likely?** (low / medium / high)
- **How bad?** (degraded experience / partial outage / data loss / business-critical)
- **What would we do now to prevent it?**

Prioritize the high-likelihood × high-impact items. Accept the rest explicitly — "we've decided to take this risk because X." Make a rollback plan for the launch itself.

## Output format

For project breakdowns, produce:

```markdown
# [Project Name] — Breakdown

## Goal
What does success look like? One sentence.

## Milestones
1. [Milestone 1] — estimate, owner, dependencies
2. [Milestone 2] — estimate, owner, dependencies
...

## Critical path
The sequence of milestones that determines the launch date. Anything off this
path can slip without affecting the date.

## Top risks
3–5 items. For each: what's the risk, how likely, how we'll mitigate.

## Open unknowns
Things we don't know yet that could blow up the estimate. Plan to resolve
each before [date].
```

For estimation responses, give a range with a reasoning footprint:

```
Gut estimate: X weeks. Doubled: 2X weeks.

Confidence: [low / medium / high] because [reason].

To get higher confidence, I'd need [planning time / spike on Y / clarity on Z].
```

## Forcing functions

When working through any planning task:

- **If the user wants to skip step 2** (pushing through details and unknowns), push back. That's the whole value.
- **If the estimate has no buffer**, ask why. Things slip. Plans without buffer become death marches.
- **If the project has no defined "done"**, fix that first. Without it, every other estimate is meaningless.
- **If the user says "the team can crunch"**, name what Fournier names: 60 hours/week to ship in a week instead of a week and a half is not "faster," it's "the team gave up their free time." That's sometimes acceptable. It is not a planning strategy.
- **If hiring a project manager would fix this**, Fournier's view: usually it won't. Project managers can become a crutch for engineers to avoid thinking about their own work. Use them carefully.

## What this skill should NOT do

- Don't produce Gantt charts for two-week projects. Match the planning depth to the project size.
- Don't pretend agile means no planning. Agile means responding to change, not skipping forethought.
- Don't accept "we'll figure it out as we go" for projects that span multiple sprints or have hard dependencies. That's a recipe for a death march.
- Don't generate plans that are obviously fictional (e.g., "Week 1: complete authentication system"). Estimates should reflect reality, including the 10-weeks-per-quarter rule.
