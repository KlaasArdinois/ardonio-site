+++ 
draft = false
date = 2026-05-10T14:33:31+01:00
title = "My view on Anthropic and OpenAI setting up Joint Ventures with PE firms"
description = "Anthropic and OpenAI are both launching enterprise-AI joint ventures with private equity firms. What these deals signal about AI reaching the mid-market."
slug = ""
authors = ["Klaas Ardinois"]
tags = []
categories = []
externalLink = ""
series = []
+++
*note: A slightly modified, and simplified, version of this post appeared on my partner's newsletter [2nd order thinkers](https://www.2ndorderthinkers.com/p/private-equitys-ai-locked-in)*

On May 4th [Anthropic announced it launched an Enterprise AI services firm](https://www.blackstone.com/news/press/anthropic-partners-with-blackstone-hellman-friedman-and-goldman-sachs-to-launch-enterprise-ai-services-firm/). The new company is a combination of Anthropic and several well known Private Equity investment firms.

> The company will serve as an accelerant in bringing AI solutions to mid-size companies, helping to drive adoption across an initial customer base of both portfolio companies of the investment firms and independent companies that can benefit from the platform.

Anthropic isn't alone, openAI is [doing the same](https://www.bloomberg.com/news/articles/2026-05-04/openai-finalizes-10-billion-joint-venture-with-pe-firms-to-deploy-ai?embedded-checkout=true).

Of course the idea of having "forward deployed engineers" isn't exactly groundbreaking. Palantir built out most of their business this way. And in less AI names: AWS, DataBricks, ServiceNow, ... . My point is, this is a standard playbook in technology. If you have a product that is complicated to onboard, requires a lot of detail and time to implement well and the expertise to do so is scarce, it's a common path to build a "service led growth" part into the organization. And as far as the role of those forward deployed engineers, it's part technical expert, part sales, part customer feedback capture. 

So the interesting question is less what are they doing, and perhaps more why are they doing it together with Private Equity firms?

The first, and obvious, answer is that PE firms are a sales channel. Rather than having to target every mid market company directly, they can just rely on those PE firms to introduce them and leverage their existing relations.
Remember that Anthropic and OpenAI do not have the benefit of a strong established sales org and customer network a company like Microsoft has to push copilot.

And because PE firms typically have a lot of sway in how the companies they own operate, it's a pretty powerful relationship. 

## A quick detour in PE
For those unfamiliar with the structure of PE firms, a quick detour. 
PE firms are run by fund managers. And the job of a fund manager is to use that capital to buy companies, with the aim to sell them 4-7 years later for a return. Fund managers are commonly called General Partners, or GP for short.
The capital they use is provided by Limited Partners (LP). In practice these LP are typically sovereign wealth funds, university endowments, large family offices, high net worth individuals, ... . And the LP pay the GP a management fee, and if there's a profit when selling the GP gets a portion of that too. 
There's more nuance, but at a high level that's the structure of every PE fund, regardless if it's a one man band or a Goldman Sachs owned vehicle.

As I just said the GP "aim to sell them 4-7 years later for a return". To do this the GP tends to put operational teams in the company and pushes the business to aggressively optimize. When PE people talk about value creation, this is what they're talking about. If you're interested in how they do that specifically, [this book](https://www.amazon.co.uk/Lessons-Private-Equity-Company-Memo/dp/B00BG6Y6IY/) is a good primer. The keywords are: relentless focus on a small set of changes, strong financial discipline, limited patience, ruthless efficiency. 

When done well, PE genuinely creates more companies that are worth more. When done poorly ... well, there are plenty PE horror stories that are only a quick google away.

Obviously these PE firms don't buy one company at a time. Quite often they run a portfolio of 5-10 of these companies, and will buy add-ons to integrate with the core 5-10 companies. Now considering that the companies involved in this structure with Anthropic are among the largest on the planet, those numbers are huge. Blackstone for instance controls close to 250 companies, not counting the various add-ons and other deals they are involved in.

This is the access that Anthropic is looking for. A rotating cast of companies where they have direct access to the people pulling the strings.

## The JV
At the very high end of the enterprise bracket, the implementation players are the typical big consulting players selling transformation services; but now with AI. This new JV however is explicitly targeting the mid market. 
Those businesses that can't necessarily afford McKinsey and Accenture level fees, and don't have in-house capability either. That's the sweet spot for forward deployed engineers and solve the implementation bottleneck. Or as the press release so nicely puts it "democratizing access to forward deployed engineers". 

You could achieve this with traditional partnership structures of course, but the JV has a few benefits. 

The money matters. PE firms putting up $300m each is a statement of intent to the market. You can't write off that kind of investment as "a quick experiment". This has the financial backing to look and feel like a durable business. And unlike GTM style partnerships which tend to be pretty loose, you don't walk away from this kind of investment.

One clear benefit is that Anthropic stays involved in the deployment, rather than relying on an implementation partner. And because of that, they keep the feedback loop. What works, what didn't, where are clients struggling. Even if it doesn't lead directly to training, it certainly shapes the direction of the products. Call it deployment intelligence.
And with that ever evolving product, comes a need to stay involved with these companies for a longer time. So you're moving from a typical transformation engagement with a clear end, to an ongoing relation. Even in the press release, they already state explicitly: *"Claude’s capabilities change on a monthly or even weekly basis, which creates a different kind of engineering challenge than traditional software deployment. The systems that companies build with AI need to evolve as the models underneath them improve."*

So what this new venture really is is a company that will have a long running recurring relationship with their clients.

Great as this all sounds, between a PE firm's goals and the JV structure there are a few concerns worth highlighting.

## Conflict of interest
The immediate reaction of everyone is that this screams conflict of interest. 
PE firm buys company with investor money. PE firm mandates that company spends some of that money with the AI company they also control.

While PE has always had the ability to control some of the operations of the companies they own, LP could always rely on what's called fiduciary duties. The concept that the PE ownership deliver impartial advice, to the best interest of making the company more valuable, entirely aligned with the LP.
And while this new JV might fill that role as "best advice", there's at least a hint of lesser impartiality now that the PE owns part of that JV.

This is however not a new situation, and falls under related party transactions. It is one of the most scrutinized areas, where both the SEC in the US and FCA in the UK look strongly on keeping this kosher.
One of the common solutions to this conflict is called a fee offset. Remember that GP get paid a management fee by the LP. The offset is where some, or at times even all, the related party fees get deducted from the management fee. The GP is effectively paying the related party out of their own pocket that way.

I'm not one to buy into conspiracy theories or assume bad intentions. The structure simply bakes in a conflict of interest that, at a minimum, will deserve some scrutiny from LP and a clear answer on who pays what.

## Improving the business
Earlier I mentioned PE putting operational teams in a business. Those teams already have playbooks. So typically they put existing senior leadership into new businesses with the express aim to "do what you've done in the previous one". I know, I'm one of those.

The principle behind these playbooks rely on pattern matching. If you've seen one of these before, you'll have the experience and judgment to do another. You've learned from your mistakes and your successes. Crucially though, in the process you have built up two very strong muscles: judgment and domain understanding.

This is the first area I'm concerned. Forward deployed engineers typically aren't domain or industry experts. Instead, they are AI implementation experts. They know how to get the best out of Anthropic's products. They don't necessarily know how to adjust a pattern for the reality of a procurement team in a small FMCG business, or how to roll up the shared IT needs of a group of vet clinics.
And while the standard answer of every transformation project is "that knowledge comes from the domain experts already in the company", we all know that 
(a) it won't be documented
(b) it's likely not easy to explain 
(c) John who knows everything actually left two years ago

It's a classic transformation consulting problem, but now with AI. And AI, with it's inbuilt lack of judgment or ability to learn and contextualize to the organization, is likely going to make this worse rather than better.

## But we have data
One of the defining qualities of mid market companies, particularly towards the lower end of the mid market, is that their internal data is underdeveloped. And the data there is is inevitably siloed and comes with a large need for interpretation. At best it looks like a few dashboards and a set of spreadsheets. At worst it's a CTO manually running a query directly on a production database. 
And you won't find much controls or governance to ensure data consistency, correctness or any of those good practices. In fact, decision making is by intuition and experience and then justified by select data, rather than justified from data. 
All of that of course creates a perfect storm for any AI project to fail before it even starts. The first job is cleansing, standardizing and centralizing the right data in a sensible structure. 
My guess is that the JV is going to do a lot of data cleansing and ETL work while they grab a few bits of low hanging fruit. Classic technique of showing momentum with some quick wins, while the hard problems are ideally worked on in the background. Nobody will get budget for an AI program that begins with "no AI for the first nine months".
Also, if any of this sounds familiar you've clearly been part of previous incarnation of transformation digital transformation.
I'd be happy to be proven wrong, but this could easily become "just another tool"; much like we all needed an ERP, a CRM, a HR system, a Cognos BI cube, a data warehouse, ... . We'll now just also need agentic-ness. 

## And then we leave?
In my detour into PE earlier I said PE holds for 4-7 years and then tries to sell. So what exactly happens with this deeply embedded AI when they sell?

In the old days it was pretty simple. You bought the business, the capability you developed stayed with the business and the acquirer bought the resulting benefits while you walked away. 
In this new model however, the JV is building up more and more knowledge of each of these businesses and specifically how each firm operates within them. At the end of the day, the point of the JV was to get access to the PE playbooks as much as their network. 
Presumably now the AI sticks around, because after deeply embedding Claude everywhere you're not going to suddenly rip it out for ChatGPT. But the knowledge you keep building accrues back to the JV even though the PE firm who was aligned with the JV no longer owns the business. 
Instead, the changes the new PE firm makes (and therefore constitute their playbook) are now pushed back to the JV too. So basically, you get the inside track on a competing PE firm's operating manual. That's fine if you're part of the same JV. If you're not though, this feels like the JV folks double dipping. 
On the one hand they get access paid for the implementation, and on the other they get to see more playbooks from outside their portfolio to bring back to their own companies. 
The language on how this usage and data feeds back and who gets to use the insights is going to become a new element in due diligence, mark my words.

And while we're talking about selling. The goal is of course to present the business in the best possible way, including strong financials. As a GP owning a business means all the incentives are aligned to high margin; possibly even leaving the JV with a little lower prices to increase margins in the portfolio company. 
The moment the ownership shifts, this dynamic disappears. The JV may have built the engine that drives the margin, but if it's not fairly priced it may have delivered value for the company at the expense of value in the JV. It's another lever to pull, and someone will pull it.

## Portfolio risk
PE firms ultimately operate a portfolio of companies, often in a similar space or industry. Again, one of the PE strengths is pattern matching across that group. So it makes sense to stay focused on a single area.
And from the press release: some of the largest opportunities for AI sit in industries like healthcare, manufacturing, financial services, retail, real estate, infrastructure, and more. 
Those are for the most part quite heavily regulated industries. The kind where being wrong can ruin a company.
Now in a pre-AI-JV if a playbook was poorly implemented in one business that was painful for the business but the rest of the portfolio was uncorrelated.
On the other hand, if we're now going to shift more and more of that playbook execution to a central source, we are effectively moving the risk. The same dynamic that makes this concentration attractive, makes it devastating.
One bad playbook no longer ruins a company, it ruins the portfolio.

In a world where the JV was just another independent vendor, each company could decide if adopting this playbook through this vendor was a good idea. In a world where the PE owns the JV, that decision is no longer questioned.

## So, benefits?
You can't end a discussion about PE without benefits. What value is created here?

Well, Anthropic gets their distribution engine. And assuming that shows signs of life quickly, that will become a driver for valuation in a potential IPO.
Anthropic also keeps a tight feedback loop from implementation since there are no independent implementation partners in between. That should help them improve their product.

On the PE side. The GP have just set up a high margin service business that will stay with their portfolio companies after they're gone. And the companies they control are the clients of that business. Even if there's some fee offset early on, the important part is that this revenue stream likely outlives the investment. Uncorrelated returns that don't need to be shared with LP.

The LP on the other hand gets possibly better exit valuations, but by and large bears most of the risk of misalignment, implementation failure and otherwise misallocated investment decisions. 

The portfolio companies, in the end, are going through the new wave of transformation. Maybe this time it will be different.