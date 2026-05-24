---
name: team-health
description: Use whenever the user wants to improve team health — proactively (installing lightweight practices like guilds, lightning talks, ADRs, five whys, DRIs, health checks, or "management bugs") or reactively (debugging a team that feels off: missing deliverables, low energy, drama, attrition, simmering conflict, unhappy stakeholders, "something isn't right"). Triggers on phrases like "my team isn't shipping", "team feels low energy", "X is being a jerk", "brilliant jerk", "people are quitting", "people drama", "the team is overworked", "we're not collaborating well", "the team isn't gelling", "I think someone is going to quit", "team morale", "silos", "departments not talking", "Conway's Law", "guild", "chapter", "tribe", "knowledge sharing", "lightning talk", "tech talks", "five whys", "5 whys", "root cause", "post-mortem", "incident review", "ADR", "Architecture Decision Record", "team health check", "Spotify model", "DRI", "Directly Responsible Individual", "RACI", "ownership", "who owns this", "management bugs", "suggestion box". Also use for debugging a team you've inherited, or when introducing a new practice to the team.
---

# Team Health

Sources:
- James Stanier, *Become an Effective Software Engineering Manager*, ch. 14 ("Good Housekeeping")
- Camille Fournier, *The Manager's Path*, ch. 5 and 7 ("Debugging Dysfunctional Teams" / "Debugging Dysfunctional Organizations")

Team health has two modes, and a healthy team needs both:

- **Proactive housekeeping** — lightweight recurring practices (guilds, talks, five whys, ADRs, DRIs, health checks) that keep the team learning, aligned, and visible. None require top-down mandate; you can start them on your team and let them spread.
- **Reactive debugging** — when symptoms appear (missed deliveries, drama, low energy, attrition), treat it like a production incident: hypothesis-driven, data first, observation before action. The same disciplines that make a good systems debugger make a good team debugger.

If housekeeping is the immune system, debugging is the diagnostic flow when symptoms appear.

## When this skill is loaded — identify mode

### Diagnostic modes (something feels off)

- **Symptom triage** — user has a vague "something isn't right" and needs to surface what specifically.
- **Specific dysfunction** — user names a pattern: not shipping, drama, overwork, low energy, "might quit", brilliant jerk, etc.
- **Inherited team** — user just took over a team they don't understand yet.

### Housekeeping modes (proactive)

- **Communication audit** — symptoms suggest Conway's Law or silos.
- **Guild setup** — start a cross-team interest or skill group.
- **Talks culture** — introduce lightning talks or department talks.
- **Root cause** — recurring problem to investigate with five whys.
- **Decisions log** — capture architecture decisions with ADRs.
- **Health check** — measure team health periodically.
- **Ownership** — clarify accountability with DRIs.
- **Management bugs** — suggestion-box queue for non-technical issues.

# Part 1 — Housekeeping (proactive)

## Conway's Law

> Organizations that design systems are constrained to produce designs which are copies of the communication structures of these organizations.

Practically: if four groups work on a compiler, you'll get a 4-pass compiler. The way humans communicate becomes the way software is shaped.

**Two common team structures, both with silo failure modes:**

| Team type | Strength | Silo failure |
|---|---|---|
| **Skill-set teams** (all backend in one team, all frontend in another) | Expertise concentration | Software siloed by stack; cross-stack work is hard |
| **Cross-functional teams** (feature teams with all skills mixed) | End-to-end ownership | Feature teams build the same thing twice; technical inconsistency across teams |

There's no silver bullet. The fix is **lateral communication structures** that cross whatever team boundaries exist.

## Guilds (the lateral structure)

A guild is a cross-team group united by **skill** or **interest** rather than reporting line. They concern themselves with:

- Best practice across a discipline
- Information sharing across teams
- Visibility of that discipline within the company

Examples:

- JavaScript guild (standards, shared libraries, lint config)
- Security guild (visibility, threat modeling, training)
- Design / UX guild (consistency across products)
- Diversity and inclusion guild (cultural)

The Spotify model formalizes this with **squads** (cross-functional teams), **tribes** (collections of squads in an area), **chapters** (skill-set groups within a tribe), and **guilds** (cross-org interest groups). For most purposes, collapse it to: teams + guilds.

### Starting a guild

You don't need leadership permission. You need a handful of interested people.

1. **Announce intent.** Short email or message describing the guild's purpose, why it's beneficial, and a call for interest.
2. **Pick members.** Balance: cover as many teams as possible; mix seniorities (less experienced members often have more time and motivation to contribute); core group small enough to function (5–10), with broader participation welcome.
3. **Pick a leader.** Not a power role — coordinates meetings, agenda, docs.
4. **Pick a cadence.** Monthly meeting is enough to start; weekly if active. Most discussion can be async.
5. **Communication channels.** Public chat channel and/or mailing list. Default to open so anyone can lurk.
6. **Decide documentation.** Where do meeting notes, decisions, and ongoing work live?

### First meeting

Often best to underplan. Just gather and see what surfaces. But possible openers:

- Each member describes how this discipline is currently done in their team. Where does it diverge? Why?
- For technology guilds: maintain a technology radar — adopt / trial / assess / hold.
- For cultural guilds (D&I, etc.): what feels most pressing? Where should the guild focus first?

Guilds aren't permanent. Disband when purpose is served. Split when they outgrow their scope.

## A culture of talks

Knowledge stays trapped in heads until you create venues for sharing.

### Team lightning talks

Start here. 5-minute talks, rotating through team members at a regular cadence (end of each sprint, every other Friday, etc.).

Why short:

- Low prep barrier (~30–60 min prep for 5 min)
- Forces clarity
- Less scary for people who don't yet enjoy speaking
- Practice for the ones who'll eventually speak at conferences

Mechanics:

- Allocate prep time as actual tickets — these benefit the team, not personal time
- Keep slides minimal (Takahashi method: a few words per slide; or PechaKucha with images)
- Practice once before delivery
- Capture feedback via a simple survey: one praise, one constructive note per speaker. Anonymous if the team isn't yet candid; named when they are.

Lightning talk topic seeds:

- A bug I debugged this week and what I learned
- My favorite feature in [language/tool]
- How [system X] works (a short walkthrough)
- An open source project I love and why
- A thing I just learned

### Department talks

Once team lightning talks are working, scale up. Department talks are 20–30 minutes, lower frequency (biweekly or monthly), open to anyone in the department.

Setup needs an owner:

- Book a regular slot
- Solicit and curate talks (a sign-up sheet helps)
- Advertise upcoming talks
- Ensure AV works (remote-friendly)
- Record talks for anyone who missed

Talk types to invite:

- Project show-and-tell (recently completed or in progress)
- Architecture deep-dive on a system
- Success story (how we solved X)
- Horror story (when everything went wrong) — these are gold
- Tech intro (something the speaker is learning)
- Lightning talk collection (batched from multiple speakers)
- Cultural / well-being topics
- External speakers when relevant

## Five whys

When something goes wrong — bug, outage, missed deadline — don't just patch and move on. Run a five-whys session. Ask "why?" repeatedly until you reach the real cause.

Example:

```
Q: Why did the application go down?
A: The API stopped serving requests.

Q: Why?
A: The latest deploy caused a deadlock at startup.

Q: Why?
A: Production has many more concurrent requests than test;
   a non-thread-safe data structure failed under load.

Q: Why didn't tests catch it?
A: Automated tests don't cover high-throughput scenarios.

Q: Why?
A: It wasn't thought about during the development of those tests.
```

Root cause: testing strategy gap. Action: improve test coverage for load.

### Mechanics

- Get the team in a room or shared doc
- Someone writes up Q&A as you go
- Don't stop at the surface answer; keep asking
- It's not always exactly 5 — sometimes 3, sometimes 7
- Output: the root cause + specific tickets for actions + a writeup stored somewhere findable

Benefits beyond fixing the immediate issue:

- Educates the whole team on the failure mode
- Reinforces that *this* level of behavior is unacceptable enough to stop and investigate
- Builds a culture of curiosity about root causes

### Five whys for decisions, not just incidents

Apply the technique to status-quo assumptions:

- Why is this code structured this way?
- Why are we using this tool?
- Why is this approval required?
- Why is this team doing X and not Y?

Surfaces decisions made for good reasons that are no longer true. Saves time and budget.

## Architecture Decision Records (ADRs)

When you make a design decision worth remembering — framework choice, infrastructure pattern, key technical bet — write an ADR. Lightweight: a few paragraphs.

Sections:

1. **Date** — when the decision was made
2. **Status** — proposed / accepted / superseded / rejected
3. **Context** — what was happening and what business priorities led here
4. **Decision** — what you decided
5. **Consequences** — what becomes easier, harder, or different as a result

Store ADRs in the codebase itself (a top-level `docs/adr/` folder) or a shared docs space. Proposing a new architectural direction = writing an ADR + PR.

Why this matters: in 6 months, someone (often the original author) will ask "why is this code like this?" — and the ADR has the answer. Even if people leave, the context survives.

Templates and examples: [adr.github.io](https://adr.github.io/).

## Management bugs

A suggestion-box-style ticket queue for non-technical issues. Anyone can raise a "management bug" describing a process, communication, cultural, or organizational problem. Examples that worked at Stanier's company:

- Clarifying how perceived performance ties to salary increases
- Discussing perceived speed of the department over time
- Concerns about not getting fallow time between projects
- New roles being advertised externally before internally
- Making the careers page more inclusive

### Mechanics

- Tickets live in a normal tracker (Kanban works)
- Anyone can raise
- Each ticket gets a clear owner
- Resolution includes a writeup shared back to the wider department
- Closed tickets archived where everyone can see

Why this works:

- Lower barrier than going directly to leadership
- Transparency — others see what's being addressed
- Forcing function to actually resolve, not just hear

## DRIs (Directly Responsible Individuals)

From Apple. For each key area, accountability rests with **one named person**. They aren't necessarily the doer — but they own that the thing gets done, that monitoring exists, that documentation is current, etc.

DRI vs. RACI (responsible / accountable / consulted / informed):

- RACI is comprehensive and often becomes a paperwork artifact
- DRI is just: *one person, named, accountable* per area

Apply to common gaps:

- Documentation
- Monitoring and alerting
- On-call rota
- Build / CI infrastructure
- A specific service or subsystem
- Quality / testing
- Diversity initiatives
- Onboarding

Make the list visible. Revisit when teams change.

## Team health checks

Periodic check on how the team feels about itself. Spotify's model defines 10 perspectives with "crappy" → "awesome" anchors. Sample perspectives:

- Is it easy to release code?
- Are current processes suitable?
- Is the codebase healthy?
- Is the team delivering value?
- Is work getting done fast enough?
- Is the team's mission clear?
- Are people having fun?
- Is the team learning?
- Does the team have the support they need?
- Are people pawns or players?

### Mechanics

- Run a workshop session (quarterly or every 6 months)
- For each perspective, the team discusses, then votes red / yellow / green
- Aggregate votes per perspective; assign a traffic light to each
- Compare to last check — what's trending up, down, sideways?
- Address red and yellow proactively

The point isn't perfect scores (green-everything is suspicious or a high-functioning unicorn). The point is *change over time* and *spotting hidden issues* before they escalate.

Health checks also feed the debugging loop below — when something's off, the most recent check is one of the first data sources to consult.

# Part 2 — Debugging (reactive)

## Get oriented first

> From Fournier — managing teams is debugging black boxes that interact with other black boxes. Don't try to diagnose before you have these three things:

1. **Surface the symptom.** What specifically is wrong? "Low morale" is not enough — what's the observable behavior? Missed deliveries? Quiet meetings? Public sniping? A specific person?
2. **How long has this been going on?** Days, weeks, months? Recent change or chronic?
3. **What's the user's hypothesis?** Even a vague one. "I think it's the product manager" or "I think it's because we shipped that incident."

Then walk through the diagnostic loop.

## The diagnostic loop

Same shape as debugging a production incident.

### 1. Have a hypothesis

Even a weak one. "I think the team is bored." "I think X is the problem." "I think the roadmap changed too many times." Don't try to investigate without a starting point — you'll boil the ocean.

### 2. Check the data

Before talking to people, look at what the systems already tell you. Often the answer is in data the user has access to but hasn't looked at:

- **Version control / code review activity** — Are check-ins slowing down? Are reviews piling up? Are PRs getting nitpicked into oblivion?
- **Ticket flow** — Are tickets too vague, too big, too small? Are they cycling between states? Are people picking them up and dropping them?
- **Incident frequency** — How much of the team's time is going to fires? Are the same fires recurring?
- **Calendar load** — How many hours per week is the team in meetings? Are the right meetings happening (1-1s, retros) or are they buried under coordination meetings?
- **Chat tone** — Banter and side-conversations, or pure transactional? Lots of "wfh today" and short responses, or normal engagement?
- **Release cadence** — How often does this team ship? Infrequent releases hide pain. Teams that release daily catch problems faster than teams that release monthly.
- **Recent health-check results** — if the team runs them, what's been trending red or yellow?

None of these are smoking guns alone. Patterns across them are the signal.

### 3. Observe the team

If data isn't conclusive, sit in their meetings. Note:

- **Who talks?** Is it the same one or two people? The manager and the PM, with engineers silent?
- **Is there real discussion?** Or is everything pre-decided and the meeting is theater?
- **Are people on phones / laptops / disengaged?** That's a signal the meeting (or the work) doesn't matter to them.
- **Is there any conflict?** Healthy teams have respectful disagreements. Silence isn't harmony — it's often fear or apathy.

Observing changes the observed. Your presence will alter the meeting. Account for that.

### 4. Ask questions

Use 1-1s and skip-levels. Don't lead the witness:

- **Do you know what the team's goals are?** If they can't articulate them, leadership is failing on direction.
- **Why are you working on what you're working on?** If the answer is "because I was told to," motivation is at risk.
- **What's frustrating you right now?** Open-ended; just listen.
- **If you could change one thing about how we work, what would it be?**

### 5. Check team dynamics

Even very professional teams have human texture. Look for:

- Do they collaborate on projects, or is each person on a solo island?
- Is there friendly chat in shared channels?
- Do they have good relationships with adjacent teams (product, design, ops)?
- Would they stick around if you bought pizza, or race for the door? (Caveat: people with obligations leave on time, that's fine.)

## Pattern library: common dysfunctions

Match the symptoms against these patterns. The fix for each is different.

### "We're not shipping"

Most common, most varied causes. Check:

- Are releases infrequent? (Tooling / process problem — invest in shipping more often.)
- Is the team blocked on something specific? (Pair, jump in, or escalate.)
- Are tickets too big? (Push for smaller decomposition.)
- Is the team underwater? (Cut scope, slow the roadmap, add help.)
- Is the team bored? (See "low energy" below.)

If the release process is the bottleneck, fix it. Fournier's example: weekly painful releases bred conflict over the scarce release slot. Daily releases eliminated the conflict overnight.

### "People drama"

Two flavors:

**The brilliant jerk** — high-output engineer making everyone around them miserable. Best handled by not hiring; second best by removing. The trap: your manager (or you) sees their output and resists losing them, while their teammates pay the cost daily. (See *The brilliant jerk problem* below.)

**The negative person** — dwells on the bad, spreads it, makes others lose energy. Easier to address than the jerk: name the pattern with specific examples, give corrective feedback, set expectations. If they can't shift, help them leave the team on good terms.

Either way: act fast. Toxic patterns spread.

### "Unhappiness from overwork"

Diagnose the cause:

- **Production instability** — slow the roadmap, invest in reliability, get downtime / alert / incident counts trending down.
- **Crunch for a real deadline** — be visible, support the team, make it bearable, and *learn* from it so it doesn't repeat. Crunches happen. They shouldn't be a quarterly habit.
- **Unrealistic roadmap** — push back. Saying yes to too much is the manager's failure, not the team's.
- **Chronic 20%+ overhead** — investigate. Often technical debt, on-call burden, or unmanaged support load.

### "Collaboration problems with another team"

- Are you having regular touch-bases with peer leaders? If not, start.
- Are your team and theirs aligned on goals, or competing?
- Are you (the manager) undermining the peer team in front of your team? Even subtle eye-rolls compound.
- Is there a structural fix — a shared metric, a joint project, a co-located meeting?

Don't underestimate small interventions: team lunches, leaving early together once, casual chat in shared channels. The basis for collaboration is people-as-people, not just roles.

### "Low energy / no engagement"

Almost always a *purpose* problem. Do they understand why their work matters? Have they had any input into what they're working on? Have they been pushed past their growth edge in a while, or are they on cruise control?

Every motivation model includes a sense of purpose and connection to the work. If that's gone, you have to rebuild it — usually by reconnecting the team to customer impact, business impact, or team impact.

### "Someone might quit"

Warning signs:

- Suddenly less chatty, leaves early, quiet in meetings, off chat
- Stops engaging with feedback
- Has just been passed over for something they wanted (promotion, project, reorg)
- Or: the opposite — abruptly *more* focused on getting things wrapped up

If you suspect, have a direct 1-1: "I've noticed X, and I want to check in. Are you OK? Is there something we should talk about?" Don't ambush. Often by the time the signs are clear, the decision is made — but sometimes you can address the underlying issue.

### "The team voted and I don't like the outcome"

Fournier's "Conflict Avoider, Conflict Tamer" pattern. Consensus is not always wisdom. Don't outsource hard decisions to a team vote so you can avoid being the bad guy.

If the user is here, ask: are you using voting as cover? Would the outcome change if you owned the call directly?

### "I keep finding out about problems too late"

Open-door policies don't work. People don't bring problems up the hierarchy on their own. Fix:

- Reinstate regular 1-1s with consistent prompts ("anything frustrating you?", "anything you'd change?")
- Do skip-level meetings — 1-1s with people who report to your managers
- Walk around, sit with teams, attend their meetings occasionally
- Build relationships across the org so information comes to you sideways, not just through your reporting chain
- Set up `management bugs` (see above) so non-technical issues have a low-barrier channel

## The brilliant jerk problem (special case)

If the user is describing a brilliant jerk specifically, this deserves its own attention because most managers underestimate the cost.

The pattern:

- Outsized individual output
- Cuts people down in meetings, code reviews, chat
- Dismisses dissent
- Hides information to maintain edge
- "Just hard to work with" but "we can't lose them"

The cost (often invisible):

- Other engineers go quiet in their presence
- People stop bringing ideas, stop disagreeing, stop learning openly
- The team's collective output drops, often by more than the jerk produces
- Hiring and retention degrade as word spreads

The fix:

- Direct corrective feedback, repeated, with specific examples
- Acknowledge the change won't come easily — they've been rewarded for this for years
- Set a clear behavioral bar
- If they can't or won't change, remove them, even at the cost of their output

This intersects with the `hard-conversations` skill — if the user is here, pull that in.

## Forcing functions

### For debugging

- **If the user has no hypothesis at all**, push for one. Even a wrong hypothesis is better than ocean-boiling.
- **If the user hasn't looked at data**, point them to specific data first. Don't theorize before checking version control, ticket flow, and recent health-check results.
- **If the user blames a single person**, ask: what conditions made that person's behavior the path of least resistance? Sometimes it's the person; sometimes it's the system.
- **If the user wants to "talk to the team about it"**, ask what they hope will happen. Team-wide meetings about morale usually backfire. Individual 1-1s usually work.
- **If the team's manager is the problem and the user is that manager**, name it directly. The skill should be willing to say "this sounds like something you're contributing to, here's how."
- **If problems are recurring**, look at structural fixes, not behavioral ones. Recurring "we missed the deadline" isn't a team-effort problem; it's a planning or commitment problem.

### For housekeeping

- **If teams keep building duplicate code or diverging tech choices**, the symptom is missing guilds. Start one.
- **If a senior person is the only one giving talks**, the culture is wrong. Push for rotation through team lightning talks.
- **If an incident gets a one-line summary in a ticket**, the team is leaving learning on the table. Push for a five-whys.
- **If "why is this code like this" is a recurring question**, that's missing ADRs.
- **If accountability is "the team owns it" without a named DRI**, that often means no one owns it.
- **If management bugs would surface real issues but the user thinks it's "too informal"**, encourage them to try it on their team and let it spread.
- **If the user thinks team health is fine but hasn't asked**, the assumption is doing work it shouldn't. Run a health check.

## What this skill should NOT do

- Don't psychoanalyze team members from secondhand description.
- Don't suggest team-building events as a fix for structural problems.
- Don't accept "the team is just like that" as an explanation. Team dynamics are debuggable.
- Don't recommend firing people lightly. But also don't recommend keeping people indefinitely whose impact is net-negative on the team.
- Don't push the user to mandate housekeeping practices from the top down. The whole point is bottom-up.
- Don't generate elaborate RACI matrices when DRI does the job.
- Don't suggest five whys for genuine compliance / legal incidents — those need proper investigation.
- Don't position health checks as performance reviews of the team. They aren't.
