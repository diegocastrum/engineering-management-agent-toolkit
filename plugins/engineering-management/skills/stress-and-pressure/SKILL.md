---
name: stress-and-pressure
description: Use whenever the user describes being under deadline pressure, a high-stakes launch, a system on fire, a team under stress, "the whole company is watching us", or projects being late. Triggers on phrases like "deadline", "crunch", "under pressure", "Eye of Sauron", "fire drill", "launch next week", "project is late", "we're slipping", "scope creep", "what should we cut", "MoSCoW", "Brooks's law", "throw more engineers at it", "imposter syndrome", "feel like a fraud", "overconfident", "Mount Stupid", "the team is burning out", "team morale during crunch". Also use after a stressful project to plan recovery.
---

# Stress and Pressure

Source: James Stanier, *Become an Effective Software Engineering Manager*, chapters 10 ("Humans Are Hard") and 11 ("Projects Are Hard").

Pressure compounds and warps. Stanier's argument: handle the *team* through it (Eye of Sauron principles), pull the right *project* levers (scope/resources/time), and watch for the psychological traps that show up under stress (Mount Stupid, imposter syndrome).

## When this skill is loaded

Identify mode:

- **Under pressure right now** — apply Eye of Sauron principles
- **After a crunch** — gaze-averted recovery sequence
- **Slipping project** — use scope/resources/time levers + MoSCoW
- **Productivity question** — productivity-per-head and Brooks's Law
- **Psychological pattern** — Dunning-Kruger / imposter syndrome surfacing
- **Pre-mortem prep** — heading into a high-stakes period

## The Eye of Sauron

When a project becomes the company's headline thing, the entire org's attention turns to you. The "Eye of Sauron" — flaming, piercing, unrelenting.

### Warning signs the gaze has turned

- Stakeholders showing increased interest unprompted
- Senior people probing in the hallway, kitchen, on Slack
- Boss or boss's boss asking direct progress questions more often
- Marketing hype escalating beyond what the project actually is
- Everything on fire and customers about to leave

### 6 principles for operating under the gaze

1. **Align the team.** If they don't already know the heat is on, tell them. Use the pressure positively — clarity on goal, clarity on what success looks like, your job to facilitate.

2. **Over-communicate.** Weekly (or more frequent) updates to stakeholders. Short demo video if quicker than writing. Make it impossible for anyone to wonder where things are.

3. **Invite responses and feedback.** Open channel — chat, mailing list — so curious minds have somewhere to go. Frustration grows when there's nowhere to ask.

4. **Release frequently.** Don't hold builds back for the deadline. Feature toggles, daily ship to production, frequent demos. Late-stage big-bang releases produce late-stage panic.

5. **Be pragmatic.** As dates close in, ship some ugly code. Note every hack to clean up later. Idealism kills launches. But document the debt explicitly so the cleanup is real.

6. **Lead from the front.** Put the work in. Be visible. High-stakes projects can be career-defining for the team — own them.

### Gaze-averted recovery (after launch / after the fire)

The crunch is over. What you do next determines whether you've earned future credibility or burned the team out.

- **Celebrate.** Lunch, drinks, cakes, gaming night, time off — whatever fits. Say thank you specifically.
- **Tidy up technical debt.** Next sprint goes to the hacks you took. Don't skip this.
- **Self-guided project time.** Block a chunk for self-directed learning. Reset minds.
- **Reflect.** Run a retrospective. What worked, what didn't, what to do differently. Even if perfect, this closes the chapter.
- **Plan and regroup.** What's next? Make it exciting, not a crash into the next crunch.

### Fallow time

If a team finds itself under the Eye too often, that's burnout and attrition incoming. As a manager, fight for the after-project space the team needs. Stagger pressure between teams across the year if you can — your marketing org should be spacing launches anyway.

It's a marathon, not a sprint. If you're sprinting every quarter, the manager is failing.

## Scope, resources, time

When a project is in trouble, you have three levers. Quality isn't one — never compromise quality (you're in the wrong job if you would).

```
                Time
                  |
                  |
            ─────●─────
                  |
        Scope ───●─── Resources
```

### Scope (your strongest lever)

Use the **MoSCoW** method. Categorize every feature in the project:

| Category | Meaning | Behavior |
|---|---|---|
| **M**ust | Absolutely required for launch | Build and ship |
| **S**hould | Important but not required for first launch | Ship as 2nd increment if possible |
| **C**ould | Desirable but not necessary | Skip unless time permits |
| **W**on't | Consciously decided not to build | Document and move on |

Pre-work this *before* crunch — make stakeholders rank. When the squeeze comes, you cut Coulds and defer Shoulds without surprise.

Use **stretch goals** to define the next milestone after the must-haves. Where's the first release line? What gets added in release 1.1? Pre-deciding gives a buffer when things go sideways.

### Resources (your weakest lever)

Brooks's Law: **adding people to a late software project makes it later.**

Why:
- New people need ramp-up that takes existing team time
- Communication overhead grows quadratically (n(n-1)/2 channels)
- Most work isn't parallelizable past a point
- Code vicinity — two engineers in the same module = merge conflicts

That said, sometimes you *can* add help — *if* the work is genuinely parallelizable. Before asking for more bodies, categorize:

- **Sequential work** (each step depends on the previous): adding people doesn't help; pair-program at best
- **Parallel work** (independent streams): adding people might help
- **Code-vicinity work** (same files): adding people definitely hurts
- **Technical-complexity work** (specialist required): adding generalists doesn't help

If you ask for help, ask for it on a *specific parallelizable piece*, with a specific person in mind. Not "send help."

### Time (rarely yours to control directly)

Before assuming the deadline is fixed, investigate.

- Who set the deadline and why?
- What actually happens if it slips by a week? Two weeks? A month?
- Is there a hard external event (conference, press release, contractual obligation) or is it artificial?

Apple announces things on stage and ships months later. Most deadlines move when you ask the right question.

If the deadline truly can't move and you can't add people, then it's **scope** — that's your lever.

## Productivity per head (Brooks's Law extended)

As a company grows, productivity per head decreases. This isn't laziness; it's structural:

- Business-as-usual gets harder (more customers, more SLAs, more security work)
- More legacy code to navigate
- Communication overhead grows
- Process overhead grows

When external observers complain "the team is slower than it used to be," the answer isn't "people are lazy" — it's "we're successful and that has costs."

What you can encourage:

- **Expose hidden complexity.** When a salesperson says "just add auth, easy" — surface the real list: session timeout, 2FA, password change, account recovery, audit log. Build empathy for what quality work means.
- **Always show progress.** Open sprint demos. Team newsletter. Frequent ship. Don't let "are they doing anything?" be a question.
- **Develop pragmatically.** Always measure customer impact. Delete features that didn't get traction. Reserve ~20% of time for technical debt and refactoring as you go.

## Mount Stupid (Dunning-Kruger)

People who know least about a topic feel *most* confident making decisions about it. Two flavors:

- **Junior engineer overconfidence.** Just graduated, top grades, thinks the problem is simple. Doesn't know what they don't know. Decides things that turn out badly.
- **Senior leader overconfidence.** Too far from technical details to know the problem is hard. Confidence + position power = decisions that overrule technical reality.

### What to do

For overconfident juniors: **coaching, not crushing.** Use the "keep the thought bubble over their head" technique — ask questions that lead them to discover the complexity themselves. "What happens at 10x our current load?" "How does this interact with [system]?" Don't humiliate; let them find the edge.

For overconfident seniors: pick your battles. Some seniors will engage with reasoned debate. Some can't — and verbal in-meeting confrontation makes it worse. For those, take it offline. Research, write up, present facts in email or short doc. Mount Stupid + big ego is the worst combo; verbal pushback rarely wins it. Sometimes you leave the meeting in a haze of anger and revisit the next day with facts.

## Imposter syndrome

The inverse of Mount Stupid. High-achieving people feel they're frauds about to be exposed.

- **Junior with imposter syndrome:** sees the seniors around them as wizards, undervalues own contribution.
- **Senior with imposter syndrome:** forgets their experience came from work, not luck. Becomes overly cautious, holds back contributions.

### What to do

For juniors with imposter syndrome: **pair them with a senior mentor.** Repeated success in pair-programming builds confidence faster than reassurance. Make their wins visible.

For seniors with imposter syndrome: **draw them into the conversation by name.** "What's your read on this?" "You've solved something similar — walk us through it." Make them realize how much they contribute. Pair them with juniors for mentoring — they'll see how much they have to teach.

## Pre-mortem (proactive prep)

When heading into a high-stakes period, run a pre-mortem with the team:

> "Imagine it's [launch date + 2 weeks]. The launch failed. What are the top 10 reasons?"

Cluster the answers. For each cluster:

- Likelihood (low / med / high)
- Impact (degraded / partial outage / data loss / business-critical)
- Mitigation now

Prioritize high×high. Accept the rest explicitly. Have a rollback plan for the launch itself.

## Forcing functions

- **If the user is mid-crunch and considering adding people**, walk through Brooks's Law and the parallelism categorization first.
- **If the user wants the team to "just work harder" or "hustle"**, push back. That's the whip; the carrot is autonomy/mastery/purpose. Crunch as policy is a planning failure.
- **If the team has been under the Eye for >1 quarter continuously**, that's burnout incoming. Recovery isn't optional.
- **If a deadline is described as "fixed"**, ask who set it and what actually happens if it moves. Most deadlines move under questioning.
- **If user is shielding the team from knowing it's high-stakes**, flag it. Hidden pressure produces panic; clear pressure can be channeled.
- **If post-crunch there's no celebration or recovery time planned**, fix that. The team paid; pay them back.

## What this skill should NOT do

- Don't help the user rationalize chronic crunch as normal.
- Don't suggest scope-cutting without involving the actual product/stakeholder owner.
- Don't encourage "hero" narratives — they entrench unsustainable patterns.
- Don't diagnose individuals as Dunning-Kruger or imposter syndrome from secondhand description.
