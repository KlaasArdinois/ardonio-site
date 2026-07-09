+++ 
draft = true
date = 2026-07-08T16:30:00+01:00
title = "It Keeps Falling Over As You Grow"
description = "The most recognisable scaling symptom, and the two loudest reactions to it — more engineering, or a rewrite — are usually both wrong. Why the fix is surgical, and how to find the one seam that's actually at its limit."
slug = "it-keeps-falling-over"
authors = ["Klaas Ardinois"]
tags = []
categories = []
externalLink = ""
series = []
+++

The system was fine. That's the maddening part.

It was fine at ten thousand users and it was fine at twenty, and then somewhere around forty it started paging someone at 2am. Not every night — just often enough that the on-call rota became a morale problem and the CEO started getting the "are we down again?" messages from customers. Nobody changed anything obvious. It just quietly crossed a line.

This is the single most recognisable symptom in a scaling company, and because it's so recognisable, it triggers two equally reflexive responses: **more engineering, or a rewrite.** Both are loud, both feel proportionate to how loud the problem is, and both are usually wrong.

They're wrong for the same reason: "it keeps falling over" *feels* like a whole-system problem, so people reach for whole-system answers. But it almost never is. Scaling failures are cliffs, not slopes. A thing that was completely fine does absolutely fine right up until it hits a limit — a connection pool, a table that was cheap to scan at fifty thousand rows and is a wall at five million, a nightly job that starts overrunning into the morning — and then it falls off. The work isn't to make everything bigger. It's to find the one thing sitting at its limit and move that limit. Surgical, not sweeping.

## "More engineering" comes in three flavours, and all three miss

When something keeps falling over, the instinct is to reach for more engineering. Fair enough. But "more engineering" is really three different reflexes, and each one answers a question nobody actually asked.

**"Throw more bodies at it."** The board-friendly one, because headcount is legible — you can spend it, and you can point at it in a deck. The trouble is you can't parallelise a diagnosis. Dropping five new engineers onto a system nobody fully understands doesn't split the problem five ways; it multiplies the number of people who need onboarding onto a team that's already firefighting. Brooks wrote this down in 1975 and it's still true: adding people to a late, struggling effort tends to make it later. _(sidenote: the fire gets worse before it gets better, and sometimes it just gets worse.)_

**"Our engineers aren't good enough — get better ones."** The talent misdiagnosis. Sometimes it's genuinely true, but far less often than the person saying it believes. The people who built the thing are also the only people who understand where the bodies are buried, and replacing them mid-fire means re-learning the system from scratch at the worst possible moment. Nine times out of ten it isn't a skill problem, it's a *mandate* problem — the team has been told to ship features for two years and nobody ever gave them the time or the permission to go fix the thing that's now breaking. And when there genuinely is a capability gap, the answer is usually one or two senior hires who can do the surgical diagnosis — not a team swap.

**"Engineering is a hassle — let's outsource it."** The ownership misdiagnosis, and it shows up most in companies that aren't software companies but happen to have some engineering in house. Engineering feels like a cost centre and a headache, so the temptation is to make it someone else's headache. But a body shop bills by the hour, which means the fire is *billable* — they have precisely zero incentive to find and kill the root cause. Worse, you're exporting the institutional knowledge of your own product at the exact moment you most need it. Outsource the commodity plumbing, fine. The thing that keeps falling over is almost always the thing that's actually core to how the business runs — which is the last thing you should hand to strangers who bill by the ticket.

Notice what all three have in common: they're answers to *"whose job is this?"* — more of them, better of them, or not-us-at-all. They're org-chart answers to an architecture question. And the constraint doesn't care who's holding the shovel. You can add shovels, hire a better shovel-holder, or outsource the whole digging crew — the hole is still in the wrong place.

## Step one is never a decision. It's better data.

So what do you actually do? Before you reorganise a single person, you upgrade the quality of the question.

The first move I make on this call is almost boringly unglamorous: **talk to the engineers, and fix the data on failures.** Because the data a company has when it makes this call is nearly always just a count — "we had six outages last month." A count tells you it hurts. It tells you nothing about where to cut.

In one instance I stopped counting outages and started *classifying* them, by cause:

- **Process** — a deployment gone wrong, a bad config push, a release that skipped a step. Self-inflicted.
- **Software** — the code itself behaving badly under load, including the architecture choices that got us here. The actual system at its limit.
- **Third-party** — an AWS wobble, a datacenter issue, an upstream dependency going dark — that we then handled *badly*.

From the outside, and from the CEO's chair, all three look identical: **we're down, customers are angry.** That's exactly why the count feels like the whole story. But they need completely different responses. A process problem is fixed with release discipline. A software problem is the surgical bit — the seam actually at its limit. A third-party problem isn't really about the third party at all; it's about your own lack of graceful degradation when someone else fails. Same symptom, three different diseases, three different cures. You cannot see which one you have from a number that just says "six."

Once the failures are classified, the critical seams and the real drivers fall out of the data almost on their own. *Then*, and only then, do you start organising people around the problem — because now you know what the problem actually is.

## Contain, cope, control

The organising principle I use once the drivers are clear is simple enough to say in a board meeting: **contain, cope, control.**

- **Contain** — limit the blast radius. Before you fix anything properly, stop one failure from taking everything down with it. Circuit breakers, isolation, a smaller area that can fail on its own. This buys you the thing you need most: room to think.
- **Cope** — the short-term patch. Not the real fix, and everyone should know it's not the real fix, but it stops the 2am pages and takes the pressure off while you do the real work.
- **Control** — properly address the root cause. The surgical fix to the one seam the data pointed at. This is the part the two reflexes skip straight to — or never reach at all.

The reason to name the three out loud is that it stops people conflating them. "We patched it" (cope) gets mistaken for "we fixed it" (control), the pressure comes off, and the thing falls over again in three months a little bigger. Naming the stages keeps everyone honest about which one they've actually done.

## Why this is hard to do from the inside

There's a reason this surgical, data-first approach is easier to run as an outsider — and it's the same reason it's easier for an outsider to [kill a doomed rewrite]({{< relref "the-rewrite-that-shipped-nothing.md" >}}). The data doesn't only find the seam; it settles the argument. "Our engineers aren't good enough" and "we just need more people" are political positions dressed as diagnoses, and inside a company under fire they're very hard to challenge. An independent read, backed by classified failure data, can say what the numbers say: sometimes *your team is fine and your architecture has one specific bottleneck no one was given time to fix* — and sometimes it can't, and there really is a gap. Either way it's a finding, not a faction.

Because in the end, "it keeps falling over" is loud, and the temptation is always to answer loud with loud. The operator's job is to answer it quietly: find the one thing at its limit, contain it, cope with it, control it. You earn the right to the big gesture — the rewrite, the ten new hires — only after you've done the surgery and found it wasn't necessary.
