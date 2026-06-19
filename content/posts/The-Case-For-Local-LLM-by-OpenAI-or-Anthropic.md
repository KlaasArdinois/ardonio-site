+++ 
draft = False
date = 2026-06-19T12:12:30+01:00
title = "AI Broke Software's Best Trick"
description = "Generative AI shattered the zero marginal cost model that made software economics so attractive. Here's why local inference is the only structural fix — and what it means for the labs."
slug = "ai-broke-software-marginal-cost"
authors = ["Klaas Ardinois"]
tags = []
categories = []
externalLink = ""
series = []
+++


Software ate the world, per Andreessen. And it did so on one particular economic pillar: zero marginal cost. In simple terms: the cost of producing an extra copy of your application is effectively zero. Compared to the cost of coding the application, shipping a few floppy disks is effectively zero cost. These days, SaaS software has replaced that shipping cost with compute cost. But the relative equation holds. One extra user of your product carries a negligable cost compared to creating that product. 

**genAI is different**. Every user, every question/response, every nano banana image, ... every interaction carries a significant direct cost. And the more a user engages, the higher the cost to the company. And it turns out that providing that service is pretty expensive, since you need high end datacenter hardware to run the computations that produce the output. 

_The traditional "scale your way out of it" doesn't work if you're not profitable on a per-user basis._ It just digs the hole faster.

Oops...

And of course, nobody sat around wanting "AI". The models are only interesting to the extent we can **do something of value** with them. For some that might be entertainment (like asking a model how to get a peanut butter sandwich out of the VCR in the style of the King James bible ... we've all tried that, right?). For others that might look more productive, like trying to get a handle on sales data. And whether or not that task ends up being done reliably really depends on the task in question.

Broadly speaking, we currently use AI on hgih value and low value tasks. 
* **High ROI tasks**. Think about coding, complex agent workflows, ... . The sort of task where the cost and token burn is probably justifiable. And exactly the sort of tasks where new frontier models are still meaningful steps forward. The difference between what Fable (when it was available) could code vs Opus 4.8 is significant.
* **Low ROI tasks**. Summarizing a meeting, drafting an email from your bullet points, scheduling a task through calendar access. The ROI on "draft this email" is hard to justify at unsubsidized LLM pricing. I'm not saying there's no value to it, but rather that the economics break. For $20 / month I'll happily have claude write and rewrite summaries. At $200 / month ... nah, my trusty manual notes in obsidian will do. 


# A broken model in three parts
First, as I just mentioned, cost grows in line with usage AND current subscriptions don't cover cost. And yes, the saas subscription pricing is normally set so that a few net-loss power users get subsidized by a long tail of net-profitable users. SemiAnalysis and others have pointed out that a user using 25% of their token limits is _at best_ a negative 25% margin. Or the more aggressive side of the calculus by Ed Zitron, 3 power users need at least 2000 low-end users to break even. Econ101: this is not how you get to a profitable product.

The second thread I want to quickly pull is ammortization. Training a frontier model carries a cost in the 100s of millions to produce the asset (and let's assume it's all capex for simplicity), and projections are that this will keep growing as bigger models need more compute time to train and more data to ingest. On the flip side, let's look at the lifetime of these models. Flagship models, major versions, ship roughly every 12-18 months with minor upgrades in between. And when a new model comes out the early adopters switch, and the laggards wait for it to become the default setting, which is typically quite quickly as well. So let's say that the first 25% (power users) switches more or less right away, and the remaining gets swept up over the next 6 months as it becomes the default model. So you've got a 100+ million asset with, generously a 2yr shelf life, and you're stacking a new asset of that size every year-ish. Sure, technically it will get written off over a longer life than its real practical use but in reality every model has about a year to make a profit.

But hey, token costs are coming down. This is the third place the economics break. Token costs are objectively coming down, however increasingly reasoning models consume more tokens to get to an answer (and FYI, reasoning tokens are considered output tokens; the expensive kind). Tokens are a poor proxy measure anyway of course, see all the "tokenmaxxing" backlash. The thing that really matters is **task completion, the economically relevant result**. And as models get more capable between reasoning and longer context windows, and we start sticking them in skills and workflows which burn more tokens as well, we're actually driving the bill "per result" up, despite token costs coming down right now. 

# Solving the economics
Since we're in a world where the users consumes more of the product than they pay for, there are only 2 simple levers to pull
1. **Charge more**. This works in the high ROI tier of tasks. Though as we've seen with recent API pricing, even that isn't as clear cut as you'd hope, in part because it's hard to tie "code" directly to "revenue" in most cases.
2. **Cost less**. This is extending the life of old models by routing "simple" tasks to lower models. The frontier labs are doing this under the hood already. And while it helps, it does little to the marginal cost per query. Older models still incur COGS and take up datacenter capacity. So while routing can be a partial offset, it's not a clean solution.

The bar to summarize an email of course isn't really getting higher over time, nor does summarizing a meeting or drafting the powerpoint bullets. This "everyday task" tier has a pretty fixed threshold, and we've crossed that bar some time ago to the point where **evolution in frontier models doesn't make that much of a difference anymore for this kind of task**. So while we can debate whether there is a plateau for LLM, and how close or far we are from it, we're at a point where "good enough" is reached for a number of tasks.

The clean solution is therefore more akin to the days of floppy disks, rather than clouds. Send the user a copy of your software and let their hardware do the heavy work while they use it. So your marginal cost becomes one of distribution, but no longer one of usage. At which point a small license fee can certainly become profitable. I'm going to call this the *market-natural* solution, as it restores software economics that will allow scaling their way to profitability.

Now I know that on 2026 hardware we're not quite in a position to run a full model on a $500 laptop, and we're more limited by memory and memory bandwidth than we are by raw compute. I'll go into more of this in the next post, but the crux here is that a combination of small model + aggressive retrieval + OS level context management is a direction that is (a) happening and (b) economically a different challenge.

# The frontier will always be the frontier
Before closing out, I want to take a quick sidestep about the evolution of the frontier. Back when gpt2 was released, it was fun but not very useful. It lacked attention (ironically), and would drift off into irrelevant nonsense in 2-3 turns. GPT 3 was far better and felt like it actually crossed a bridge into "useful", for some definition of useful. And as I mentioned before, more recently the difference between Fable and Opus was another leap.

The interesting question is what happens behind that frontier. As frontier models get quantized (reduce the number of bits used to store the model weights, at the cost of accuracy in the calculation) and distilled ("summarized" into a smaller model). Both action have the net effect that a smaller model can do an approximation of the frontier capability. And smaller models of course can do with lesser hardware. 

So think of this as a conveyor belt. The frontier permanently occupies the leading edge of what is possible in all its glory. And behind it, tasks that were previously frontier become available to "lesser" models with lesser hardware requirements. What GPT3 could only do on the edge, I can easily do better today on my 3 year old macbook air with a local model.

And that's exactly where I'll leave it today. The economics point to a release valve that solves the economics of the frontier labs, with capability shifting to local.

However, that release valve comes with quite different plumbing. Because when you're running the model local the lab no longer sees the queries, the results nor the system in which it runs. 

The release valve works by offloading the cost, but at what price to the labs? That's where I'm going with the next article
