---
name: team-health-debugger
description: Use whenever the user describes a team that feels off — missing deliverables, low energy, drama, simmering conflict, attrition, unhappy stakeholders, or just a vague "something isn't right." Triggers on phrases like "my team isn't shipping", "the team feels low energy", "X is being a jerk", "people are quitting", "people drama", "the team is overworked", "we're not collaborating well", "the team isn't gelling", "I think someone is going to quit", "team morale". Also use for debugging a team you've inherited or one you don't fully understand yet.
---

# Team Health Debugger

Source: Camille Fournier, *The Manager's Path*, chapters 5 and 7 ("Debugging Dysfunctional Teams" and "Debugging Dysfunctional Organizations").

Fournier's framing: managing teams is debugging black boxes that interact with other black boxes. The same disciplines that make a good systems debugger make a good team debugger — relentless about *why*, hypothesis-driven, data-checking before guessing.

## When this skill is loaded, do this first

Get oriented in three quick steps. Don't try to diagnose before you have these:

1. **Surface the symptom.** What specifically is wrong? "Low morale" is not enough — what's the observable behavior? Missed deliveries? Quiet meetings? Public sniping? Specific person?
2. **How long has this been going on?** Days, weeks, months? Recent change or chronic?
3. **What's the user's hypothesis?** Even a vague one. "I think it's the product manager" or "I think it's because we shipped that incident."

Then walk through the diagnostic loop below.

## The diagnostic loop

Same shape as debugging a production incident.

### 1. Have a hypothesis

Even a weak one. "I think the team is bored." "I think X is the problem." "I think the roadmap changed too many times." Don't try to investigate without a starting point — you'll boil the ocean.

### 2. Check the data

Before talking to people, look at what the systems already tell you. Often the answer is in the data the user already has access to but hasn't looked at:

- **Version control / code review activity** — Are check-ins slowing down? Are reviews piling up? Are PRs getting nitpicked into oblivion?
- **Ticket flow** — Are tickets too vague, too big, too small? Are they cycling between states? Are people picking them up and dropping them?
- **Incident frequency** — How much of the team's time is going to fires? Are the same fires recurring?
- **Calendar load** — How many hours per week is the team in meetings? Are the right meetings happening (1-1s, retros) or are they buried under coordination meetings?
- **Chat tone** — Banter and side-conversations, or pure transactional? Lots of "wfh today" and short responses, or normal engagement?
- **Release cadence** — How often does this team ship? Fournier's heuristic: infrequent releases hide pain. Teams that release daily catch problems faster than teams that release monthly.

None of these are smoking guns alone. Patterns across them are the signal.

### 3. Observe the team

If data isn't conclusive, sit in their meetings. Note:
- **Who talks?** Is it the same one or two people? The manager and the PM, with engineers silent?
- **Is there real discussion?** Or is everything pre-decided and the meeting is theater?
- **Are people on phones / laptops / disengaged?** That's a signal the meeting (or the work) doesn't matter to them.
- **Is there any conflict?** Healthy teams have respectful disagreements. Silence isn't harmony — it's often fear or apathy.

Fournier's warning: observing changes the observed. Your presence will alter the meeting. Account for that.

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
- Would they stick around if you bought pizza, or race for the door? (Fournier's "happy team" heuristic — caveat: people with obligations leave on time, that's fine.)

## Pattern library: common dysfunctions

Match the symptoms against these patterns from chapter 5. The fix for each is different.

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

**The brilliant jerk** — high-output engineer making everyone around them miserable. Best handled by not hiring; second best by removing. The trap: your manager (or you) sees their output and resists losing them, while their teammates pay the cost daily.

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

Fournier's framing: every motivation model includes a sense of purpose and connection to the work. If that's gone, you have to rebuild it — usually by reconnecting the team to customer impact, business impact, or team impact.

### "Someone might quit"

Warning signs from chapter 6:
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

This intersects with the hard-conversations skill — if the user is here, suggest pulling that in.

## Forcing functions

When working through team-health questions:

- **If the user has no hypothesis at all**, push for one. Even a wrong hypothesis is better than ocean-boiling.
- **If the user hasn't looked at data**, point them to specific data first. Don't theorize before checking version control and ticket flow.
- **If the user blames a single person**, ask: what conditions made that person's behavior the path of least resistance? Sometimes it's the person; sometimes it's the system.
- **If the user wants to "talk to the team about it"**, ask what they hope will happen. Team-wide meetings about morale usually backfire. Individual 1-1s usually work.
- **If the team's manager is the problem and the user is that manager**, name it directly. The skill should be willing to say "this sounds like something you're contributing to, here's how."
- **If problems are recurring**, look at structural fixes, not behavioral ones. Recurring "we missed the deadline" isn't a team-effort problem; it's a planning or commitment problem.

## What this skill should NOT do

- Don't psychoanalyze team members from secondhand description.
- Don't suggest team-building events as a fix for structural problems.
- Don't accept "the team is just like that" as an explanation. Fournier's premise is that team dynamics are debuggable.
- Don't recommend firing people lightly. But also don't recommend keeping people indefinitely whose impact is net-negative on the team.
