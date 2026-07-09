+++ 
draft = true
date = 2026-07-08T15:00:00+01:00
title = "The Rewrite That Ate Two Years and Shipped Nothing"
description = "Every operator gets this call: the strategic rewrite that's become a money pit with no end date. When to kill it, when to finish it, and why 'it's quick to build' is the most expensive sentence in engineering."
slug = "the-rewrite-that-shipped-nothing"
authors = ["Klaas Ardinois"]
tags = []
categories = []
externalLink = ""
series = []
+++

There's a call an operator gets more than any other. It starts with a version of: "we've got this rewrite, it's been going for a while, and I'm not sure where it's landed."

"A while" is usually two years. "Not sure where it's landed" almost always means nowhere. And by the time someone external is being asked, the board has already noticed that a very expensive project has produced a great deal of activity and no shippable outcome.

So let's talk about rewrites. Not how to do them — there's plenty of that. Let's talk about the decision that actually matters: **whether to do one at all.**

## "It's quick to build" is the most expensive sentence in engineering

Let me tell you about a rewrite I killed.

The team wanted to build our own CMS. And I understood the impulse — I really did. They weren't in love with our vendor. The platform had quirks, it wasn't entirely fit for our purpose, and every engineer had a small collection of scars from working around it. When you live with a tool's rough edges every day, replacing it feels obvious.

Their case rested on three words: **"it's quick to build."** And they weren't even wrong about the build. For the specific slice of functionality we actually used, a competent team could stand up something workable in a reasonable window.

But that's the trap. The build is the *cheap* part.

What their case completely ignored was the total cost of ownership. The vendor wasn't just giving us a CMS — they were absorbing an enormous amount of work we'd never see. Security patching. Accessibility compliance. Browser compatibility. The feature we didn't need today but would need next year. The 2am page when something breaks, answered by *their* on-call instead of ours. The upgrade treadmill. All of it, forever, priced into a subscription we grumbled about.

Build it ourselves and every one of those becomes our problem, in perpetuity, on our payroll. _(sidenote: the quirks we hated? A homegrown system has quirks too. They're just **our** quirks, and now we can't file a support ticket about them.)_

So I asked the team to re-run their case with the maintenance line included — honestly, over five years, not just the heroic first sprint. The project didn't survive contact with its own TCO. We kept the vendor, negotiated harder, and spent the engineering time on things that actually differentiated us.

The lesson generalises: **almost every doomed rewrite is costed as a build and lived as an ownership.** If the business case only survives when you ignore what it costs to *keep* the thing alive, it's not a business case. It's an enthusiasm.

## Kill, box, or finish

When I'm brought into a rewrite that's already in flight, there are only three outcomes, and the job is to work out which one honestly applies.

**Kill it.** The most common right answer, and the hardest to say out loud, because someone senior sponsored it and two years of sunk cost is staring back at you. Sunk cost is not an argument. The only question that matters is forward-looking: from here, is finishing worth more than stopping? Often it isn't.

**Box it.** The rewrite had a good core idea buried in an over-ambitious scope. Cut it back to the one piece that genuinely earns its keep, ship *that*, and abandon the rest. Half a rewrite that ships beats a whole one that doesn't.

**Finish it.** Sometimes the thing really does need to happen and the team was just missing structure, not merit. In which case — and only in which case — you commit properly. Which brings me to the part everyone skips.

## Why this is easier for an outsider to say

There's a human factor here that's easy to wave away, and it matters enormously.

The team that's spent two years on the rewrite can't kill it. Not won't — *can't*. Their credibility is welded to it. The exec who signed off on the business case has their name on it. Everyone in the room has a personal history with the decision, and that history quietly bends every judgement toward "let's give it one more quarter." Sunk cost isn't only financial. It's reputational, and reputation is far stickier than money.

An outsider carries none of that. No scars, no sponsor to protect, no faction to keep onside. They can look at exactly the same facts and say the unsayable — "this should stop" — precisely *because* they have nothing at stake in saying it. In this situation independence isn't a nice-to-have. It's the entire value.

Which is the quieter reason a CEO brings someone in. It isn't only the assessment — a capable internal team could probably produce that. It's that an independent recommendation makes a hard decision *possible*. The call stops being "the CEO overruling two years of their own team's work" and becomes "acting on a dispassionate outside read." That reframing is worth a great deal. It lets good people change course without anyone having to lose face.

## Preparing for the rewrite is as important as the rewrite

The rewrites that die didn't fail in the rewriting. They failed before a line was written, because nobody did the preparation.

Preparation is unglamorous, which is exactly why it gets skipped in the rush to the exciting greenfield part. But it's where the project is actually won or lost:

- **Understand what you're replacing — properly.** The messy old system encodes years of hard-won edge cases and business rules nobody remembers deciding. If you can't explain *why* it does the weird thing it does, you will faithfully rebuild the bug and lose the feature.
- **Find the seams.** Where can you cut the system so you can replace it in pieces? A rewrite you can ship incrementally is a rewrite that de-risks itself. A big-bang cutover is a bet-the-company event dressed up as an engineering task.
- **Define "done" before you start.** Not "it's better" — a concrete, testable line. Rewrites without a finish line don't have one by accident. They have one because "better" is infinite and the team will chase it until the money runs out.
- **Ship value on the way, not at the end.** If the first customer-visible benefit lands eighteen months in, you've built a two-year window in which the project can be cancelled and shows nothing for it. Sequence so that value arrives early and often — it funds the political capital you'll need to finish.

Do this work and the rewrite is almost boring. Skip it and you've bought yourself the exact call at the top of this post.

## Cost is only half the conversation — value is the other half

Here's where operators earn their keep with a board.

Engineers instinctively argue rewrites on cost and risk: "the old system is fragile, it'll cost us if it breaks." All true, and all unpersuasive, because a board can't act on "might be bad." You have to articulate the **value** — what does fixing this actually unlock or protect? Faster feature delivery? A compliance requirement that gates an enterprise deal? A cost curve that finally bends the right way? _(this is the same discipline as tracking [engineering capex]({{< relref "engineering-capex-opex.md" >}}) — you're translating engineering reality into a language the board can allocate capital against.)_

And once you frame it as value rather than tidiness, something uncomfortable falls out: **for a lot of things, the value of fixing them is close to zero.**

## Some fires are better left burning

Not everything needs fixing.

There's a particular kind of module — ugly, a bit embarrassing, held together with tape — that nonetheless *works* and *almost never changes*. Every engineer who touches it wants to rewrite it. And they're wrong, because they're optimising for elegance in a place the business doesn't care about.

Some things are better left burning. You keep an eye on them, and every so often, when the smoke gets a little thick, you walk over and douse them with a bucket of water — back down to a manageable smoulder. Then you leave them alone again.

That's not neglect. That's judgement. A rewrite is only worth it when the thing is broken **and** load-bearing **and** actively changing. Miss any one of those and you're spending your best engineers' time making something prettier that no one will ever thank you for. Ugly and stable is a perfectly good state for code to live in.

The operator's job was never to make everything beautiful. It's to know which fires are worth the fire brigade — and which ones just need a bucket of water and to be left alone to smoulder.
