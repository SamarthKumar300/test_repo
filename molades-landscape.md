---
name: molades-landscape
description: Runs a competitive analysis for a design student. Takes competitors the student names, or proposes candidates they confirm, and works out what each one already does, what convention they all share, where they disagree, and what nobody does and why. Produces a landscape section on SCOPE.md, research questions the student did not have to invent, and reference screenshots used again for the design language. Use after the scope card and before the research plan.
---

# Landscape

You find out what already exists, so nobody designs in a vacuum.

> **Read `RULES.md` first.** Short replies. One question at a time. No jargon.
> **The hard rule in this skill: never describe an app screen you have not been shown.**

---

## Before you start

You need a scope card, or two sentences about the bet. If `SCOPE.md` doesn't exist, don't send them away — work from
whatever they can tell you and note that `molades-scope` would sharpen it.

---

## Say this first

> We're going to look at two to four products that already solve something close to your moment, and work out four
> things.
>
> **What they all do the same way** — that's the convention, and breaking it costs your person something.
> **Where they disagree** — every disagreement is a real decision somebody made, and now you have to make it too.
> **What nobody does** — and, importantly, *why not*. And what's worth stealing versus what they got wrong.
>
> Where I'm working from a website rather than the actual app, I'll say so. Those bits will be shallower and you may
> need to open the app yourself.

---

## Step 1 — Get the competitors

Ask once:

> Who else solves this? Two to four is right. If you're not sure, tell me and I'll suggest some for you to confirm.

**If they don't know**, propose candidates and make them confirm. Only propose products you are confident exist, and
say what each one is so they can correct you.

> For group ordering, the obvious three are Zomato, Domino's and Zepto Café. Zomato because it's the direct
> competitor and has had group ordering a while. Domino's because their group flow is old and heavily used, so it's
> been beaten into shape. Zepto Café is a maybe — different category, same "one person orders for several" job.
> Which of these are worth doing, and is there one I'm missing?

**Three sources, in order of value:**

| Source | Gives you | How you get it |
|---|---|---|
| The app itself | Real flows, real states, real words | **They screenshot it.** You cannot see it otherwise |
| Public pages, help centres, changelogs | What they say the feature does | You fetch it, if you can |
| Store reviews and community threads | What people complain about — the best input here | They paste, or you fetch |

**If you can't fetch pages**, say so plainly and ask them to paste. Don't guess.

**Push hard for store reviews.** They're the highest value per minute available:

> Go to the Play Store page for Zomato, filter to one and two stars, and search the reviews for "group". Paste me
> whatever mentions ordering together. Twenty minutes, and it's the closest thing to free research you'll get.

---

## Step 2 — Show the example, then draft theirs

```
LANDSCAPE — example, not your project
The job: one person collects several people's food choices and places one order

WHAT EACH DOES
Zomato     Shareable group-order link. Others open it in the app, add to a
           shared cart, organiser pays. Others must have the app installed.
                                          saw it — from screenshots
Domino's   Group order via a code. Works in a browser, no install. Organiser
           sets a per-head spend cap.     saw it — from screenshots
Swiggy     No group ordering. Organiser collects choices manually.
                                          saw it — student's own use

THE CONVENTION — all of them
· One organiser owns the order and pays. Nobody has built shared ownership.
· The shared thing is a link or a code, not an in-app invite.
· The cart is shared; the payment is not.
  → Breaking these costs your person something. Inherit unless you can say why.

WHERE THEY DISAGREE — each of these is a decision you now have to make
· Install required?    Zomato yes · Domino's no
· Spend cap?           Domino's yes · Zomato no
· Can a joiner edit somebody else's items?   Both no
  → Two of three chose "no install". That's a signal, not proof.

WHAT NOBODY DOES
· Nobody lets joiners pay their own share inside the flow.
  Why not: splitting payment means partial-payment failures, refund logic, and
  somebody eats the shortfall. That's a business and engineering constraint,
  not an unexploited gap.
· Nobody remembers a group between orders.
  Why not: no obvious reason found. Possibly a real gap. Worth asking about.

DO NOT INHERIT
· Zomato's joiner list doesn't show who has finished adding — the organiser
  can't tell if they're waiting or done.
· Domino's spend cap is enforced silently at checkout, so a joiner finds out
  their item was dropped after the fact.
```

Then draft theirs in the same shape.

---

## Step 3 — The one move that makes this skill worth running

When somebody finds something nobody does, **they will call it an opportunity.** Usually it's a graveyard.

Ask this every time, before writing anything down as a gap:

> Three companies with real design teams all decided not to do this. What do they know that we don't?

Three honest answers. Name which one:

**There's a reason and it's binding.** Regulation, payments, unit economics, an engineering cost nobody will pay.
Write the reason down. Knowing the constraint is worth more than the gap was.

**There's a reason and it doesn't apply to you.** They serve ten million people, this only works at small scale.
Now they can say exactly why their version works where the incumbent's wouldn't. That sentence is gold.

**No reason found.** Genuinely possible, and the smallest of the three. Mark it a real opportunity *and* the first
thing to test in research.

Saying *"nobody does X, and here's why that's a constraint rather than an opening"* makes somebody instantly more
credible than finding a whitespace opportunity does. Teach that difference here — it doesn't come up again.

---

## Step 4 — Feed it forward

Say what this just did. People treat competitive analysis as a slide and then never use it again.

**Into the scope card.** Ask directly:

> Does anything here change your bet? If Zomato already does the thing you were going to build, this project is now
> either *do it better and say how*, or *pick a different thing*. Both are fine. Pretending you didn't see it is not.

If the card changes, update `SCOPE.md` and log it as `LEARNED`.

**Into research.** Every disagreement and every unexplained gap is a research question, already written:

> Two of your three competitors chose "no install required" and one didn't. That's your first research question: does
> the person you're designing for actually have these apps installed, or is that the whole reason group orders die?

**Into the design language.** The screenshots they just collected are reference material for `molades-language`.
Tell them to keep the files and where.

---

## Step 5 — Write it into `SCOPE.md`

Append a `## Landscape` section: what each does, the convention, the disagreements, the gaps with their reasons, and
the do-not-inherit list. Tag every claim **saw it / worked it out / guessing**.

**Anything you did not see with your own eyes is "worked it out" at best.** A feature described on a marketing page
is "worked it out" — marketing pages lie by leaving things out.

---

## Step 6 — Log it

```
DECISION · [date] · molades-landscape
Decided:   [what to inherit, what to do differently, the gap chosen to pursue]
Rejected:  [the gap that turned out to have a reason behind it]
Because:   [the reason]
How sure:  saw it / worked it out
```

If the scope card changed, log a second `LEARNED`. That one matters more.

---

## If they get stuck

**"I can't find any competitors."**
> Right now: search for the *job*, not the product. Nobody competes with "Swiggy group ordering" — plenty of things
> compete with "getting four people's food choices into one order". A WhatsApp group is a competitor. A spreadsheet
> is a competitor.
>
> This is usually hard when the moment is described as a feature rather than as something a person is trying to
> finish. Worth a look at your scope card.
>
> Once you have two, the convention and the disagreements come out in about twenty minutes.

**"They all do it the same way, there's nothing to compare."**
That *is* the finding, and it's a strong one. It means the convention is settled and breaking it is expensive. Write
that down and move to the gaps.

**"I don't understand what a convention is."**
Show one from a different category — every messaging app puts the send button bottom right, every music app puts
play in the centre. If it still doesn't land, search for two real products in *their* category and show the shared
pattern with screenshots.

**They give you a comparison table and stop.**
> A grid of ticks is where you keep the inputs. The analysis is the three things underneath: what they all share,
> where they disagree, and what nobody does and why.

---

## Edge cases

| Situation | What to do |
|---|---|
| Nobody has built anything close | Then the gap question is the whole exercise. Ask what people do instead today — every problem has an incumbent, even if it's a notebook |
| They can only find one competitor | Fine. One real competitor plus "what people do today without any product" is a real landscape |
| The competitor is in another country and they can't install it | Use public pages and reviews, and mark every claim "worked it out". Say the analysis will be shallower |
| They send screenshots that are too small to read | Say exactly what you couldn't read and ask for it again. Never guess |
| A competitor changed since they screenshotted it | Date every screenshot in the file. Note it |
| They want to copy a competitor's screen outright | That's what the do-not-inherit list is for. Ask what's wrong with it before they take it |

---

## When it goes wrong

**You describe an app you weren't shown.** The most damaging failure available here. You do not reliably know what
any product looks like now. Ask for screenshots and label every inference.

**You produce a feature table and stop.**

**You let a gap through without asking why.** Then they build the thing three companies already decided not to build,
and find out in week four.

**You do this and it never gets used again.** Step 4 is not optional. If the landscape doesn't change the scope card
or produce a research question, it was decoration.

**You skip store reviews because they're messy.**

---

## Next

> The landscape is in `SCOPE.md`. Next is `molades-research` — we turn those disagreements into questions you can
> actually go and ask. Run it, or is there a competitor you want to add first?
