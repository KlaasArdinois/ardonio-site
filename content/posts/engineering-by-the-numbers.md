+++ 
draft = false
date = 2026-07-13T11:10:00+01:00
title = "Engineering by the Numbers"
description = "The scorecard I ran with my engineering managers. Not to replace their judgment, but to earn it a seat at the table. A practical system for making a team think in data without killing the narrative."
slug = "engineering-by-the-numbers"
authors = ["Klaas Ardinois"]
tags = []
categories = []
externalLink = ""
series = []
+++

Every month, my engineering managers walk into a room knowing they'd have to answer the same question: "tell me what you think, and bring something to back it up."

I called it Engineering by the Numbers. Despite the name it's never really about the numbers. I care about their gut feel, their finger-on-the-pulse insight, but at the end of the day I also want something that tells that story with facts.

## The two ways this usually goes wrong

Engineering leadership in a young organization often sits at one of two extremes, and both are broken.

The first is **management by anecdote**. The team is "doing great", the last release "went well", the on-call week was "a bit rough but fine now". Everyone nods. It's human, trusting and most likely everyone in the room is close enough to the story they remember it. That works until an investor or board member asks "how do you know?" ... and the honest answer is a bit of handwaving. You can't manage what you can't see, and you certainly can't defend it one level up.

The second is worse: **management by dashboard**. Someone reads a blog about DORA metrics, wires up a tool, and now deployment frequency is the thing we're talking about. And within a quarter the team has learned that smaller commits and gamed ticket sizes lead to huge increases in velocity and deployment frequency. Sadly for the customer, nothing is actually delivered, we just looked busier. _(sidenote: the moment a metric becomes a target, it stops being a measurement. Goodhart's law is undefeated.)_ 

I'm calling this one worse because managing by anecdote is at least grounded in people's perception of what's going on. The second is usually actively doing the wrong thing.

Of course, I want that sweet middle ground. I want my managers' judgment, that in-the-moment read that only the person actually running the unit has, but I want it **backed by something** so we can see evolution and have a baseline. 

## A new hope

So here's the whole idea in one line: **a number without a story is noise. A story without a number is a hope.**

The data was never the final verdict, nor was it ever good or bad. It's just a datapoint in a series. What makes it valuable is the narrative, it's answering **why**. That _interpretation_ was entirely for my team to bring, and that comes from their experience and presence.

"Cycle time doubled this month" is a fact, something that's not really up for debate. However if it's because half the team was off on holiday or we redeployed on quality pre-release, that will drive a very different reaction and expectation. "Cycle time doubled" might actually be a very positive signal, rather than something that went wrong.

## Metrics per unit

The mistake people make is picking one set of metrics for "engineering". But engineering isn't one thing. What "good" looks like for a product dev team is not what it looks like for the people keeping the lights on. So each unit had its own handful.

A handful, not a full room-filling display. If you can't hold your unit's health in your head, you've got a dashboard, not an understanding. Here are a few samples:

**Product development**
- Cycle time: first engineering work (typically taking it into a sprint) to in production. The click into this is measuring touch time vs wait states.
- Deployment frequency: how often do we move code to production
- Escaped defects: bugs that reached a customer, not the ones we caught before something went live
- Planned vs unplanned work: how much of the month got eaten by fires

**Infrastructure / platform**
- Uptime / availability. I prefer measuring something functional rather than just uptime. The classic case of a broken log-in screen. Technically you're up, in practice you're unavailable. Pick your measure carefully so it is meaningful.
- Mean time to recovery. Things will break; the question is how fast we get back

**Level 3 customer support (engineering escalations)**
- Repeats. How often is a problem coming back.
- Backlog age. Are we dealing with the problems our customers report, or do we just quietly hope they go away.

Hopefully you'll notice most of these are indicators, not targets. That's deliberate. They exist to provoke the question "why", not to be gamed into green. 

## What rolls up

Only a subset of this climbs into my exec and board scorecard. The majority of this detail stays inside the engineering engine room. This is the communication vocabulary for running the teams, not for running the company. 
The board doesn't need cycle time for instance. They need to know the machine is reliable, the cost curve is under control, and quality isn't quietly eroding. So what went up was a translation, not a copy:

- **Availability** -> Can our customers reliably use our product
- **Efficiency** -> cost per customer (or cost per minute back in my telco days). Some form that speaks to the question "are we protecting our operating margins"
- **Quality** -> escaped defects, because that's the one that hits revenue and reputation
- **Predictability** -> are we delivering roughly what we said we would. As a business matures, being able to be realistic about capacity in engineering delivery becomes crucial. Startups just go "fast", but as you mature being able to cadence it, get the marketing comms aligned, roll out on schedule become skills you need to master.

Everything else was operational detail that would have been noise at board altitude. Part of the job is knowing which numbers are for running the unit and which are for governing the company. Confusing the two is how you end up with a board debating story-point estimation. _(sidenote: I've watched it happen. Do not let it happen.)_

This also ties back to how I think about [engineering capex and opex]({{< relref "engineering-capex-opex.md" >}}) — the scorecard and the cost tracking are two views of the same underlying discipline.

## Protecting the narrative

If you're not careful, "bring data" curdles into "the spreadsheet decides". Managers stop bringing their judgment because they've learned the number wins every argument. You've now optimized your best people down to dashboard-readers, and you've lost the exact thing you hired them for.

I protected against it with a few simple rules:

1. **Number first, then story — always in that order.** The data sets the scene; the manager tells me what it means. The story is not optional and it is not a footnote.
2. **No metric is a target.** They're indicators. The second someone tried to "improve the metric" instead of the underlying thing, we had a different, harder conversation.
3. **A surprising number is a good thing, not a failure.** If cycle time spiked and the manager had a clear-eyed read on why, that was a *win* — they were paying attention. The failure mode was never a bad number. It was a bad number with no story, or a good number with no idea why.
4. **"I don't know yet" was an acceptable answer** exactly once. It meant "I've seen it and I'm on it," which is fine. What wasn't fine was not having seen it at all.

The point of all this of course wasn't to turn managers of people into data analysts. It was to help create an environment where we could have an open and honest discussion about the true state of things. Reflected both by sentiment and cold hard data.

## How to actually roll this out

If you're a CTO or VP Eng at a maturing company and you want to introduce this without your team feeling a stopwatch over their shoulder:

- **Start with the data you already have.** Do not build a metrics platform. Your ticketing system, your deploy pipeline, and your incident log already hold most of this. A spreadsheet is a completely respectable place to begin.
- **Monthly, not weekly.** Weekly turns it into surveillance and the noise drowns the signal. Monthly gives trends room to actually mean something.
- **Let each unit lead propose their own handful.** Ownership beats imposition. You keep veto, they keep authorship. Make sure they know _why_ they're measuring something. Ask the question "what aspect of your team health/performance/... are you measuring with this".
- **Never open with a gotcha.** The first time a number is used to ambush someone in front of their peers, the whole thing dies. It becomes theater, and you get managed numbers instead of managed teams. 

Do it right and something quietly shifts. Your managers stop coming to you with "it's going well" and start coming with "here's the number, here's what I think it means, and here's what I'm doing about it."

Which is, when you get down to it, the entire job.
