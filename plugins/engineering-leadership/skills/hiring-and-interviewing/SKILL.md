---
name: hiring-and-interviewing
description: Use whenever the user is hiring engineers or managers — writing job descriptions, screening resumes, designing an interview loop, calibrating loops, debriefing after interviews, making hire/no-hire decisions, doing reference checks, or evaluating candidates for culture fit. Triggers on phrases like "hiring", "interview loop", "hire", "no-hire", "JD" / "job description", "debrief", "calibration", "reference check", "screen", "phone screen", "onsite", "loop", "hiring manager", "hiring a senior engineer / tech lead / manager". Also use when the user is reviewing a resume or LinkedIn profile.
---

# Hiring and Interviewing

Source: Camille Fournier, *The Manager's Path*, chapters 7 and 9 ("Hiring Managers", and the chapter 9 discussion of culture fit and ladders).

Fournier's distinction throughout: hiring for skills is the easy part; hiring for **culture fit** (defined as shared *values*, not shared friendships) is where most loops fail.

## When this skill is loaded, identify what's needed

- **Loop design** — what should the interview loop look like for this role?
- **JD writing** — how should this role be described, what level, what required vs. nice-to-have?
- **Pre-interview prep** — I have an interview tomorrow with X for role Y, what should I focus on?
- **Debrief / decision** — interviews done, now what?
- **Reference checks** — who to call, what to ask
- **Calibration concern** — my loop keeps producing bad hires / passing on good candidates

Ask if it's not clear.

## Loop design

For engineers, a typical loop covers:
- **Technical depth** — can they actually code / design at the level expected
- **Technical breadth** — do they have the experience the role requires
- **Collaboration** — do they work well in a team setting
- **Culture / values fit** — do they share the team's working values

For managers, the same categories exist but the content is different:
- **Management skills** — can they actually run 1-1s, give feedback, debug teams, hire
- **Strategy / judgment** — can they make good calls under ambiguity
- **Technical credibility** — enough to lead engineers (varies by level)
- **Culture / values fit**

### Engineer loop, opinionated default

For mid-to-senior engineers (adjust for level):

1. **Phone screen / recruiter screen** — basic qualification, role fit, salary range
2. **Hiring manager call** — what's the role, what's the team, what are they looking for
3. **Coding / technical depth** — give them a real-feeling problem, ideally one drawn from problems your team has actually faced (anonymized). Pair-coding format is more humane than whiteboard.
4. **System design** — for anyone above mid-level
5. **Collaboration / behavioral** — past projects, conflicts, decisions. STAR-format probing.
6. **Team interview** — at least one peer they'd work with daily
7. **Skip-level / cross-functional** — meet a manager-of-managers or PM peer

### Manager loop, opinionated default

Fournier's specific recommendations from chapter 7:

1. **Hiring manager screen** — basic fit, role context
2. **1-1 role-play** — have the people who'd report to this manager interview them. Ask them to help with a real problem one of those engineers has right now. Or to role-play a 1-1 with someone underperforming. You learn more about a manager's instincts in 30 minutes of role-play than in an hour of "tell me about your management philosophy."
3. **Team debugging** — ask about a project that ran late and what they did. Or role-play addressing an engineer who's thinking about quitting.
4. **Management philosophy** — what do they think the job is? How do they delegate? How do they stay hands-on? An experienced manager with no philosophy is a red flag.
5. **Technical screen** — calibrated to the role. Don't make a noncoding director do a coding screen, but do verify they can establish credibility with engineers through design / architecture questions on systems they've built.
6. **Presentation** — for senior roles. How do they handle a room, structure thoughts, answer questions? Caveat: don't overweight this. Plenty of excellent managers aren't strong public speakers.
7. **Cross-functional peer interview** — product, design, or another tech lead they'd partner with
8. **Reference checks** — non-negotiable for management hires (see below)

## JD writing

A good JD answers four questions:

1. **What does this person do day-to-day?** Concrete. Not "drive innovation" — "lead a team of 4–6 engineers building X."
2. **What level / scope is the role?** Map to your career ladder if you have one.
3. **What must they have already done?** Distinguish must-haves from nice-to-haves rigorously. Long lists of must-haves filter out good candidates (especially underrepresented ones).
4. **What's the team / company context?** Culture, scale, what stage, what's the engineering culture like.

For technical levels above mid-career, the JD should distinguish **management track** vs. **IC track** if both exist at that level. Fournier specifically argues for parallel ladders.

## Pre-interview prep

When the user has an interview coming up:

1. **What signal is this interview supposed to produce?** If you can't say, the loop is broken. Each interview owns specific signals (technical depth / collaboration / values / etc.). Don't try to assess everything in every slot.
2. **Review their resume / prior interviews** if any. Spot the things you want to probe.
3. **Prepare 2–3 anchor questions** for the signals you own, plus follow-ups for likely answers.
4. **Plan the time**: intro (3–5 min), main content (40 min), their questions (10 min), close (2 min). Don't run over and steal time from their questions — what they ask tells you a lot.

For values / culture-fit signals specifically: don't ask "are you a culture fit?" Ask behavioral questions that surface the values you care about:
- If you value collaboration: "Tell me about a time you disagreed with a teammate on technical direction. How did it resolve?"
- If you value ownership: "Tell me about something that broke in production that you owned end-to-end."
- If you value mentorship: "What's been your experience helping more junior engineers grow?"

## Debrief

Run the debrief tightly. Common failure modes:

- **Letting the loudest opinion anchor the decision.** Collect written feedback before anyone discusses, ideally with a hire/no-hire vote already submitted.
- **"Culture fit" used as a vibe check.** Always ask: *which values* did this person clash with or align with? If the answer is "I just didn't click with them," that's not signal, that's bias.
- **Falling for charm in management hires.** Managers can interview well — they're good at communication — and still be ineffective on the job. Probe the role-play results more than the polished answers.
- **Hiring against gap rather than for strength.** If you're hiring because the team is drowning, you'll be tempted to take whoever can start Monday. Resist. A bad hire is more expensive than a slow hire.

### Decision framework

For each interviewer, get:
- **Hire / no-hire** (binary, no "weak hire / weak no-hire" hedging — push for a decision)
- **What signal did they get?** (positive and negative)
- **What's the strongest concern?**

Then synthesize. Strong opposition from one interviewer with specific reasons usually beats lukewarm support from three. But also watch for the lone dissenter who can't articulate why — sometimes that's bias.

## Reference checks

Fournier's hard rule: **always do reference checks for management hires.** Skipping is a disservice to your team.

Even for engineers, reference checks catch what interviews miss. The candidate picks the references — that's fine — and you can still learn a lot.

Good questions:
- "What was your working relationship?"
- "What does this person do best?"
- "Where do they struggle? What do they need to work on?"
- "What kind of manager / teammate gets the best out of them?"
- "Would you work with them again? Would you hire them?"
- For management references specifically: "How did their team feel about working for them?"

Listen for hesitations, evasions, faint praise. "They were... very smart" is not a recommendation.

## Calibration concerns

If the user says their loop keeps producing bad hires:

- **Are loop members aligned on the bar?** Calibration session: review notes from recent hires (good and bad), agree on what signals would have caught the bad ones.
- **Is the loop consistent?** Same loop for every candidate, same questions, same scoring rubric.
- **Are interviewers trained?** Many engineers interview by gut. Brief them on what signals they own and how to elicit them.
- **Are you over-weighting any single signal?** "Crushed the coding round" doesn't mean hire if the collaboration round was a disaster.

If the user says their loop keeps passing on people the team later wishes they'd hired:

- **Is the bar miscalibrated?** Some teams set the bar so high they only hire people who would have been overqualified.
- **Is the loop biased against certain backgrounds?** Trial questions on people who've shipped real software but didn't go to a "top" school, or who came from non-traditional paths.
- **Are you optimizing for a profile that's not what the role needs?** A staff engineer doing system design interviews on someone you're hiring to ship features fast might be filtering for the wrong things.

## Culture fit, done right

Fournier's framing: culture fit means shared *values*, not shared friendships. The "would you be stuck in an airport with this person" test is a friendship test, and friendship tests correlate with school / class / race / gender — they discriminate without telling you so.

To do culture fit well:

1. **Write down your values explicitly.** "Engineering excellence." "Collaboration over heroics." "Direct, kind communication." Whatever yours are. If you can't name them, you can't hire for them.
2. **For each value, define what it looks like behaviorally.** What does someone exhibiting this value *do* in a meeting? In a code review? Under pressure?
3. **Design interview probes** for those behaviors.
4. **Debrief on values explicitly** — not "did they fit" but "which value did they exemplify or clash with."

Done this way, culture fit *expands* the candidate pool by surfacing alignment in people who don't look or sound like the existing team. Done as a vibe check, it shrinks the pool to clones of the founders.

## Forcing functions

When working through hiring tasks:

- **If the user says "we just need someone," check the bar.** Desperation drives bad hires.
- **If "culture fit" appears without specifics**, demand specifics. Which value?
- **If the loop has no role-play for a management hire**, flag it. Conversation alone doesn't surface management instinct.
- **If the user is about to hire someone with significant concerns**, name them. "You've described X, Y, Z concerns. Do you want to hire this person, or do you want to keep looking?" Don't rubber-stamp.
- **If reference checks aren't planned for a management hire**, push back hard. This is the cheapest signal you can get.

## What this skill should NOT do

- Don't write generic JDs from a one-line prompt. Push for context.
- Don't generate interview questions that test trivia (favorite color of the bikeshed). Tests should reflect real work.
- Don't help the user rationalize a hire they have concerns about. Surface the concerns; let them decide.
- Don't recommend hiring fast at the expense of hiring well. Fournier's view: an empty seat is cheaper than a bad fill.
