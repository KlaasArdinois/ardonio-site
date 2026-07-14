+++ 
draft = false
date = 2026-07-14T08:00:00+01:00
title = "The Rewrite That Ate Two Years and Shipped Nothing"
description="The two-year rewrite that has produced no shippable outcome. How to decide whether to kill it, box it, or finish it, and why the build was never the cost."
slug = "the-rewrite-that-shipped-nothing"
authors = ["Klaas Ardinois"]
tags = []
categories = ["playbook"]
externalLink = ""
series = []
+++

There is one conversation I have had more than any other when meeting boards. The phrasing varies, but it boils down to: "For a while now we're going through a rewrite, cleaning up technical debt, and at this point we're not quite sure where it's going."
Variants include "it's behind schedule" and "it's a waste".

"A while" is usually about two years. "Not sure where it's going" almost always means nowhere. And by the time someone external is being asked, the board has already noticed that a very expensive project has produced a great deal of activity and no shippable outcome.

And more often than not it's followed by a solution that sounds a lot like "should we just buy _<other company/tech>_ to speed it up?".

So let's talk about the decision that matters here: **should you be rewriting at all?**

## "It's quick to build" is the most expensive sentence in engineering

Quick story to illustrate my point.

The team wanted to build an in-house CMS. At that point we had already spent years with a third party that wasn't quite fit for purpose. We had bastardized the software for a tangential but not core purpose, scaffolded some workflows against it, written custom code to extend it where it truly lacked. And as any enterprise system, the UX had the typical quirks (oh yeah ... that one page we need all the time...yeah that is always a 20-second load time. They can't fix it) that make using the system every day a debilitating experience.  

So we had both real technical scars, and a lot of emotional damage in our colleagues. 

The key here wasn't that it was a bad platform by any measure, it was simply a textbook example of drifting into failure. Lots of small decisions, each one benign and justifiable in its own right, that over time decay into an untenable mess.
But when you live with that every day and you are no longer the person who remembers why we drifted here, there is a point where "rip it out, replace it" starts to sound incredibly attractive.

Their case ultimately rested on one deadly phrase: **"it's a simple system that is quick to build."** 

And they weren't even wrong about the build. For the specific slice of functionality we actually used, a competent team could stand up something workable in a few weeks. These days with AI-assisted coding, it's probably a day or two at most.

But that's the trap. The build is the *cheap* part.

What their case completely ignored was the total cost of ownership. The vendor wasn't just giving us a CMS. Instead they were absorbing an enormous amount of work we'd never see. The typical ongoing maintenance to fight the natural decay of software. Security patches, small bugfixes, browser compatibility, logging & auditing, database backups, on-call support so every end-user question doesn't hit one of our engineers. The sort of things you only notice when they don't happen. All conveniently priced in a few seat licenses.

Build that ourselves and every one of those becomes our problem, in perpetuity, on our payroll.

 _And those quirks we hated? A homegrown system has quirks too. They're just **our** quirks, and now we can't file a support ticket about them._

So I asked the team to go back and re-run their case, but extend it from "quick to build", to "build, maintain, operate for five years". The whole project didn't survive the first round once it met TCO. It did give us a good baseline to negotiate with our vendor, and then repurpose our engineering time on things that actually differentiated our product.

The lesson more generally: **almost every doomed rewrite is costed as a build and a rampdown, rather than a true ongoing maintenance.** If the business case only survives when you ignore what it costs to *keep* the thing alive it's a hobby project for enthusiasts.

## Finish, box, kill

So now when I'm seeing a rewrite in flight, there are really only three outcomes of the inspection. The hard part is working out which one honestly applies.


**Finish it.** Sometimes the thing really does need to happen and the team was just missing structure, not merit. In which case, and only in which case, you commit properly. 

**Box it.** The rewrite had a good core idea buried in an over-ambitious scope. Cut it back to the one piece that genuinely earns its keep, ship *that*, and abandon the rest. Half a rewrite that ships beats a whole one that doesn't.

**Kill it.** The most common right answer, and the hardest to say out loud, because someone senior sponsored it and two years of sunk cost is staring back at you. Sunk cost is not a rational argument, but it is hard to get over emotionally. The only question that matters is forward-looking: from here, is finishing worth more than stopping? Often it isn't.

There's a human factor here that's easy to wave away in writing, but hard to ignore when you're in the room.

The team that's spent two years on the rewrite can't kill it. Read that again: *can't*. Their credibility is welded to it. The exec who signed off on the business case has their name on it. Everyone in the room has a personal history with the decision, and that history quietly bends every judgment toward "let's give it one more quarter." Sunk cost isn't only financial. It's reputational, and reputation is far stickier than money in most organizations.


## Preparing for the rewrite is as important as the rewrite

Most failed rewrites start their failed journey here. Even successful rewrites start their journey of failure here all too often.

Preparation is unglamorous, which is exactly why it gets skipped in the rush to the exciting greenfield part. But it's where the project is actually won or lost:

- **Properly understand what you're replacing.** The messy old system encodes years of hard-won edge cases and business rules nobody remembers deciding. If you can't explain *why* it does the weird thing it does, you will faithfully rebuild the bug and lose the feature.

  > "The old system will be retired when the phrase 'the old system used to do it this way' disappears." Pat, VP Engineering, mentor

- **Find the seams.** Where can you cut the system so you can replace it in pieces? A rewrite you can ship incrementally is a rewrite that de-risks itself. A big-bang cutover is a bet-the-company event dressed up as an engineering task.
- **Define "done" before you start.** Not "it's better", but a concrete, testable line. You need a finish line, because "better" is infinite and the team will chase it until the money runs out.
- **Ship value on the way, not at the end.** If the first customer-visible benefit lands eighteen months in, you've built a two-year window in which the project can be canceled and shows nothing for it. Sequence so that value arrives early and often. If you're familiar with small batch thinking and cost of delay this should be a no-brainer; not to mention the political goodwill and all-important momentum.

This is unglamorous work. And no plan survives first contact with reality. But as always, the value is in planning rather than the produced plan.

## Cost is half the conversation. The other half is value

Engineers instinctively argue rewrites on cost and risk: "the old system is fragile, it'll cost us if it breaks." All true, and all unpersuasive, because a board can't act on "might be bad". Not to mention engineers are often looking at fringe scenarios and worst-case. It's in our nature, but we're not great at risk-adjusted thinking.

And more importantly, you have to articulate the **value**. What does fixing this actually unlock or protect? Faster feature delivery? A compliance requirement that gates an enterprise deal? A cost curve that finally bends the right way? 

_(this is the same discipline as tracking [engineering capex]({{< relref "engineering-capex-opex.md" >}}): you're translating engineering reality into a language the board can allocate capital against.)_

And once you frame it as value rather than tidiness, something uncomfortable falls out: **for a lot of things, the value of fixing them is close to zero.**

## Some fires are better left burning

So if the value of something is close to zero, what do we do? 

We let it burn! _(mind you, a controlled burn rather than a raging dumpster fire)_

This is the hardest decision to make for an engineer.  

Some things are better left burning. You keep an eye on them, and every so often, when the smoke gets a little thick, you walk over and douse them with a bucket of water so it gets back down to a manageable smolder. Then you leave them alone again.

Judgment, benign neglect, call it what you will. A rewrite is only worth it when the thing is broken **and** important **and** actively changing. Miss any one of those and you're spending your best engineers' time making something prettier that no one will ever thank you for. Ugly and stable is a perfectly fine state for code to live in.

The operator's job was never to make everything beautiful. It's to know which fires are worth the fire brigade and which ones just need a bucket of water and to be left alone to smolder.
