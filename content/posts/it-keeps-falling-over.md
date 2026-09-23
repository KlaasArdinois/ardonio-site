+++ 
draft = false
date = 2026-09-22T16:30:00+01:00
title = "It Keeps Falling Over"
description = "The most recognizable scaling symptom and the two common reactions to it: more engineering or a full rewrite. Both are usually both wrong. The fix is systems thinking, finding the constraints, and getting comfortable with things lightly on fire."
slug = "it-keeps-falling-over"
authors = ["Klaas Ardinois"]
tags = []
categories = []
externalLink = ""
series = []
+++

The platform was fine. That was the most concerning part.

In fact, it was perfectly fine handling ten thousand users. And it was comfortably serving twenty thousand. And then somewhere around forty thousand our monitoring started occasionally flagging errors. Monitoring is generous. In those days monitoring was mostly customer support receiving complaints the platform wasn't working. Not down, just slow, occasionally unable to save data, ... . But it got so regular that on-call became a dreaded "what's it going to be this time?" and the CEO was receiving direct uncensored messages from our top customers everytime something happened. 

Nothing had really changed in the platform, we weren't taking extra risk in deployment or skipping quality control. We simply had crossed the line of what the architecture could handle even with an aggressive "let's throw extra hardware at it". 

This is probably the single most recognizable symptom in a scaling company, and because it's so recognizable, it triggers two equally reflexive responses: **more engineering or a rewrite**. They're loud answers to a big loud problem. 

They're wrong for the same reason: "it keeps falling over" *feels* like a whole-system problem, so people reach for whole-system answers. But it almost never is. Scaling failures are mostly cliffs, not slopes. A thing that was completely fine does absolutely fine right up until it hits a limit and then it drops. Could be a connection pool running out of memory, a table that was cheap to scan at fifty thousand rows and is a wall at five million, a nightly job that starts overrunning into the morning knocking user traffic out, ... . The answer isn't to make *everything* bigger. It's to find the one thing sitting at its limit and move that limit. Surgery, not butchering.

## "More engineering" comes in three flavors

When something keeps falling over, the instinct is often to reach for more engineering. Instinctively it makes sense to think you just need more hands at the pump. But "more engineering" in my experience often boils down to one of these 3.

**"Throw more bodies at it."** Most of the time followed by some form of "...and then we'll ramp back down". Expert advice: the exit ramp you planned isn't the one you'll take. But it is a board-friendly plan usually because headcount is something tangible, and you can point at it in a deck and "more people, more work done" works in many other areas of the company. The trouble is **you can't parallelise a diagnosis**. Dropping five new engineers onto a system nobody fully understands doesn't split the problem five ways; it multiplies the number of people who need onboarding onto a team that's already firefighting. Brooks wrote this down in 1975 and it's still true: adding people to a late, struggling effort tends to make it later. _(sidenote: the fire gets worse before it gets better, and sometimes it just gets worse.)_

**"Our engineers aren't good enough, we should get better ones."** The talent misdiagnosis. Sometimes it's genuinely true, but far less often than the person saying it believes. The people who built the thing are also the people most likely to know where the bodies are buried. Replacing these people mid-fire means re-learning the system from scratch at the worst possible moment. **Nine times out of ten it's less skill problem and more a mandate problem.** The team has been told to ship features for two years and nobody ever gave them the time or permission to go fix the thing that's now breaking. And when there genuinely is a capability gap, the answer is a few expert targeted hires who can do the surgical diagnosis, not a full squad rotation.

**"Engineering is a hassle, let's outsource it."** Shows up regularly in companies that aren't technology companies but happen to have some engineering in house. Engineering feels like a cost center and a headache, so the temptation is to make it someone else's headache. But at the end of the day a body shop bills by the hour, which means the fire is billable. They have precisely zero economic incentive to find and kill the root cause. I'm not saying they won't try their best or have people who care. But there is an inherent disconnect between your company's performance and theirs. Even worse, **you're exporting the institutional knowledge of your own system at the exact moment you most need it**. Outsource the commodity plumbing, fine. The thing that keeps falling over is almost always the thing that's core to how the business runs. And that's the last thing you should hand to strangers who bill by the ticket.

Notice what all three have in common: they're answers to *"whose job is this?"* "More of them", "better of them", or "not us at all". They're org-chart answers to an architecture question. And the constraint doesn't actually care who's holding the shovel. You can add shovels, hire a better shovel-holder, or outsource the whole digging crew. End of the day the hole is still in the wrong place.

## Step one is not a decision. It's better data.

So what do you actually do? Before you reorganize a single person you upgrade the quality of the question.

The first move is almost laughably unglamorous and obvious: **talk to the engineers, and fix the data on failure modes.** Because the data a company has when it makes this call is nearly always just a count in my experience. Something like "we had six outages last month." A count like that tells you it hurts. It tells you nothing about where to cut.

In one instance I stopped counting outages and started *classifying* them, by cause:

- **Process** — a deployment gone wrong, a bad config push, a release that skipped a step. Self-inflicted.
- **Software** — the code itself behaving badly under load, including the architecture choices that got us here. The actual system at its limit.
- **Third-party** — an AWS wobble, a datacenter issue, an upstream dependency going dark that we then handled *poorly*.

From the outside, and from the CEO's chair, all three look identical: **we're down, customers are angry.** That's exactly why the count is the commercial story. Nuance be damned. But those causes need completely different responses. A process problem is fixed with release discipline. A software problem is the surgical where the system is actually at its limit. A third-party problem isn't really about the third party at all; it's about your own lack of graceful degradation when someone else around you fails. Same symptom, three different diseases, three different cures. You cannot see which one you have from a number that just says "six."

Once the failures are classified you can start organizing a solution.

## Contain, cope, control

The organizing principle I use once the drivers are clear is non-technical and practical enough to be understood in a board meeting: **contain, cope, control.**

- **Contain** — limit the blast radius. Before you fix anything properly, stop one failure from taking everything down with it. Circuit breakers, isolation, a smaller area that can fail on its own. This buys you the thing you need most: room to think.
- **Cope** — the short-term patch. Not the real fix, and everyone should know it's not the real fix, but it stops the 2am breakdowns and takes the pressure off while you do the real work.
- **Control** — properly address the root cause. The fix to the constraint the data pointed at. 

The reason to call this out is that it stops people conflating them. "We patched it" (cope) gets mistaken for "we fixed it" (control), the pressure comes off, and the thing falls over again in three months a little bigger. Naming the stages keeps everyone honest about which one they've actually done.

Also, don't be afraid to let something live in contained mode for a long time. Some problems really aren't worth controlling. The occasional patch can make perfect commercial sense over a proper fix. Usually much to the dismay of the engineering team. But we are running a business after all.


## In practice?

In the end, "it keeps falling over" is loud, and the temptation is always to answer loud with loud. The operator's job is to answer it quietly: find the one thing at its limit, contain it, cope with it, control it. You'll earn the right to the big gesture, the rewrite, the ten new hires, only after you've done the surgery and found it wasn't necessary.
