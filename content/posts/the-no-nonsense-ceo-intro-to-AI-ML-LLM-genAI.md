+++ 
draft = false
date = 2025-04-15T14:22:13+01:00
title = "The no nonsense ceo intro to AI, ML, LLM and genAI"
description = ""
slug = ""
authors = ["Klaas Ardinois"]
tags = []
categories = []
externalLink = ""
series = []
+++

I love a good onion diagram when something has layers! So here's my gen-AI onion.

# The Gen AI Onion
![Onion Diagram showing the layers of AI](/images/posts/AI-Onion.png)

# Artificial Intelligence (AI) & AGI
In computer science AI is a broad umbrella term. It’s any technology that helps mimic cognitive functions. That can range from seeing (i.e. classifying objects in an image, or recognizing handwriting), and hearing (“speech to text” transcriptions) to more abstract tasks such as responding to a question or applying a series of logical rules. AI is not really a technology in itself, but a group of techniques that help computer programs “learn” how to perform these functions.

*Narrow AI vs AGI (Artificial General Intelligence, aka strong AI)*

Narrow AI is software trained on a specific topic such as “image recognition”, “predicting if you’ll like a movie”, “generating text based on input text”, … .    
AGI on the other hand is the idea of an intelligent system that has human-like cognitive abilities, and can perform ***and learn*** new tasks independently and autonomously.   
It might be tempting to think that AGI is the sum of a set of Narrow AI, but unfortunately a part of AGI is that it can take these different systems and combine them. When people talk about multi-modal, this is why that matters. Can I recognize something in an image, listen to a conversation and put those 2 events together to learn and remember something new\!

**The CEO perspective**

* Practical business applications today use narrow AI and you should focus on specific problems you need to solve  
* When vendors claim "AI", make them spell out what they’re actually doing. It’s important to ask \- do they have proprietary trained models? How much do they know about error rates of their underlying model? How does adding “AI” make a demonstrable difference to your goal with them?   
* AGI and anything approaching ongoing self-learning or broad autonomy are still mainly theory and areas of fundamental research; rather than ready-made products or solutions. Despite the fact there has been significant progress in the field of AI

# Machine Learning (ML)

Now we’re getting into how software actually accumulates information and “learns”. Machine learning is the application of statistical techniques to analyze existing data. It’s asking the question: are there relevant patterns and correlations in this dataset? And then use those to make inferences (\~ ”predictions”) about new data.

In a trivial example, think of it as drawing a trendline on data in excel. And then using the equation of that trendline to make predictions about new data.

***Note**: There is a different branch of learning next to ML called “Symbolic AI”. It is currently getting very little attention (these things come and go in waves). Where ML relies on observing patterns in data, Symbolic AI relies on humans coding fundamental rules in a system. And the system “learns” by executing and combining those rules appropriately (i.e. (1) all swans are birds. (2) all birds can fly. \-\> “learned behavior”: swans can fly)*

*Most independent researchers in the AI community believe that only using ML derived AI will never produce AGI.*

**The CEO perspective:**

* ML is an excellent solution if you have a substantial amount of good quality data  
* Many common ML use cases (customer segmentation, recommendations, … ) have near off the shelf providers. Your problem is likely not unique, even if your data is  
* If you go down the custom model path, be prepared to keep investing. As your business and data changes, your model will drift and need retraining

# Deep Learning (DL) & Generative AI

A subset of ML techniques that use **neural networks** for learning. While some of the initial concepts developed in the 1950s&1960s are inspired by our understanding of the human brain at that time, deep learning has little to do with neurobiology. It’s a refinement on the statistical approaches used to “learn” in the broader ML landscape. 

The particular techniques in Deep Learning rely on combining layers of units (the preferred jargon nowadays, instead of neurons). And a unit has some inputs, a level of importance (weight) for each input, and a mathematical function that takes those weighted inputs and creates a single output.

Think of it as a machine with a huge amount of dials (the weights) you can tweak. And by moving them up or down you change the output. The goal is to find the optimal setting for all dials so that your input produces the desired output as close as possible. That process, but automated, is the learning phase for a neural network.  
And once you’ve finished setting your dials, you can run any input you want and “predict” the result.

Deep Learning, as the name suggests, is all about how models learn. **Generative AI** on the other hand is using those models to create new things, as opposed to for instance classifying images with dogs and cats. It’s a particular application of DL models. And depending on what you’re generating, you’ll end up with language models, image models, … . Which in turn can be used to power chatbots, social media post generators, video creators, notetakers, … .

**The CEO perspective**:

* Deep Learning requires significant computing resources and rare specialized talent to build and run effectively  
* Best suited for complex pattern recognition in unstructured data (images, audio, natural language).   
* Unless models are your core business, bring in a specialist 3rd party and/or use off the shelf models for as long as possible. Focus the team on minimizing switching costs of models, as they evolve incredibly quickly

# Large Language Models (LLMs)

LLMs are *deep learning models* trained on huge amounts of text. They’re why tools like ChatGPT can write emails, code, FAQs, and even strategic plans that sound plausible. Feel free to take “text” very broad to include transcripts of movies and youtube videos, digital copies of classic books, everything on social media, press releases, earnings calls, radio interviews … you name it. 

And because it’s ultimately still a Deep Learning trained model inside a Machine Learning world, it really is also just a statistical model under the hood. And as any statistical model there are no inherent hard rules or knowledge. There are only statistical patterns that are incredibly close to approximating input & output from training.

The key differentiator between today’s LLM and earlier predictive-text models is the attention mechanism. It’s what allows current models to stay “on topic” in a conversation, rather than merely predicting “the next word”. The mechanism allows to relate terms that are far apart in a text, and adds context. It’s how the model differentiates the bat in “I swing my bat” and “the bat is in the cave”.

**The CEO perspective**:

* Can rapidly augment knowledge work, content creation, and customer interactions  
* Implement with human oversight \- outputs require verification and regularly contain fabricated information  
* Focus on integrating LLMs into existing workflows rather than complete automation  
* This is a field that is highly in flux right now with very little best practices. Be prepared for anything you build to overnight stop working or be outdated. Make small bets, no tight coupling, no critical functions.

# Models and Agents

However you got it trained, the goal of a model is to be able to predict output based on unseen input data. It doesn’t matter if that prediction is an image for your website, a summary of your meeting notes, a recommendation on your checkout page,... . It’s just an engine that’s been tuned to deliver an output based on patterns it has learned. 

“Agents” have been around in computer science forever. They’re a catch-all term for software that does a task autonomously on behalf of a user. “AI agents” in that regard are simply bits of software that do a task, but happen to use a trained model in the process. The kind of decisions you allow a statistical model to make on your behalf is a measure of the autonomy the agent has. But really it’s also a statement on how well you think the model fits the task.

Agentic solutions is where you combine several of these agents, perhaps even orchestrated by an “overseer” agent instead of a traditional workflow engine, to work through a high level task. Think about perplexity or manus, who will take your request, draft a plan, google search or execute small code snippets and combine it all in a report for you. They’re excellent illustrations of what an agentic solution technically can achieve today.

There is however a huge caveat in AI agentic systems and autonomy. Underneath it all are still statistical models with inherent limitations and error rates. And the more you chain model-based autonomous decisions together, the more the error rate multiplies and the harder it becomes to pinpoint and adjust when it goes off track. 

**The CEO perspective**

* Data Scientists build models, but they need engineers to integrate that in products to bring ROI  
* AI Agents are just software wrappers around a model. They’ll only ever be as good as the model.  
* Extreme caution when you let a model interact with customers directly or let it sit in business critical situations.


# Buyer Beware

AI is a field that has seen waves of huge advances alternated with periods of neglect. As hardware advances, so does the research it enables. The goal of AI, as a field looking for systems that can perform tasks requiring human level intelligence, hasn’t really significantly changed since the 1950s. Yet by the 1950s standard, a lot of what we take for granted today would be considered AI. Think about your netflix recommendations, phone and meeting transcripts, advanced spreadsheet functions, automatically tagging a friend in a picture, … . 

**If anything, the hallmark of progress in AI is probably that we stop calling it AI.**

And therein lies the key for your business: Can you make the AI disappear?

**The CEO perspective**

* Focus on business outcomes, not just technology adoption  
* Think about the ongoing impact on data, maintenance cost and talent  
* Partner with vendors who understand your industry context, not only AI technology  
* GenAI and agent-based solutions will become commonplace. Budget for small bets to learn when and where they add value. Look for scenarios where being wrong has a low impact
