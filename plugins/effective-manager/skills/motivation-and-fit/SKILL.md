---
name: motivation-and-fit
description: Use whenever the user is thinking about what motivates an individual report, how to match work to person, or why someone is engaged/disengaged. Triggers on phrases like "motivation", "what motivates them", "they seem bored", "they're disengaged", "stretch project", "they want a challenge", "they want to learn", "good fit", "wrong fit", "career growth", "they like routine", "they hate change", "they love new things", "burnout signs", "they thrive on chaos", "they need stability", "right job for them". Also use when planning project assignments, considering team composition, or trying to keep a strong performer engaged.
---

# Motivation and Fit

Source: James Stanier, *Become an Effective Software Engineering Manager*, chapter 5 ("The Right Job for the Person").

Stanier's reframe: stop trying to find the right person for the job; find the right job for the person. The chapter's three frameworks — Maslow at work, the zone of proximal development, and cathedral vs. bazaar — are the tools.

## When this skill is loaded

Identify mode:

- **Diagnostic** — someone on the team feels off (bored, disengaged, frustrated, restless)
- **Assignment** — deciding who should work on what for an upcoming project
- **Career growth** — a report wants to grow; how do you map a path?
- **Conversation prep** — preparing to discuss motivation with a report in 1-1
- **Self-reflection** — the user is wondering about their own motivation

## Maslow's hierarchy, at work

Stanier maps Maslow's five levels onto the workplace:

| Level | At work, this means |
|---|---|
| Physiological | Fair pay, reasonable benefits |
| Safety | Job security, safe environment |
| Love/belonging | Working with people you like, strong manager relationship, team belonging |
| Esteem | Recognition, appropriate title, promotions, public/private praise |
| Self-actualization | Growth, challenge, mastery, mission |

**Key insight:** the company provides the bottom two by default (mostly). Belonging, esteem, and self-actualization are *what the manager affects*. That's where your leverage is.

Concrete contributions you can make at each level:

**Belongingness:**
- Build strong relationships through 1-1s, contracting, follow-through
- Encourage radical candor — promotes trust
- Connect the team to the wider org so they feel part of something larger

**Esteem:**
- Frequent specific praise
- Honest critical feedback (rare praise without correction reads as fake)
- Career conversations about progression and titles
- Coaching that builds confidence

**Self-actualization:**
- Delegate work that stretches them (see Zone of Proximal Development below)
- Allocate budget for training and conferences
- Give them freedom to solve problems their way as long as outcomes are right
- Connect their work to mission/customer impact

**Diagnostic use:** when someone is disengaged, walk them up the hierarchy. Where does it break? Are they fairly paid? Worried about job security? Disconnected from the team? Underrecognized? Not learning? The breakage point is your fix point.

## Zone of Proximal Development (ZPD)

Vygotsky's learning theory: there's a band of tasks just beyond what someone can do alone, but achievable with help from a more knowledgeable person. That's the zone where growth happens.

```
[ Can do alone ] [ ZPD — can do with help ] [ Can't do even with help ]
```

The ZPD is where you should be assigning work to people — most of the time. As they master that zone, the boundary moves outward.

**Applying it at task level:**

- Don't always give junior engineers the easy work; give them ZPD-stretching work paired with mentorship from a senior.
- Don't always give senior engineers the hard work; sometimes give them mentorship roles to develop teaching skills.
- Pair-program ZPD-stretching tasks. The junior learns; the senior practices mentoring.
- Delegate some of your own managerial work to engineers thinking about management. Walk them through it.

**Applying it at career level — skill trees:**

Take a long-term career goal and break it into a tree of skill-level steps in their ZPD. Each step unlocks the next.

Example for "speak at an international conference":

```
[Speak at international conference]
            ↓
[Speak at local meetup]
        ↗       ↖
[Watch / meet     [Deliver monthly
 great speakers,   onboarding session
 study their       to new hires (+
 technique]        speaking course)]
        ↖       ↗
[Internal department talk]
            ↑
[Internal team talk]
```

Each node is in the ZPD given the one below. Walk through this kind of map with reports who have a far-off goal — they often can't see how to get there. Drawing the tree makes the next step actionable.

The point isn't to follow the tree rigidly. It's to make the path concrete enough that they can take the first step without it feeling impossible.

## Cathedral vs. bazaar

Borrowed from Eric Raymond's open source essay. Reframed: people are motivated by very different things.

- **Cathedral constructors** — yearn for focus, depth, mastery, stability. Become subject-matter experts. Cornerstone of teams. Build for the long term.
- **Bazaar browsers** — yearn for novelty, variety, chaos, change. Sample widely. Get bored without new challenges. Build for breadth.

**Neither is wrong.** Both are valid motivational profiles, and individuals can shift over time depending on life stage and circumstances.

**Diagnostic clue:** what did they describe as their happiest career period in their first 1-1 or contracting session? Look for words like "deep dive," "really got to know," "became the expert" → cathedral. Words like "new," "different," "got to try," "exciting" → bazaar.

**What cathedral constructors need from you:**
- Opportunity to become *the* subject-matter expert in a core area
- Long uninterrupted projects with depth
- Mentorship roles where they teach
- Distance from politics and ambiguity
- Stability — don't shuffle them between teams

**What bazaar browsers need from you:**
- First crack at new projects, new tech, new domains
- Prototyping, experimentation, build-and-throw-away work
- Permission to switch focus when they're getting bored
- Loaner arrangements with other teams when your team gets stale
- Permission to move teams if needed

**Common manager mistake:** assuming everyone wants what *you* want. If you're a bazaar browser, you'll keep handing variety to your cathedral constructor and wonder why they're frustrated. If you're a cathedral constructor, you'll keep giving the same project to your bazaar browser and watch them disengage.

This is great 1-1 material. Have the conversation explicitly: "Do you find more joy in the deep mastery of one thing, or in the breadth of trying many things? Has that shifted recently?"

## Assignment mode

When deciding who works on what:

1. **Map the team to cathedral/bazaar** — based on what they've said in 1-1s and how they've worked previously.
2. **Identify the project type** — long deep build, broad cross-system integration, novel exploration, maintenance, refactor.
3. **Match accordingly**:
   - Long deep build → cathedral, with bazaar support on connections to other systems
   - Novel exploration → bazaar, with cathedral guidance on rigor
   - Maintenance/refactor → cathedral usually thrives; bazaar resents
   - Cross-system integration → bazaar usually thrives; cathedral resents
4. **Cross-check with ZPD** — even with the right motivational match, is this task in their growth zone? If too easy, they'll cruise; if too hard alone, pair them with a senior.

## Career growth mode

When a report wants to grow:

1. Get the long-term aspiration (10 years out is fine — see career-vision-exercise skill if user wants to do this formally).
2. Translate to a 2-year aspiration. What level / role / scope?
3. Decompose into skill tree of ZPD-sized steps.
4. Pick the next 1-3 steps to focus on this quarter.
5. Identify the support they need at each step — mentorship, training budget, project assignment, visibility.

## Diagnostic mode (someone's off)

Run the three frameworks as a checklist:

**Maslow audit:**
- Pay/benefits OK? (basic)
- Job security stable? (basic)
- Strong team relationships? Strong relationship with you? (belonging)
- Feeling recognized? Title match scope? (esteem)
- Learning and growing? (self-actualization)

**ZPD audit:**
- Is current work too easy (cruising), about right (growing), or too hard (drowning)?
- Are they getting mentorship if they need it?
- Are they getting mentees if they're senior enough to need teaching outlets?

**Cathedral/bazaar audit:**
- Do they thrive on or resist variety?
- Does current work match their preference?
- Has anything shifted recently — life stage, kids, health, role change?

Whichever audit shows the misalignment, that's your conversation topic.

## Forcing functions

- **If the user is treating motivation as universal**, push for individual mapping. What works for one person can demotivate another.
- **If the user has someone who's been on the same project for 18+ months**, ask: are they thriving in depth or stagnating? Cathedral or bazaar?
- **If a report wants "a stretch project"** but the user can't articulate what's in their ZPD, that's the conversation to have first.
- **If money/title is the only lever the user can name**, walk them up the rest of Maslow. Money is necessary, rarely sufficient.
- **If the user is about to assign a project based on availability**, pause. Match motivation first. Mismatch costs more than calendar Tetris.

## What this skill should NOT do

- Don't generate generic "ways to motivate people" lists. Use the three frameworks.
- Don't psychoanalyze a report from secondhand description.
- Don't suggest a manager rigidly type-cast people as cathedral or bazaar forever — these things shift.
