+++ 
draft = false
date = 2026-06-24T12:12:30+01:00
title = "AI Surface war"
description = "OS players are positioning to own the consumer AI surface. What the TomTom playbook tells us about where frontier labs end up."
slug = "AI-surface-wars-local-LLM"
authors = ["Klaas Ardinois"]
tags = []
categories = []
externalLink = ""
series = []
+++

Local inference solves the operating cost problem of frontier Labs, by making the customer effectively pay the hardware bill. And between consumer hardware and small model improvements that's becoming an increasingly realistic option for many day to day tasks. That's what I argued in [an earlier post](../ai-broke-software-marginal-cost/).

Perhaps the most clear indicator in that direction is the path Apple has been following with Apple Silicon. Increasingly, neural processing (the core of LLM inference) is running on apple silicon, with an offload to a frontier model (openAI). And it's exposed to developers through an Apple controlled layer in core AI (local inference), Core ML (classic machine learning) and Apple Intelligence (for Siri interactions).

And outside the Apple ecosystem, Qualcomm Snapdragon X1 and X2 are now powering "AI" laptops from the usual suspects. Dell has an X1 based lattitude (the business oriented dell we all love) around £1200. That's getting towards mass market territory.

And on the not-apple software side, microsoft has Phi and is clearly pushing hard to get copilot as this generation's clippy.

The trend I'm seeing is that increasingly the local players are setting up to own the consumer, rather than the frontier labs.

# What I didn't say last time: how the labs make money going forward
When moving inference locally what's the point of your claude subscription, you might rightfully ask. Are we just going back to the good old days where I pay once, install something on my machine and then run it forever? Remember those days?

I see a few ways forward for the frontier labs in this world, keeping in mind that the real frontier models won't run locally ([as I said, the frontier will always be the frontier](../ai-broke-software-marginal-cost/#the-frontier-will-always-be-the-frontier)). So that part of their business remains protected, and billable (and presumably eventually no longer subsidized).

The likely candidates in my view are:
* Become a player in the local-model space and sell an "installable" version of their models. More or less how you run claude as a desktop app today, but with a local model included; and probably a router to offload hard things to cloud. 
* License frontier models for others to distill into local models. 
* Become the fallback for other companies to offload their hard questions to the frontier
* Exit the consumer tier altogether and focus purely on the frontier

My thesis is that eventually the frontier labs will have a lesser, or even non-existent, role in local inference. And they'll end up initially probably as a fallback for the OS/consumer players and eventually possibly entirely replaced (we'll get to that in a second). 

So yes, I am saying that claude and openAI might not be the powerhouse consumer businesses they pretend to be. And they're, if anything, in a race against their own partners. A race I think they are likely to lose as time goes on.

# Friction beats capability
Right now, my average interaction with claude involves an awful lot of copy and pasting things. Or I may have to struggle through some clumsy MCP connectors (looking at you gmail) or letting it "do things" in my browser. I've long been a fan of taking my notes in markdown, so at least I'm text-first already (shoutout to [obsidian](https://obsidian.md/)) which has helped a lot. But I also use a myriad of other apps that are either poorly accessible to Claude (apple mail) or need me to install specific extensions to get claude to do something in the app (like excel).

I'm not saying this is unusable, we muddle through, but the duct-tape is regularly visible and irritating.

Compare this to what the developers of your operating system could do if you play in their sandbox. You could have OS-level indexing of documents (already happens anyway), software libraries for developer to call that with OS level permissions built-in, and deep integration in their own tools. 

Take apple mail as an example (or any other mail client). The pre-drafted email appears right in your mail client, based on (a) the conversation it's in and (b) other emails you've had with this contact and (c) your writing style seen over all the emails you've sent. Compare that to the "hey claude, help me draft a reply to this email" copy and paste. Could I get Claude to get all that context? Technically, yes. In practice: I just need a quick email drafted, don't make it hard.

# So, why doesn't openAI pay Apple to be the default? 
Pull a Google, basically. Pay Apple a large amount of money so they route every LLM inference query to open AI. Sadly, the business model doesn't work that way (yet). First because inference actually costs openAI significant amounts of money, and second because they don't have a business model yet where another revenue source can fill this in.

Compared to Google who would buy the traffic because the eyeballs that came with that traffic were very valuable to their advertisers. And I'm aware openAI is looking at advertising and other avenues of not having to make money. But right now, they would simply be paying Apple for the privilege of then paying cost for the inference, with no obvious revenue in return. 

# We've seen this before
Back in my days at TomTom I have seen this exact playbook before from Apple when maps on phones were the new thing. Here's what that looks like

1. **Launch with a supplier**. Apple Maps v1 was partially built on TomTom's data. And while imperfect in many ways, it was simply shipped to displace the then-default Google. That was more or less the Siri+openAI spiel we saw. Side note, there was in fact talk of TomTom being acquired by Apple.
2. **Rebuild first-party underneath**. Apple then apologized and went quiet on maps while they rebuilt a lot from the ground up. The public kept the data from the 3rd party supplier, internally though things are shaking. If that sounds familiar, think apple silicon and their focus on NPU.
3. **The Apple ecosystem**. I will never again underestimate the power of this. In time maps stopped being an app and become a feature of the OS. Handoff, navigation, calendar integration, watch, ... . Sure, technically it's still an app, but the routes into it are so tied into using the device you're on it's easy to forget. This is where we're heading with apple AI. It'll stop being a destination and just become part of the fabric.
4. **Apple doesn't need to make money from the feature**. Because of step 3, it stops being a solo thing to monetize. You don't buy maps, you simply buy an iDevice because it all plays nicely together. Apple monetizes the ecosystem as a whole, not the point solution.

So what happened to TomTom during this playbook? Well, our consumer business got crushed by Apple (and Google) removing all the friction of a dedicated device for navigation. The phone in your pocket hit the bar for "good enough + low friction" over "higher quality extra device". And TomTom got relegated to the B2B afterlife, licensing its data to others at a fraction of the revenue.

And to put that fractin of revenue in context 
€1,364M (FY06) → €1,737M (FY07 - iphone released) → €1,748M (FY08, peak - iphone now has GPS) → €1,273M (FY11) → €1,057M (FY12 - apple maps released) → €860M (FY18) → €585M (FY23) → €574M (FY24). 

That's Peak-to-present: ~67% revenue decline over sixteen years.

And the company's valuation dropped close to 90% between 2007 and 2009. The market clearly repricing TomTom on the credibility of the threat of phone+map, rather than the slow confirmation through revenues.

That is the important lesson for openAI and Anthropic. The moment a credible path opens up for displacement, in my mind local inference dominated by OS-level players, the market will likely reprice the frontier labs. And the real question is what the labs place in that new world would be. 

When people started looking at their phones for navigation, Apple started to learn a lot. Every path, every walk, every drive, ... became an anonymous trace. And putting all those on top of each other showed where the map was deficient vs the real world, where and when traffic bottlenecks occur, etc. Data that had little to do with the process of making the map, but a feedback loop that was incredibly helpful to point out where to improve.

If you map this to LLM usage. Right now, Claude can generate your email but doesn't actually know what you send. If you have the OS level view (or at least baked into the mail client) you get visibility on exactly how edited the item in the sent folder is from the draft. Even if you can't use the actual draft (privacy reasons of course), the telemetry from knowing that edit behavior is another means of measuring if your model update is better or worse in this situation. 

Apple is of course notorious for its closed system. But Microsoft isn't that far behind. They own the corporate office stack, that's not going anywhere. Windows + MS Office + Teams is the default in the vast majority of white collar workers' lives. Add to that Snapdragon X series becoming mainstream, Phi as a local model and the inevitable CoPilot and you've got the same cocktail. And through their stake in openAI, arguably they also have a finger in the pie for the fallback routing on the frontier.

# The Bull case
If you're with me so far, you might think I'm writing off frontier labs. But in some way, the TomTom example shows the bull case: niche B2B. TomTom lost a lot of earnings from their consumer business, but underneath was a capability (producing high quality map data) that was still value to other businesses. 

So the path that I see that would save the frontier labs is in the domain specific high ROI frontier applications. In other words, how many more "claude code" niches exist, where there is a true ROI for frontier. "Claude Legal", "Claude finance", "Claude biotech", ... .

If those niches keep existing (or are created) and adopted faster than local capability catches up, that's the bull case in a nutshell here. 

# So?
Summing up across these 2 articles
* Local inference is becoming viable, and helps the labs towards a usable business
* High ROI tasks (e.g. coding) will become the battleground for frontier labs
* Lower ROI tasks are technically capable of shifting towards local hardware
* The local inference approach favors a lower friction user experience. This end-user surface is where the battle is, and in my opinion favors the Operating Systems.
* Value will accrue to the winners of that end-user surface battle. LLM capability will become an input, not a moat.
