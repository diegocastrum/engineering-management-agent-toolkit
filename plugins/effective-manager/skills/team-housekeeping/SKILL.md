---
name: team-housekeeping
description: Use whenever the user wants to improve how the team or department works — communication patterns, breaking down silos, sharing knowledge, root-causing problems, capturing architecture decisions, or measuring team health. Triggers on phrases like "silos", "departments not talking", "Conway's Law", "guild", "chapter", "tribe", "knowledge sharing", "lightning talk", "tech talks", "five whys", "5 whys", "root cause", "post-mortem", "incident review", "ADR", "Architecture Decision Record", "team health check", "Spotify model", "DRI", "Directly Responsible Individual", "RACI", "ownership", "who owns this", "management bugs", "suggestion box". Also use when the user wants to introduce a new practice to the team or scale something they're doing locally.
---

# Team Housekeeping

Source: James Stanier, *Become an Effective Software Engineering Manager*, chapter 14 ("Good Housekeeping").

The team's hidden technical and process debt accumulates silently. Stanier's argument: lightweight, recurring practices keep the team learning and aligned, prevent silos, and surface problems before they compound. None require top-down mandate — you can start them in your team and let them spread.

## When this skill is loaded

Identify mode:

- **Communication audit** — symptoms suggest Conway's Law or silos at play
- **Guild setup** — user wants to start a cross-team interest/skill group
- **Talks culture** — user wants to introduce lightning talks or department talks
- **Root cause** — there's a recurring problem to investigate
- **Decisions log** — user wants a way to capture architecture decisions
- **Health check** — user wants to measure team health
- **Ownership** — user wants to clarify accountability

## Conway's Law

> Organizations that design systems are constrained to produce designs which are copies of the communication structures of these organizations.

Practically: if four groups work on a compiler, you'll get a 4-pass compiler. The way humans communicate becomes the way software is shaped.

**Two common team structures, both with silo failure modes:**

| Team type | Strength | Silo failure |
|---|---|---|
| **Skill-set teams** (all backend in one team, all frontend in another) | Expertise concentration | Software siloed by stack; cross-stack work is hard |
| **Cross-functional teams** (feature teams with all skills mixed) | End-to-end ownership | Feature teams build same things twice; technical inconsistency across teams |

There's no silver bullet. The fix is **lateral communication structures** that cross whatever team boundaries exist.

## Guilds (the lateral structure)

A guild is a cross-team group united by **skill** or **interest** rather than reporting line. They concern themselves with:

- Best practice across a discipline
- Information sharing across teams
- Visibility of that discipline within the company

Examples of guilds:

- JavaScript guild (standards, shared libraries, lint config)
- Security guild (visibility, threat modeling, training)
- Design / UX guild (consistency across products)
- Diversity and inclusion guild (cultural)

The Spotify model formalizes this with **squads** (cross-functional teams), **tribes** (collections of squads in an area), **chapters** (skill-set groups within a tribe), and **guilds** (cross-org interest groups). For most purposes, collapse it to: teams + guilds.

### Starting a guild

You don't need leadership permission. You need a handful of interested people.

1. **Announce intent.** Short email or message describing the guild's purpose, why it's beneficial, and a call for interest.
2. **Pick members.** Balance: cover as many teams as possible; mix seniorities (less experienced members often have more time and motivation to contribute); core group small enough to function (5-10), with broader participation welcome.
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
- Low prep barrier (~30-60 min prep for 5 min)
- Forces clarity
- Less scary for people who don't yet enjoy speaking
- Practice for the ones who'll eventually speak at conferences

Mechanics:
- Allocate prep time as actual tickets — these benefit the team, not personal time
- Keep slides minimal (Takahashi method: a few words per slide; or PechaKucha with images)
- Practice once before delivery
- Capture feedback via a simple survey: one praise, one constructive note per speaker. Anonymous if the team isn't yet candid; named when they are.

Some lightning talk topic seeds:
- A bug I debugged this week and what I learned
- My favorite feature in [language/tool]
- How [system X] works (a short walkthrough)
- An open source project I love and why
- A thing I just learned

### Department talks

Once team lightning talks are working, scale up. Department talks are 20-30 minutes, lower frequency (biweekly or monthly), open to anyone in the department.

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

Example (a real Stanier flow):

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

## Management bugs

A suggestion-box style ticket queue for non-technical issues. Anyone can raise a "management bug" describing a process, communication, cultural, or organizational problem. Examples that worked at Stanier's company:

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

## DRIs (Directly Responsible Individuals)

From Apple. For each key area, accountability rests with **one named person**. They aren't necessarily the doer — but they own that the thing gets done, that monitoring exists, that documentation is current, etc.

DRI vs. RACI (responsible/accountable/consulted/informed):

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

## Forcing functions

- **If teams keep building duplicate code or diverging tech choices**, the symptom is missing guilds. Start one.
- **If a senior person is the only one giving talks**, the culture is wrong. Push for rotation through team lightning talks.
- **If an incident gets a one-line summary in a ticket**, the team is leaving learning on the table. Push for a five-whys.
- **If "why is this code like this" is a recurring question**, that's missing ADRs.
- **If accountability is "the team owns it" without a named DRI**, that often means no one owns it.
- **If management bugs would surface real issues but the user thinks it's "too informal"**, encourage them to try it on their team and let it spread.
- **If the user thinks team health is fine but hasn't asked**, the assumption is doing work it shouldn't. Run a health check.

## What this skill should NOT do

- Don't push the user to mandate any of these from the top down. The whole point is bottom-up.
- Don't generate elaborate RACI matrices when DRI does the job.
- Don't suggest five whys for genuine compliance/legal incidents — those need proper investigation.
- Don't position health checks as performance reviews of the team. They aren't.
