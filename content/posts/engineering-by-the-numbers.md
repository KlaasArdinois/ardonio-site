+++ 
draft = true
date = 2026-07-08T11:00:00+01:00
title = "Engineering by the Numbers"
description = "The scorecard I ran with my engineering managers. Not to replace their judgment, but to earn it a seat at the table. A practical system for making a team think in data without killing the narrative."
slug = "engineering-by-the-numbers"
authors = ["Klaas Ardinois"]
tags = []
categories = []
externalLink = ""
series = []
+++

Every month, my engineering managers walked into a room knowing they'd have to answer the same question: "tell me what you think — and bring something to back it up."

I called it Engineering by the Numbers. And despite the name, it was never really about the numbers.

## The two ways this usually goes wrong

Most engineering leadership sits at one of two extremes, and both are broken.

The first is **management by anecdote**. The team is "doing great", the last release "went well", the on-call week was "a bit rough but fine now". Everyone nods. It feels human and trusting, right up until a board member asks "how do you know?" and the honest answer is a shrug. You can't manage what you can't see, and you certainly can't defend it one level up.

The second is worse: **management by dashboard**. Someone reads a blog about DORA metrics, wires up a tool, and now deployment frequency is a target. Within a quarter your team has learned to game it — smaller commits, gamed ticket sizes, velocity that goes up while nothing ships. _(sidenote: the moment a metric becomes a target, it stops being a measurement. Goodhart's law is undefeated.)_ You've traded vibes for a different kind of fiction, one that comes with a nice chart.

I wanted neither. I wanted my managers' judgment — the in-the-moment read that only the person actually running the unit has. But I wanted it **backed by something**.

## The thesis: the number buys you a seat, the story is what you do once you're sitting

Here's the whole idea in one line: **a number without a story is noise. A story without a number is a hope.**

The data was never the verdict. It was the ticket to the conversation. My managers brought their numbers *and* their narrative, in that order. The number is not up for debate — it is what it is. But the *interpretation* was entirely theirs, and that's where the value lived.

"Cycle time doubled this month" is a fact. Whether that's because we took on a gnarly migration, lost a senior engineer, or quietly let quality slip — that's the judgment I was actually buying. The number just made sure we were talking about something real instead of a feeling.

## Metrics per unit

The mistake people make is picking one set of metrics for "engineering". But engineering isn't one thing. What "good" looks like for a product dev team is not what it looks like for the people keeping the lights on. So each unit had its own handful.

A handful. Not a wall. If you can't hold your unit's health in your head, you've got a dashboard, not an understanding.

**Product development**
- Cycle time — PR opened to running in production
- Deployment frequency
- Escaped defects — bugs that reached a customer, not the ones we caught
- Planned vs unplanned work — how much of the month got eaten by fires

**Infrastructure / platform**
- Reliability against SLO — and how much of the error budget we'd burned
- Cost per customer (or per transaction) — is the unit economics curve bending the right way?
- Mean time to recovery — not incident count, recovery. Things break; the question is how fast you're back
- Capacity headroom

**Level 3 customer support (engineering escalations)**
- Volume reaching L3 — this should trend *down* over time. Rising escalations is a product-quality tell, not a support problem
- Time to resolution
- Novel vs recurring — a recurring escalation is a bug you've chosen not to fix, wearing a support ticket as a disguise
- Backlog age

**Internal IT**
- Time-to-productive for a new hire — laptop, access, tools, all of it
- Ticket volume and time to resolve
- Manual vs automated — what fraction of the toil have we actually removed?
- Spend per head

You'll notice most of these are indicators, not targets. That's deliberate. They exist to provoke the question "why", not to be gamed into green.

## What rolls up — and what deliberately doesn't

Only a subset climbed into my exec and board scorecard. Most of it stayed inside engineering, on purpose.

The board doesn't need cycle time. They need to know the machine is reliable, the cost curve is under control, and quality isn't quietly eroding. So what went up was a translation, not a copy:

- **Reliability** — are we hitting our SLOs (the board version of a dozen infra metrics)
- **Efficiency** — cost per customer, and the trend
- **Quality** — escaped defects, because that's the one that hits revenue and reputation
- **Predictability** — are we delivering roughly what we said we would

Everything else was operational detail that would have been noise at board altitude. Part of the job is knowing which numbers are for running the unit and which are for governing the company. Confusing the two is how you end up with a board debating story-point estimation. _(sidenote: I've watched it happen. Do not let it happen.)_

This also ties back to how I think about [engineering capex and opex]({{< relref "engineering-capex-opex.md" >}}) — the scorecard and the cost tracking are two views of the same underlying discipline.

## Protecting the narrative

This is the part everyone gets wrong, so I'll be blunt about it.

If you're not careful, "bring data" curdles into "the spreadsheet decides". Managers stop bringing their judgment because they've learned the number wins every argument. You've now optimised your best people down to dashboard-readers, and you've lost the exact thing you hired them for.

I protected against it with a few simple rules:

1. **Number first, then story — always in that order.** The data sets the scene; the manager tells me what it means. The story is not optional and it is not a footnote.
2. **No metric is a target.** They're indicators. The second someone tried to "improve the metric" instead of the underlying thing, we had a different, harder conversation.
3. **A surprising number is a good thing, not a failure.** If cycle time spiked and the manager had a clear-eyed read on why, that was a *win* — they were paying attention. The failure mode was never a bad number. It was a bad number with no story, or a good number with no idea why.
4. **"I don't know yet" was an acceptable answer** — exactly once. It meant "I've seen it and I'm on it," which is fine. What wasn't fine was not having seen it at all.

The point of all this was never to turn managers into analysts. It was to make sure that when they told me what they thought — and I genuinely wanted to know what they thought — it was grounded in something I could stand behind one level up.

## How to actually roll this out

If you're a CTO or VP Eng at a maturing company and you want to introduce this without your team feeling a stopwatch over their shoulder:

- **Start with the data you already have.** Do not build a metrics platform. Your ticketing system, your deploy pipeline, and your incident log already hold most of this. A spreadsheet is a completely respectable place to begin.
- **Monthly, not weekly.** Weekly turns it into surveillance and the noise drowns the signal. Monthly gives trends room to actually mean something.
- **Let each unit lead propose their own handful.** Ownership beats imposition. You keep veto, they keep authorship.
- **Never open with a gotcha.** The first time a number is used to ambush someone in front of their peers, the whole thing dies. It becomes theatre, and you get managed numbers instead of managed teams.

Do it right and something quietly shifts. Your managers stop coming to you with "it's going well" and start coming with "here's the number, here's what I think it means, and here's what I'm doing about it."

Which is, when you get down to it, the entire job.
