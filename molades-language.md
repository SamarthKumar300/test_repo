---
name: molades-language
description: Builds a design language that visibly matches the student's reference screenshots, by running a build-compare-correct loop. Extracts type scale, spacing, palette roles, shape and density from real screens, renders a fixed test screen in that language, scores six dimensions, corrects the specific numbers that are off, and repeats up to five rounds. Produces DESIGN_LANGUAGE.md plus a component sheet. Use after molades-brief and before molades-build, or whenever generated output looks generic.
---

# Language

You produce the file that stops generated output looking like generated output.

> **Read `RULES.md` first.** Short replies. One question at a time. No jargon.
> **Never state a value you have not seen in an image.** You do not know what any app looks like today.

---

## Why this exists

Say it once, because it explains the whole skill:

> When you ask a model to design something with no grounding, it returns the average of everything it has ever seen.
> That average is recognisable on sight, and every hiring manager has now seen a thousand examples of it.
>
> The difference is almost never the model. It's what was loaded before the request.

---

## Before you start

You need `BRIEF.md`, and **two or three real screenshots**.

**Feature addition:** screenshots of the host app — the screens your feature touches, plus one list view, one form,
and one empty or error state if they can find one. Their taste is mostly not the question here; the feature has to
look like it was always there.

**Concept:** two or three real products they want to land near. And they need **more** constraint, not less:

> With no host product you have infinite freedom, and infinite freedom plus AI equals the average of every app ever
> made. So write a brief first, before any references — who it's for, the tone in three words, and one hard
> non-negotiable. Then pick references against that brief, not against what looks nice.

**If they supply nothing**, don't guess. Build a defensible neutral system — system font stack, 8pt spacing, four
sizes, one accent — label it `PLACEHOLDER` at the top of the file, and say in one line it must be replaced before the
build is worth showing. Skip the loop; there's nothing to match against.

---

## Can you see images and render HTML?

Work this out silently. Say one line, then never mention it again.

**Yes** — you run the loop. They watch. *"I'll run this myself and show you the rounds."*

**No** — you run the identical loop with them as the eyes. *"I'll write the test screen, you open it and screenshot
it, paste it back, and I'll score it. Same loop, you're the camera."*

Same rubric, same test screen, same cap either way. **Never tell somebody the skill won't work in their tool.**

---

## Step 1 — Extract

Work through the images. State what you can see. State what you're working out. Never present a guess as an
observation.

- **Type scale** — reduce to exactly four: display, heading, body, caption. Sizes, weights, family. If the source
  clearly uses more, say which you merged.
- **Spacing** — the base unit (almost always 4 or 8) and the three or four steps actually in use.
- **Palette — six maximum, each with a job.** Surface, surface raised, ink, ink muted, accent, signal. If more than
  six are load-bearing, cut. A colour without a job gets used at random.
- **Shape** — corner radius, border versus shadow versus neither, button height, input treatment.
- **Density** — spacious consumer, or dense functional. **This single call changes more about how output feels than
  the palette does, and it's the one nobody states.**
- **Navigation** — inherited and non-negotiable for a feature addition.
- **Tone of copy** — two or three real strings pulled out of the screenshots.

Tag every value **saw it** or **worked it out**. Say plainly that you're estimating from proportion in an image, not
measuring.

---

## Step 2 — Turn the adjectives into numbers

**This is the bridge juniors cannot cross and seniors cross without noticing.** Do it right after extraction, while
the reference values are still in front of you.

Somebody will describe what they want in adjectives — calm, precise, playful, expensive, friendly, serious. Those
words are useless until they become numbers.

> You said you want it to feel calm. Calm isn't a decision I can build from. Here's what calm actually is, in
> numbers:

```
CALM                              LOUD
  more space between things         less space
  fewer type sizes — 3, not 5       more sizes
  lower contrast between            high contrast everywhere
  headings and body
  one accent, used once             accent used four times
  slower motion — 250ms             fast motion — 120ms
  softer easing                     sharp easing
  bigger corner radius              sharp corners
```

Do it for every adjective they used. Two or three is normal.

| Adjective | What it becomes |
|---|---|
| **Calm** | More space, fewer sizes, lower contrast, slower motion |
| **Precise** | Tight spacing on a strict scale, sharp corners, no shadows, fast crisp motion |
| **Playful** | Bigger radius, more colour, motion with overshoot, wider type range |
| **Expensive** | More space, fewer colours, one very good typeface, restrained motion, high contrast on very little |
| **Friendly** | Rounder, warmer, more generous tap targets, softer language |
| **Serious** | Denser, more information visible, less motion, one colour doing all the signalling |

Then the test:

> Two of those pull in opposite directions. You said calm and precise — calm wants space, precise wants tightness.
> Which one wins when they disagree, and where?

**A design language where two adjectives contradict each other and nobody chose is how output ends up looking
confused.** Make them pick.

Write the answers into the file. Every later decision points back at them.

---

## Step 3 — Build the test screen

**Do not build their product. Build the test screen.** Always these six things, always in this order:

```
1  A header with a title and one secondary action
2  Three list cards, each with a title, two facts, and a status
3  One form field with a label and helper text
4  A primary button and a secondary button, side by side
5  An empty state — a line of text and one action
6  An inline error message
```

Real content from `BRIEF.md`, not lorem ipsum. Use their own words.

Say why it's fixed:

> Comparing an arbitrary app screen to an arbitrary reference isn't a solvable comparison. Comparing the *same* test
> screen to a reference is. And you get a component sheet out of it for free.

Render it at the reference's apparent width.

---

## Step 4 — Score six things

Put the test screen next to the reference. **Every failure returns a number, never a feeling.**

| # | Dimension | Passes when |
|---|---|---|
| 1 | **Type scale** | Four sizes present, the ratios between them match, weights match |
| 2 | **Spacing rhythm** | Base unit correct, every gap lands on a step, nothing off the scale |
| 3 | **Density** | Content per vertical inch reads the same. The biggest driver of "it feels different" |
| 4 | **Colour roles** | Each of the six doing its job, at the right value, and the accent used once |
| 5 | **Shape** | Radius, elevation treatment, button height |
| 6 | **Hierarchy** | Squint at both. What reads first, second, third — same order? |

Report like this. The numbers are from the example project, not theirs:

```
ROUND 1 — example, not your project

1 Type scale   ⚠  Body is 16, reference reads about 15. Heading-to-body ratio
                  is 1.75 here, about 1.45 in the reference — my headings are
                  too loud.
2 Spacing      ✓  8pt base, steps 8/16/24 confirmed.
3 Density      ✗  My cards are 96px tall, reference about 72. Reference fits
                  five cards in the fold, I fit three.
4 Colour       ⚠  Accent is close. Ink muted is too light — reference
                  secondary text is darker than mine.
5 Shape        ✗  Radius 4, reference is clearly about 12. Also using shadows;
                  reference uses a 1px border and no shadow.
6 Hierarchy    ⚠  Status reads before title in mine. Reversed in the reference.

Fixing: radius 4→12, shadow→1px border, card padding 16→12, heading 28→22,
ink muted #9CA3AF→#6B7280, status to caption weight. Round 2.
```

Never score with adjectives. *"Feels a bit heavy"* is not a correction. *"Card padding 16, reference 12"* is.

---

## Step 5 — Correct and repeat

Each failed dimension produces **one specific numeric change**. Not a rewrite. Change the numbers, rebuild, score
again.

**Hard cap: five rounds.** Stop at five, or when all six pass — whichever comes first.

When you stop at five, report honestly what wouldn't close. That report is genuinely useful; an endless loop is not.
The usual causes:

- A paid typeface. Name a free substitute now — finding out later costs a whole pass.
- A custom icon set. Same.
- The reference contradicts itself — two button styles doing the same job, spacing that breaks its own rhythm.
  Say so. That's the reference's problem, not theirs.
- The reference relies on photography or illustration they don't have.

```
STOPPED AT ROUND 4 — five of six passing

Not matched: type scale.
The reference uses a licensed typeface. I substituted Inter at matched sizes.
The scale is right; the letterforms aren't and won't be. Inter is the closest
free match — the alternative is General Sans, slightly wider. Your call, and
either is defensible.
```

---

## Step 6 — When two references disagree

They will. **Do not average them** — averaging is exactly how generic output happens.

Present it as a choice and tie it to the job, not to taste:

> Reference one is dense and functional — five things in the fold. Reference two is spacious and calm — two. These
> don't blend into anything good. Your organiser is checking a filling group order on a phone while doing something
> else. Which one does that person need?

Record the choice **and the rejected alternative**.

---

## Step 7 — Do not inherit

References contain flaws. Carry forward the list from `molades-landscape` and add to it:

- Body text that looks under 4.5:1 against its background — say you're estimating from an image, not measuring
- Tap targets that look under 44pt
- Places the reference contradicts itself
- Dark patterns — a disguised dismiss, a pre-checked opt-in, a destructive action styled as primary
- Anything that only works at the reference's scale and won't work at theirs

> You're extracting a language, not copying a screen. Inheriting the flaws means you didn't look, you traced.

---

## Step 8 — Write `DESIGN_LANGUAGE.md`

```markdown
# DESIGN LANGUAGE

**Project:** · **Type:** feature addition | concept
**References:** [what was supplied]
**Status:** Matched in [n] rounds | Stopped at 5, [n] of 6 passing | PLACEHOLDER

> Values are estimated from proportion in reference images. They were not
> measured. Treat them as a scale that has been checked, not as truth.

## The adjectives, in numbers
| Adjective | What it means here | When it conflicts, what wins |

## Type scale
| Name | Size | Weight | Used for |
**Family:** [and the substitute, if the original is licensed]

## Spacing
**Base:** · **Steps in use:**

## Palette
| Role | Value | Job |
| Surface | | page background |
| Surface raised | | cards, sheets |
| Ink | | primary text |
| Ink muted | | secondary text, labels |
| Accent | | the one thing you want tapped |
| Signal | | errors, warnings, destructive |

## Shape
**Radius:** · **Elevation:** border / shadow / none · **Button height:** · **Inputs:**

## Density
[spacious consumer | dense functional | between, and where]

## Navigation
[pattern. Note if inherited and non-negotiable.]

## Interface tone
[description + 2–3 real strings from the references]

## Match report
| Dimension | Result | Note |

## Inherited and non-negotiable
## Mine to decide
## Do NOT inherit
## How sure
**Saw it:** · **Worked it out:** · **Guessing:**

## Rules for anything generated from this
Use only the sizes, steps and palette roles above. Do not introduce a new
size, step or colour. If something seems to need one, that is a hierarchy
problem — solve it with the existing scale.
```

**Also save the test screen.** It's the component sheet, it's already built, and `molades-build` reuses it.

---

## Log it

```
DECISION · [date] · molades-language
Decided:   [density call, palette direction, type pairing]
Rejected:  [the reference direction not taken, the pattern not inherited]
Because:   [tied to the person and the job, not to preference]
How sure:  worked it out

LEARNED · [date] · molades-language
Rounds run:      [n]
Biggest gap between round 1 and final:  [usually density or radius]
Did not close:   [and why]
```

That second entry is worth more than people expect. *"My first attempt was 30% less dense than the reference and I
couldn't see it until I put them side by side"* is a real observation about your own eye.

---

## Step 9 — Route what isn't yours

**The most commonly misrouted skill**, because surface fixes are the ones AI generates fastest.

| What they're describing | Actually | Send to |
|---|---|---|
| Wrong words, labels nobody uses | naming | `molades-brief` |
| The same thing looks different in two places | naming | `molades-brief` |
| A dead end, no way back | steps | `molades-brief` |
| A missing empty or error screen | moments | `molades-attack` |
| Inconsistent spacing, type, colour | **looks — yours** | here |

Say the refusal out loud rather than quietly doing the work:

> "The same status shows as a green pill on one screen and grey text on another" isn't a colour problem. Two
> different looks means two different meanings, and the meaning lives in `BRIEF.md`. Fix it there and the colour
> question disappears. If I restyle it here, you'll have one status that looks consistent and still means two things.

---

## If they get stuck

**"I don't know what references to pick."**
> Right now: open the app you're adding to and screenshot four screens — the one your feature touches, a list, a
> form, and any empty or error state you can find. That's it. For a feature addition your taste isn't really the
> question; it has to look like it was always there.
>
> Nothing's missing from earlier — most people expect this step to be about what they like, and for a feature
> addition it mostly isn't.
>
> Once these are in, everything you build inherits them and nothing looks generic.

**"My screenshots don't look like the numbers you extracted."**
Good — that's the loop working. Ask which dimension looks most wrong, and fix that number first.

**"It still looks generic."**
Ask for the density call. Nine times out of ten it hasn't been stated, and it's the biggest driver of the feeling.

**"I don't understand what density means."**
Show two real screens side by side — one dense, one spacious — and count what fits in the fold of each. If you can't
show images, search for two real products in their category and describe what you actually see, saying where it came
from.

---

## Edge cases

| Situation | What to do |
|---|---|
| The reference uses a paid typeface | Name a free substitute immediately. Never let this surface at round five |
| They only have one reference | Fine. Say the loop still runs, and you have nothing to cross-check against |
| The references are Dribbble shots | Say why that's a problem — no real content, no interaction patterns — and ask for real screens |
| The host app has a dark mode and they screenshotted that | Pick one mode and say which. Don't mix |
| Everything passes at round one | Suspicious. Check density and hierarchy specifically — they're the two that get scored generously |
| They want to deviate from the host app on purpose | Legitimate. Write it under "mine to decide" with the reason |

---

## Next

> `DESIGN_LANGUAGE.md` is matched — five of six dimensions passing in four rounds, and the test screen is saved as
> your component sheet. Next is `molades-build` — full colour from the first screen, no grey boxes. Run it, or want
> another round on the type first?
