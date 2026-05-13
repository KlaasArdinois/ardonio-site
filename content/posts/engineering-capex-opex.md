+++ 
draft = false
date = 2026-05-12T11:55:28+01:00
title = "Why engineering capex tracking doesn't have to be a mess"
description = ""
authors = ["Klaas Ardinois"]
tags = []
categories = []
externalLink = ""
series = []
+++

Engineering capex tracking often rests on one of two options: 
1. Ignored. Viable path if you're a small startup. It shows a fairer burn on the PnL and no arguments around the shelf-life of your pre product-market fit work.
2. Hourly tracking of engineers. Despised by all and producing data nobody particularly trusts. Even worse if it's started with estimated hours, but that's a debate for a different time.

Over the years I've implemented a 3rd way that is good enough for financial purposes AND light enough to not become a burden. And we all know, things that are easy to measure are more likely to be consistently measured.


# The system
My system is pretty straightforward and relies on engineers self reporting at the end of the sprint. I usually ask my teams to embed it in their end of sprint ceremonies. Or in flow-based teams, we just agree to do it every other week on the Friday standup. The point is, pick a regular timeslot and institutionalize the practice.

So what is the actual practice?

Surprisingly simple: each team fills out a short allocation table every 2 weeks. 

And they have one simple question: as a team, what percentage of your time this sprint went into each of these buckets?

And I make it pretty clear to each team that I'm not looking for pinpoint precision, but I'm in for "broadly right". 

The buckets are:
* Spikes - Tasks that are typically about de-risking a solution or prototyping an approach; and occasionally true feasibility questions
* Bugs - Time spent fixing things that were broken; and crucially were broken in production (or in case of internal software, when it was used). A problem discovered in testing before a feature was live does not fall under this definition. 
* Feature work and improvements - Usually the vast majority of the work. I normally include both direct product features as well as work on the supporting systems like CI/CD
* Meetings and admin overhead - everyone's favorite 
* Time off - the real favorite

I need to put some quick clarification here to the nuance between bug vs feature work/improvements. 
THe core concept of a bug, from a capex/opex point of view, is that you're fixing a problem on a system that's in live use. Finding a bug during pre-release testing is part of building. You really only care about escaped defects.

Because everything in software can be illustrated with cars, think about it this way:
* Re-attach mirrors that are falling off a car while customer is driving through UK potholed road -> bug
* Designing a new and better mirror strut -> feature / improvement
* Replacing the robot arm that places the front window panel on the assembly line -> bug
* Producing a slightly better suction cup to place the window panel more accurately -> feature / improvement

Admittedly, the line between a bugfix and a feature can get blurry at times. But we're all adults, there is some judgement required. And **who better to judge than the people doing the work**.

Once the teams are used to this it takes roughly two minutes. And for clarity, it is done by the team rather than each individual. So the estimates reflect collective effort.

# From effort to money
Since the estimates are on a per-team basis, you need a per-team cost. Which, to nobody's surprise, is simply the salary of all the people who were in that team. And teams are quite stable, certainly within a 2 week period, so it's mostly a set and forget.

And with that cost multiply through the self-reported percentages to get 

The CapEx/OpEx rules we agreed with our finance team:

* Spikes → 90% CapEx. Most spikes at this stage are de-risking known problems, not pure feasibility research, so the majority qualifies.
* Bugs → OpEx. Maintaining existing functionality isn't creating a new asset.
* Feature work and improvements → CapEx. This includes product features, CI/CD investment, platform work — anything that extends the useful life or capability of the product.
* Meetings, overhead, time off → OpEx.

And finance and I keep a small list of "products" we use to allocate budget to for capex purposes. Think of this, by way of example, broadly as "3rd party integrations, core system, pipelines & tooling, billing engine, ... ". Things that are relatively stable in time and have meaningful value and ability to drive revenue. Owning this list is shared between finance and tech, but from experience keep it short.

# The auditor question
The natural concern is whether these self-reported estimates really hold up. In my experience: they do.

However since you're likely running a ticket system in the background you will have some data to correlate. Spot checking a few sprints based on when tickets moved status is a good enough proxy. **You're aiming to be "correct on average"**, rather than "nail hours worked on every ticket".

And for what its worth, our big 4 auditor did this and concluded our approach was acceptable.

# Why it works
The two-minute constraint is a feature rather than a limitation. If you make the reporting burdensome, engineers will either game it or resent it. Two minutes means they'll actually do it, and the social dynamics of doing it as a team over a 2 week window rather than by task means the estimates are usually good enough without looking like surveillance.

The goal is a defensible, consistent methodology that gives finance what they need and doesn't turn your engineering culture into a billable-hours shop. 
