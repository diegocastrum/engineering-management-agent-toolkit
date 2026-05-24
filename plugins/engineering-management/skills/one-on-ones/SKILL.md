---
name: one-on-ones
description: Use whenever the user is preparing for, running, reflecting on, or trying to fix 1-1 meetings with direct reports — including preparing an agenda, deciding what to bring up, capturing notes afterward, contracting with a new report, planning feedback to deliver, or diagnosing 1-1s that feel off (status-only, boring, cancelled, drifting into therapy). Triggers on phrases like "1-1", "1:1", "one-on-one", "weekly check-in", "first 1-1", "contracting", "rolling agenda", "new direct report", "what to talk about", "they have nothing to say", "should I cancel". Also use when starting a new reporting relationship (new hire, transfer, former peer now reporting in).
---

# One-on-Ones

Sources:
- James Stanier, *Become an Effective Software Engineering Manager*, ch. 4 ("One-to-Ones")
- Camille Fournier, *The Manager's Path*, ch. 1 and 4

1-1s are the operating system of management — the highest-leverage hour a manager has each week. Skip them and you stop seeing problems until they're irreversible. They aren't status meetings, they aren't optional, and they need deliberate setup to work well.

## When this skill is loaded — identify mode

- **Setup mode** — user has never run 1-1s before and needs the basics.
- **First 1-1 (contracting)** — new reporting relationship; set the terms explicitly.
- **Prep mode** — "I have a 1-1 with X tomorrow." → produce an agenda.
- **Reflect mode** — "Here's what we discussed." → capture, extract actions, flag patterns.
- **Diagnostic mode** — 1-1s feel wrong (status-only, cancelled, silent, therapy-like).

If it's not obvious, ask once. Then proceed.

## Setup mode: the fundamentals

If the user is starting from scratch, lock these in:

- **Cadence**: weekly, every week. Steady rhythm matters more than perfect timing.
- **Duration**: 1 hour to start. Shorten later if mutual; don't default to 30 min.
- **Location**: private — meeting room or quiet corner, not breakout area, not near desks.
- **Same time, same place** each week. Don't move unless absolutely necessary.
- **Shared notes doc per report** — Google Docs or similar. The rolling agenda lives here; both sides add to it during the week.
- **If remote**: video call, both cameras on. Not phone, not chat.

## The five 1-1 styles

> From Fournier — a 1-1 is not one thing. Match the style to what's actually needed.

| Style | When it fits | Watch out for |
|---|---|---|
| **To-do list** | Both sides have concrete items; shared doc works well | Becoming so transactional that the human side disappears |
| **Catch-up** | Direct report drives; open agenda; good for senior ICs | Drifting into therapy or pure complaining |
| **Feedback meeting** | Quarterly cadence on career, growth, behaviors | Treating it as the *only* time feedback happens — it isn't |
| **Progress report** | Mostly for managing managers, or someone on a side project you don't see | If this is your default for ICs, you're wasting both your times |
| **Getting to know you** | New reports, after big life events, when relationship feels thin | Forcing it on people who don't want it |

Most healthy 1-1s mix two or three. If every 1-1 is the same style, that's a signal.

## First 1-1: contracting

A contracting session is the first 1-1 with any new direct report. It's structured. The point is to make the relationship's terms explicit instead of assumed.

Send the questions ahead so they can think. Work through them in the meeting and capture answers in the shared doc.

### The five contracting questions (Stanier)

1. **Which areas would you like the most support with?** Don't suggest answers if they struggle — let it sit. Solutions aren't required yet.

2. **How would you like to receive feedback and support?** Probe with concrete examples. "If I disagreed with your technical direction on a whiteboard with the team watching, would you want me to say so in front of everyone, pull you aside afterward, or send it in writing later?"

3. **What could be a challenge of us working together?** Surfaces initial impressions, gaps in skill alignment, awkward dynamics. If they recently applied for the role you got, address it here.

4. **How might we know if the support I'm offering isn't going well?** Explore each other's signs of frustration. Some people get loud; some go quiet and stew.

5. **How confidential is the content of our meetings?** What can you act on directly? What requires their permission? What can you relay to your own manager by default?

Revisit contracting every 6-12 months, or when something changes.

### Also worth asking (Hogan, via Fournier)

Tactical preference questions — drop into contracting or an early follow-up 1-1:

- How do you like to be praised — in public or in private?
- What's your preferred medium for serious feedback — written so you can digest it, or verbal in conversation?
- Why did you decide to work here? What are you excited about?
- How will I know when you're in a bad mood or annoyed? Any consistent triggers?
- Are there manager behaviors you know you hate?
- Any surprises since you joined — good or bad?

### Other setup for new hires

- A **30/60/90-day plan** with concrete milestones — surfaces mishires fast.
- An invitation for *their* feedback on you in the first 90 days, while their eyes are still fresh.

### Former peer transitioning to report

Name the awkwardness directly: "This is going to be a weird transition and I'm going to make mistakes — I need you to tell me when I do." Resist the urge to micromanage; they'll be hypersensitive to any "I got rewarded over you" signaling.

## Prep mode

The shared doc *is* the agenda. Both sides drop items during the week. Pre-meeting, scan it and add what's missing. Set a recurring to-do reminder to prep the agenda day-of.

When generating an agenda, gather:

1. **Recency.** What's happened with this person since the last 1-1? Recent work shipped or stuck? Recent feedback given or owed? Signals from skip-levels, peer comments, code reviews, incidents?
2. **Standing items.** Anything in the running notes that's been hanging? Open commitments from either side?
3. **Their agenda.** Most 1-1s should be majority-driven by the report. If you don't know what they want to discuss, the first item is "what's on your mind."
4. **Your agenda.** What feedback do you owe (positive or corrective)? What context do they need? What career or growth conversation is overdue?

Output a short agenda — 3–5 items, ordered by what *they'd* want to discuss first, then what you need to bring up. Flag anything deferred from a previous 1-1: Fournier's "no surprises" rule means avoidable surprises in reviews come from feedback that should have been given in a 1-1 and wasn't.

## How to actually run the meeting

**It's their meeting, not yours.** Aim for them to do ~70% of the talking. Use leading questions:

- "How has your work been going this week?"
- "Tell me about those production issues last week."
- "How are you feeling about the June deadline?"
- "How could we ensure we've got the right metrics in place ahead of time?"

**Silence is golden.** Don't fill every pause. The best parts of conversations often emerge after a trailing-off silence. "...and that's the problem, I guess. I just have no idea why they aren't helping us more." Let it land before responding.

**Don't make it a status meeting.** Status lives elsewhere (tickets, standup, chat). Touch updates if needed, then move on. Probe deeper: "How could we deploy that quicker?" "Is this the right technical approach?" — you don't need to know the answer.

## Reflect mode

During the 1-1, take notes in the shared doc — yes, visibly, while you talk. Bullets; bold for actions.

After the 1-1:

1. **Capture takeaways** — what was discussed, what was decided, what's open.
2. **Extract actions** separately for you and for them. Explicit owner and rough timeline.
3. **Move your actions into your to-do list immediately.** Nothing destroys trust faster than a manager who doesn't follow up on what was raised — most people have experienced this and assume it of all managers.
4. **Flag patterns across multiple 1-1s** if context is available: is this person bringing the same problem repeatedly? Have you praised them this month? Is feedback you intended to give still undelivered?

## Diagnostic mode

Match the complaint:

- **"It's just a status meeting"** — move status to async (email, chat, standup). Open with "What's on your mind?" If they have nothing prepared, use a topic idea below.

- **"They have nothing to say"** — sometimes true; some senior ICs in a groove genuinely don't need weekly. Try bi-weekly with mutual agreement. But check first: are they hiding things? Disengaged? About to quit? A senior IC in flow is different from a junior who doesn't know what 1-1s are for. Ask directly: "How honestly are we able to talk in these? What would have to change for them to feel more useful?"

- **"They keep cancelling / I keep cancelling"** — the cadence is broken. Marc Hedlund's line, via Fournier: *1-1s are like oil changes — skip them and plan to get stranded.* Re-anchor the slot. Mid-morning Tuesday–Thursday holds up best; Mondays and Fridays get killed by long weekends.

- **"It always tails off after 20 minutes"** — fine some weeks. Don't pad; end early. But if it's consistent, the relationship is too distant for an hour — fix the relationship, not the agenda.

- **"It feels like therapy / it's just complaining"** — empathetic listening is good; wallowing isn't. Acknowledge the feeling, then redirect: "What would help here?" or "What's in your control?" If it's recurring and heavy, see *You are not a therapist* below.

- **"I never know what to bring up"** — usually means you're not paying enough attention day-to-day. Look at their tickets, code reviews, recent meetings. There's always something. If there genuinely isn't, the relationship is too distant — use the topic ideas below as a stopgap and fix the upstream problem.

- **"Pulling teeth — they won't open up"** — you may be talking too much. Try the silence test. Try a coaching question instead of probing. Try going for a walk instead of sitting across a table.

- **"They never push back / never disagree"** — possible culture-of-fear problem. Test: when's the last time they told you you were wrong? If you can't remember, you have the problem, not them.

## Topic ideas when the agenda is thin

- **Architecture deep dive** — ask them to walk you through part of the system. You learn; they surface weak spots.
- **Process deep dive** — how many steps to ship? Could any be removed?
- **A relevant article** — something from Hacker News, an open source project. Loop it back to the work.
- **Teaching** — share something you're learning (delegation, hiring).
- **Department or company direction** — what do they think? Reservations?
- **Collecting feedback** — anyone been particularly helpful recently? Pass it on.
- **Sharing something you're working on** — a JD draft, your own side project, a roadmap discussion with the PM. They like seeing what their manager does.

Connecting themes: sharing, trust, working through technical and interpersonal problems together.

## Pulling the Andon Cord

If either of you feels uncomfortable with a topic — too personal, too off-topic, needs someone else's help — either can call it: "Let's pause this; I'm not sure I'm the right person, can we bring HR in?" or "This is getting heavier than I expected, can we revisit next week?"

(Metaphor: on a Toyota production line, any worker can pull the cord to halt the line and bring in support. Same principle here.)

## You are not a therapist

A 1-1 sometimes turns into a venting session or, rarely, surfaces real distress. Be clear about the line:

- You can listen empathetically. You should.
- You shouldn't try to diagnose, treat, or be the primary support for someone in mental health distress.
- If someone is struggling beyond what a manager can help with, say so: "I sense you may not be feeling your best self. I want to make sure you get external support if you need it." Suggest HR, EAP, a therapist.
- Never diagnose. Never assume. Wait until they tell you something is wrong before treating it as such.

## Forcing functions (apply silently)

When generating any 1-1 output:

- **If the user hasn't done contracting with a new report**, push for it as the first 1-1. The awkwardness is worth it.
- **If 1-1s are status updates**, name it. The fix is to move status async.
- **If the user is doing all the talking**, flag the ~70% rule.
- **If the user hasn't praised this person in the last 2–3 1-1s** (per their notes), surface "what's something they did well recently?" as a prompt.
- **If corrective feedback has been deferred more than once**, flag it explicitly — this is now the kind of thing that becomes a review-day surprise.
- **If actions from previous 1-1s haven't moved**, that's a trust problem. Address it directly with the report and own it.
- **If the user is delaying or moving 1-1s frequently**, push back. The whole system depends on the steady cadence.
- **Treat "everything's fine" reports with mild suspicion.** Sometimes true; also the most common signal of a report about to quit (Fournier's "warning signs" pattern).

## Output format

For prep mode:

```markdown
# 1-1 with [name] — [date]

## Standing items (their doc)
- ...

## Items I want to bring up
- ...

## Topic suggestion if agenda is thin
- ...

## Things to ask about
- ...
```

For reflect mode:

```markdown
# 1-1 with [name] — [date]

## Discussed
- ...

## Decisions
- ...

## Actions — me
- [ ] ...

## Actions — them
- [ ] ...

## Follow up next week
- ...
```

## What this skill should NOT do

- Don't psychoanalyze the report from secondhand description. Stick to what the user observed.
- Don't generate generic "rapport-building" prompts. Use the contracting questions or the topic ideas list.
- Don't suggest 30-minute 1-1s as a default. Start at 60 — you can always shorten later.
- Don't treat the 1-1 as a venue for performance reviews. Those happen separately, with prep, in dedicated sessions.
- Don't produce HR-style scripts for normal conversations. 1-1s are between two adults; over-scripting kills them.
