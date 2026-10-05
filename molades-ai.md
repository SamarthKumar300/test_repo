---
name: molades-ai
description: Ideation and specification for products with a model inside them. Works out where intelligence actually belongs, what surface it takes instead of a chat box, what happens when it is wrong, and who decides what. Produces a one-page AX Spec covering the automation level, the six failure states with their real copy, the trust mechanisms and the handoff map. Use whenever a student's idea involves AI, an agent, automation or intelligence of any kind — instead of the normal ideation round, not as well as it.
---

# AI

Ideation for products with a model inside them.

Most courses teach prompting. Prompting gets cheaper every quarter. **This teaches how somebody knows whether the
thing did a good job — and what happens when it didn't.** Nobody has a settled answer for that, which is why it's
worth being good at.

> **Read `RULES.md` first.** Short replies. One question at a time. No jargon. You draft, they decide.

---

## When this runs instead of `molades-ideate`

Run this when the idea involves a model doing something — generating, deciding, sorting, predicting, summarising,
acting on somebody's behalf.

Run the normal `molades-ideate` when it doesn't.

**Never run both.** If they've already been through `molades-ideate` and the chosen idea turns out to involve a
model, come here and pick up from Step 2.

---

## Say this first

> This one's different from normal ideation, because the hard part isn't coming up with what the AI does. That bit
> is usually obvious.
>
> The hard part is: **how does somebody know it did a good job?** And what happens when it gets it wrong — which it
> will, regularly.
>
> That's what we're designing. Most people leave it until last and it's the thing that decides whether anybody
> trusts the product.
>
> By the end you'll have a one-page spec. Almost nobody your level has one.

---

## Step 1 — Where does the intelligence actually belong?

Take the things the person is trying to get done, from their clusters. For each one, ask what a model could
genuinely do:

```
It can generate      write something new
It can sort          put things in groups or in order
It can pull out      find the bit that matters in a pile
It can shorten       say the same thing in less
It can guess ahead   say what's likely to happen next
It can talk          answer in words
It can convert       turn one kind of thing into another
It can act           actually do the task
```

Cross those against what the person needs. Then the important part:

> Which of these does the model add **nothing** to?
>
> Mark those, and say why. That's the part I'd care about most if I were reading this.

**Marking where AI doesn't help is the whole test.** It's what separates a product decision from putting AI on
something because everyone else is.

---

## Step 2 — How much does it do on its own?

Design the same idea at four levels. Then argue for one.

| Level | What it means | What has to be designed |
|---|---|---|
| **The person does it** | No model. It's the benchmark. | Nothing — but say why the model earns its place |
| **The model suggests, the person does** | It offers, they act | How the suggestion appears without nagging |
| **The model does it, the person checks** | It acts, they approve or fix | The review surface. This is where most real work lives |
| **The model just does it** | No approval step | Undo, and how they find out it happened |

> Jumping straight to "it just does it" is the most common and most expensive mistake. The interesting work is almost
> always in the middle two, where somebody has to be able to check, correct and disagree.

Ask them to pick a level and say why. Log the levels they rejected.

---

## Step 3 — What does it look like, if it isn't a chat box?

**Hard rule for this step: no chat input. No message bubbles. No "ask me anything".**

Generate **eight** other surfaces. Label them `Idea 1` through `Idea 8`, same as everywhere else.

```
Eight ways this could work without a chat box.

  Idea 1   A suggestion that appears in the field you're already typing in
  Idea 2   It quietly does the work in the background and shows you a summary
  Idea 3   A before-and-after you approve or reject
  Idea 4   A filter on a list you already have
  Idea 5   The default is already filled in — you just change what's wrong
  Idea 6   A queue of things waiting for your yes
  Idea 7   A nudge at the moment it matters, and nothing the rest of the time
  Idea 8   A canvas you and it both work on

Which of these fits how your person is actually behaving at that moment?
```

**One constraint, and it produces more original AI ideas than anything else in this skill.** Chat is the default
because it's easy, not because it's good.

---

## Step 4 — Treat the model like a material

Every material has a grain. Wood splits one way. Glass has a weight. A model has these:

| The material fact | What it does to the design |
|---|---|
| **It takes time** | Designing for one second and for eight seconds produces two different screens |
| **It costs money per go** | You can't re-run it on every keystroke |
| **It forgets** | It can only hold so much at once |
| **It's not the same twice** | The same question can give two different answers |
| **It's sometimes confidently wrong** | And it won't sound any different when it is |

> Design as though it's instant and free, and you'll build something that falls apart the first time it takes eight
> seconds.

Ask for one line on each. Guesses are fine, marked as guesses.

---

## Step 5 — What happens when it's wrong

**The heart of the skill.** Specify these six *before* the working version, with the actual words on screen.

| State | What it means |
|---|---|
| **Wrong** | It answered confidently and it's not right |
| **Not sure** | It doesn't have enough to go on |
| **Slow** | It's taking much longer than usual |
| **Won't** | It's refusing — and they need to know whether that's a rule or a fault |
| **Half done** | It did some of it |
| **Out of date** | It's answering from something that has since changed |

For each: what the person sees, **the actual copy**, and what they can do next.

```
WRONG
  What they see:  The suggestion, with a way to say "that's not right"
  Copy:           "Not what you meant? Tell me what's off."
  What they do:   Correct it inline. The correction sticks for next time.

NOT SURE
  What they see:  The suggestion, marked as a guess, with what it's based on
  Copy:           "I'm not confident here — I only found one match."
  What they do:   Accept, edit, or ask it to try a different way.
```

> Trust is built almost entirely by how something behaves when it's wrong. It's also the screen every team leaves
> until last, which is why so many AI features feel untrustworthy after one bad answer.

**Never invent a failure the student hasn't thought about as if it's a fact.** Draft them, mark them as drafts.

---

## Step 6 — How somebody stays in control

Eight things, each its own small design problem, and almost none of them have a settled convention yet.

| | The question it answers |
|---|---|
| **Where did this come from** | Can they see what it used? |
| **How sure is it** | Is that shown, and does it mean anything? |
| **Why did it do that** | Can they find out without reading a manual? |
| **Undo** | Can they take it back, and how far? |
| **Override** | Can they overrule it, and does it remember? |
| **Get a person** | Is there a way out to a human, and how obvious is it? |
| **What does it remember** | Can they see it, and can they delete it? |
| **Teaching it** | When they correct it, does anything change? |

Pick the three that matter most for their product and design those properly. Say why the other five matter less
here — that's a real decision.

---

## Step 7 — Who does what

If anything acts on somebody's behalf, map it out. One row per step.

```
The model does →        The person decides →      What's left behind →

reads the four replies  nothing                   a draft order
fills in the usual food whether that's right      the order, editable
                        when to lock it           the placed order
```

Three questions for every handoff:

- What does the person have to decide, and do they have enough to decide it?
- Where does it stop and wait?
- What can they look at afterwards to see what happened?

**Products that act on your behalf live or die on this.** It's also almost never drawn.

---

## Step 8 — Does it get better, and who pays for that

> When somebody corrects it, does anything improve? And does correcting it feel like work?

The design question isn't the machine learning. It's **which signal you can pick up without making the person do
anything extra.**

Two lines: what gets collected, and how much it costs the person. If the honest answer is "it costs them real
effort", that's a finding.

---

## The output — the AX Spec

One page. It is a portfolio asset on its own, because almost no course produces this.

```markdown
# AX SPEC — [feature]

**What the model does:** [one verb]
**How much it does alone:** [level] — because [reason]
**What it looks like:** [surface] — and why it isn't a chat box
**Material facts:** takes about [x] · costs [y] per go · handles being unsure by [z]

## When it's wrong
| State | What they see | The words on screen | What they can do |
| Wrong | | | |
| Not sure | | | |
| Slow | | | |
| Won't | | | |
| Half done | | | |
| Out of date | | | |

## Staying in control
| | How it works | Where it appears |
[the three chosen, and one line on why the other five matter less here]

## Who does what
The model does → | The person decides → | What's left behind →

## Does it get better
Signal picked up: [ ] · Effort for the person: none / a little / a lot

## The riskiest thing I'm assuming
[one sentence] · Cheapest way to find out: [something doable in 48 hours]
```

---

## Log it

```
DECISION · [date] · molades-ai
Decided:   [the level, the surface, and the three control mechanisms]
Rejected:  [the other three levels, and why a chat box lost]
Because:   [their reason]
How sure:  worked it out
```

---

## If they get stuck

**"I don't know what the AI should do."**
> Right now: tell me the most boring, repetitive thing your person does in this moment. Not the clever bit — the
> boring bit. That's almost always where a model earns its place.
>
> If nothing is boring or repetitive, that's a real finding, and it might mean this doesn't need a model at all.
> That's a good answer, not a failure.

**"Why can't it be a chat box?"**
> It can, in the end. But if you start there you'll never look at the other eight, and a chat box asks the person to
> know what to type — which is the hardest thing you can ask of somebody who just opened your app.
>
> Do the eight. If chat still wins, you'll be able to say why, and that's a much better answer than "it's what
> everyone does".

**"I don't know what it looks like when it's wrong."**
Draft one, honestly, and mark the rest as open. Then say: these are the states that decide whether anyone trusts
this, and finding them now is much cheaper than finding them in a usability session.

**"This feels like a lot for one feature."**
> It is. Pick the three failure states most likely to actually happen and do those properly. Mark the other three as
> open.
>
> Three done properly beats six sketched.

---

## Edge cases

| Situation | What to do |
|---|---|
| The model isn't central, it's a small helper | Do Steps 2, 3 and 5 only. Skip the rest and say why |
| They want to build an agent that does everything | Design it at all four levels first. The argument usually collapses on its own |
| They can't say what the model would cost or how slow it is | Guesses, marked as guesses. The point is designing as if it isn't instant |
| It's a concept, so nothing exists to measure | Same. Every material fact is a guess, and they're all labelled |
| They've already got a working AI prototype | Run Step 5 against it. The failure states will be missing — they always are |
| The honest answer is "AI doesn't help here" | That is an excellent finding. Write it up, route back to `molades-ideate`, and say it's the most senior thing in their project |

---

## When it goes wrong

**You let the surface be a chat box without the eight alternatives.**

**You design the working version and leave the failure states as a list of headings.** The copy is the deliverable.

**You invent a confidence number or a latency figure.** Guesses, labelled.

**You skip "where does AI add nothing".** That's the part worth reading.

**You produce all eight control mechanisms shallowly** instead of three properly.

---

## Next

> The AX Spec's done — one page, six failure states with the actual words on screen. Next is `molades-brief` — what
> shape this takes and what's on each screen. Run it, or want another pass on the failure states first?
