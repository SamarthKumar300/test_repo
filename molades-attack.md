---
name: molades-attack
description: Breaks a student's build on purpose and then checks it against rulers instead of taste. Two passes in one skill. The stress pass runs the screen through Nothing, Too much, Wrong and Waiting after making the student predict what will fall over. The craft pass makes them declare their spacing scale, type sizes, weights and emphasis rule first, then runs five visual checks and seven accessibility checks that return PASS, FAIL or CAN'T TELL. Use after molades-build and before molades-test.
---

# Attack

Two passes on something that already works. Break it, then measure it.

**Pass one — stress.** What happens when the data isn't perfect.
**Pass two — craft.** Does it hold up visually, and can everybody actually use it.

Run both. If you're short on time, cut the number of cases inside each pass — never cut a whole pass, and never cut
the tables at the end.

> **Read `RULES.md` first.** Short replies. One question at a time. No jargon.
> **Never invent a result.** "Can't tell from a static file" is an honest answer and you should use it often.

---

## Before you start

Ask for three things in one message, then wait:

> 1. **The screen** — paste the HTML, or a screenshot, or both.
> 2. **The job** — one sentence: what does somebody come here to finish?
> 3. **Your `BRIEF.md`** if you have it. If not, the job sentence is enough.

**If there's no job sentence, get it before anything else.** Without it, "this is broken" is an opinion and you can't
grade a single finding.

---

# Pass one — stress

## Say this first

> Every prototype works with tidy data. Tidy data is the enemy, so we're going to replace it.
>
> A designer who shows one perfect screen is showing a mockup. A designer who shows the same screen under nothing,
> too much, wrong and waiting is showing a product. That difference is most of the gap between a student portfolio
> and a hired one.

## They predict first. Always.

**Before you show them anything:**

> Before I break it: name four things you think will fall over. One from each kind — nothing, too much, wrong,
> waiting. Rough is fine. Wrong is fine.

Take whatever they give you. Don't correct it yet. You score it later, and that scoring is the actual lesson.

Somebody handed a list of missing states learns nothing. Somebody who guesses four and misses six remembers all ten.

## The four kinds

| Kind | What you do to the screen | What it usually exposes |
|---|---|---|
| **Nothing** | Remove everything. First run, zero items, no results, no permission, no history | There is no empty state — the screen is a header and white space |
| **Too much** | The longest realistic name. 247 items. A nine-digit number. Six tags. Every optional field filled. Two items with the *same* name | Truncation that hides the thing you need, layouts that collapse, numbers that overlap |
| **Wrong** | Bad input, declined payment, a duplicate, something deleted in another tab while they were looking at it | There is no error state, or the error names an internal code nobody can act on |
| **Waiting** | Slow network, half-loaded, offline, request in flight, the primary button pressed twice | No loading signal, no disabled state, double submission, no confirmation that it worked |

## Build two or three real cases per kind

For *this* screen, in their domain. **Use real strings, not instructions.**

- Teaches nothing: *"use a long name"*
- Teaches everything: `Krishnamurthy Venkataraghavan Subramanian` — in their card layout

Write every case the same way:

```
THROW    [the exact content or condition — a real string, a real number]
EXPECT   [what a well-built screen would do]
ACTUAL   [what this screen does — or "can't tell from a static file"]
```

**Never guess an ACTUAL.** A stress test that invents its results is worse than none.

## Grade against the job sentence, and nothing else

- **Blocker** — under this condition the job cannot be finished at all
- **Major** — it can be finished, but wrongly, or they can't tell whether it worked
- **Minor** — it looks bad, the job still completes

**Cap the fix list at five.** More than five and nothing gets fixed. Say which five and why those five.

## Then hold up the mirror, in one line

> You predicted four of these. You missed six. The ones you missed cluster in **waiting** — that's the kind you
> don't currently think about, and it'll keep happening until you do.

## This is not a redesign

If a break can only be fixed by changing what the screen *is*, note it and say so. That's a `molades-brief` problem.
Name it, park it, move on.

## Hand back the stress table

```markdown
### Stress pass — [screen] · [date]

**The job:** [one sentence]
**I predicted:** [n] of [total]. **I missed:** [which kinds]

| Condition | What should happen | What did happen | How bad |
|---|---|---|---|

**Fixing:** [the five]
**Deliberately not fixing:** [what, and the reason]
**Couldn't test statically:** [what would need a real build]
```

Tell them to fill it in now, and say why:

> This table is one of the most convincing things you can show. It says: I knew this could break, I checked, and
> here's what I did. Nobody argues with that.

---

# Pass two — craft

## The rule this pass rests on

> You cannot fix taste, and I'm not going to try. You can fix a missing ruler. So the ruler comes first, and every
> judgement afterwards points back at it.

## Step 1 — Make them declare the rulers, before you look at anything

Ask for this first, in one message, and wait. Highest-value ninety seconds in the session.

> Before I look at anything, tell me your rules. One line each — and "I don't have one" is a real answer.
>
> 1. **Spacing** — what numbers are you allowed to use?
> 2. **Type** — how many sizes exist on this screen, and what are they?
> 3. **Weight** — how many font weights?
> 4. **Emphasis** — how many primary actions can be visible at once?
> 5. **Alignment** — how many left edges should there be?

**If they can't answer, that is the finding, and it's the biggest one in the run.** Say it plainly, and kindly:

> Nothing is wrong with your taste. You have no scale — so every spacing decision is being made one at a time, by
> eye, and they don't agree with each other. That is what "amateur" actually looks like, and it's a ten-minute fix.
>
> **Take this and move on:** spacing 4 · 8 · 12 · 16 · 24 · 32 · 48. Four type sizes maximum. Two weights. One
> primary action per view. Two left edges maximum.

Then move on. Don't debate it.

## Step 2 — The visual pass, five checks

Each one points at a ruler from step 1, which is what makes it arguable instead of personal.

| # | Check | How you check it | Fails when |
|---|---|---|---|
| 1 | **Scale adherence** | List every spacing value on the screen | Any value isn't on their scale |
| 2 | **Type count** | Count distinct font sizes | More than four |
| 3 | **Emphasis** | Count things competing to be the main action | More than one, or zero |
| 4 | **Alignment** | Count distinct left edges | More than two without a reason |
| 5 | **Rhythm** | Is the gap *between* groups bigger than the gap *inside* a group? | Inside-gap ≥ between-gap |

Explain check 5 in one line, because almost nobody knows it exists:

> Things that belong together sit closer together than things that don't. If the gap inside a group equals the gap
> between groups, there are no groups — just a list of items.

## Step 3 — The accessibility pass, seven checks

These are the ones genuinely verifiable on a static screen. Anything else is CAN'T TELL.

| # | Check | The standard |
|---|---|---|
| 1 | **Text contrast** | 4.5:1 body · 3:1 for text 24px+ or 19px bold. Compute it. Report the actual ratio |
| 2 | **Non-text contrast** | 3:1 for borders, icons, input outlines, focus rings |
| 3 | **Target size** | 44×44px minimum. Measure the hit area, not the icon |
| 4 | **Labels** | Every input has a visible label. A placeholder is not a label — it disappears on typing |
| 5 | **Colour alone** | No meaning carried only by colour. Red-for-error also needs a word or an icon |
| 6 | **Structure** | One h1, headings in order, no skipped levels. Read the markup, not the visual size |
| 7 | **Text at 200%** | Content reflows, nothing cut off or overlapped. Or CAN'T TELL |

**Report the number, not the verdict alone.**

- Worth nothing: *"contrast is a bit low"*
- Worth ten times more: `#8A8A8A on #FFFFFF = 2.9:1, needs 4.5:1 → moved to #595959 = 7.0:1`

Say this once:

> These findings are the most valuable ones in your portfolio, and the reason is boring: they are numbers. "I thought
> the hierarchy felt weak" is a taste claim anyone can dispute. "Body text was 2.9:1 against a 4.5:1 requirement, so
> I moved it to 5.1:1" is a fact. Nobody argues with a fact.

**What you may not claim:** that the screen is accessible, compliant, or done. You checked seven things on a static
file. Keyboard order, screen-reader output, motion sensitivity and anything dynamic are **CAN'T TELL** — list them
under that heading and leave them there.

## Step 4 — Five fixes, ranked

Sort every FAIL by this order and take the top five:

1. Anything that stops somebody using the screen at all — contrast failure on the primary action, an unlabelled
   required input, a target too small to hit
2. Anything that makes the screen unreadable rather than ugly — no rhythm, no emphasis
3. Everything else

Then name what's below the line explicitly.

> **Knowing what you chose not to fix, and why, is design. Fixing everything is homework.**

## Hand back the craft table

```markdown
### Craft pass — [screen] · [date]

**Rulers I set:** [spacing] · [type sizes] · [weights] · [one primary action]

| Check | Verdict | Detail |
|---|---|---|
| Text contrast | FAIL | #8A8A8A on #FFF = 2.9:1, needed 4.5:1 → moved to #595959 = 7.0:1 |

**Fixed:** [the five]
**Not fixed, on purpose:** [what, and why it was below the line]
**Couldn't check statically:** [focus order, screen-reader output, motion, anything dynamic]
```

The "not fixed, on purpose" row is the one interviewers read twice.

---

## Rewrite the document, then rebuild from it

Hand back replacement blocks for `BRIEF.md`:

```markdown
## When it's not perfect
- **empty** — [what's on screen, the one action, the actual copy]
- **loading** — [what's visible while waiting, what's disabled, or "not applicable, and why"]
- **error** — [which error, what they see, what they can do about it]
- **done** — [how they know it worked, and what stays on screen]
- **too much** — [what truncates, what wraps, what stays readable — name the element]
- **not allowed** — [hidden, greyed, or refused after the tap]

## Constraints
**Spacing scale:** [the numbers, and nothing else is allowed]
**Type scale:** [the sizes and their jobs]
**Weights:** [two, and what each is for]
**Emphasis:** one primary action per view — [name it]
**Contrast floor:** 4.5:1 body, 3:1 UI and large text
**Target minimum:** 44×44px
**Every input:** visible label above the field
**Never colour alone:** every state also carries a word or an icon
```

Then:

> Take this back to `molades-build` and rebuild from the document, not from this conversation. If you patch the HTML
> by hand, the document and the screen drift apart — and the document is the thing you can actually reuse.

---

## Log it

One `CRITIQUE` entry per finding, not one per session.

```
CRITIQUE · [date] · molades-attack · Source: self
Finding:   [what, where, under what condition]
Severity:  blocker / major / minor
Layer:     the bet / things / steps / moments / looks
Action:    [blank — filled when fixed, deferred or rejected]
```

---

## If they get stuck

**"I can't predict what will break."**
> Right now: pick the busiest thing on the screen and ask what happens if it's empty. That's one. Then ask what
> happens if there are two hundred of it. That's two. You're halfway.
>
> Nothing's missing from earlier — predicting is genuinely hard the first time and everybody misses most of them.
> That gap is the lesson, not a mark against you.
>
> After this you'll have the four kinds in your head permanently, and you'll design states before anybody asks.

**"I don't have any rulers."**
Hand them the default and move on. Do not make it a moment. It is a ten-minute fix and it is the single most
common finding in this whole pass.

**"How do I compute contrast?"**
Give them the two hex values and the ratio directly. If they want to do it themselves, name one free contrast
checker. Never ask somebody to compute it by hand.

**"There are too many findings and I don't know where to start."**
That's what the cap is for. Give them the five, in order, and say plainly what's below the line and why it can wait.

**"I don't understand rhythm."**
Take one group on their screen, measure the two gaps, and show the numbers. If you can't measure it, describe the
test and ask them to look. If it still doesn't land, find a real product screen and point at where the grouping is
obvious.

---

## Edge cases

| Situation | What to do |
|---|---|
| It's a screenshot, not code | Run the visual and contrast checks. Everything behavioural is CAN'T TELL. Say so up front |
| The screen has no interactive elements | Then the states pass is short and the craft pass is the whole run. Fine |
| Every check passes | Suspicious. Check rhythm and emphasis specifically, and check the states nobody built |
| A break is really a structural problem | Name it, park it, send it to `molades-brief`. Don't fix it here |
| They disagree with a finding | Ask for the reason. If they have one, log it as rejected with the reason — that's judgement, and it goes in the case study |
| They want to fix all thirty | Five. Say what's below the line. Fixing everything is how the deadline disappears |

---

## When it goes wrong

**You show the breaks before they predict.** Kills the entire lesson.

**You use generic edge cases.** "A long string" teaches nothing.

**You invent what happened.** Say "can't tell from a static file".

**You skip the rulers step.** Then every later judgement is your opinion against theirs, and they'll do what you said
without learning the rule.

**You give taste feedback.** If you can't name the ruler it breaks, it isn't a finding — delete it.

**You claim the screen is accessible.** You checked seven things. Say seven things.

**You list thirty issues.**

---

## Next

> Two tables, ten findings, five to fix. Next is `molades-build` — rebuild from the updated document. Then
> `molades-test`, where somebody who isn't you tries to use it.
