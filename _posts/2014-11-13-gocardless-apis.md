---
layout: post
title: How GoCardless Manages Two APIs
---

[GoCardless](https://gocardless.com/ "GoCardless") is a recurring payments company with a twist: instead of using credit cards they operate with direct debits. They’re based in the UK and currently help over 30,000 businesses manage their recurring direct debits. They went through [YCombinator](https://www.ycombinator.com/ "YCombinator") and now have investment from companies like [Benchmark Capital](http://www.benchmark.com/ "Benchmark Capital"). Their business started in 2011 when direct debits were still seen as something complicated and only accessible to large companies. GoCardless simplifies the direct debit process so that anyone can easily use it by consuming one of their two APIs.

![](/img/APIChangelogGoCardlessInterview.png)

The original [GoCardless API](https://www.apichangelog.com/api/gocardless "GoCardless API Changelog"), was built 3 years ago and was the core of the GoCardless offering. The API was an abstraction of direct debit services which have classically only been available to large enterprises. Since launching their service the GoCardless team have learnt an enormous amount from running and launching one of the highest growth API based companies in the FinTech space. We talked with [Grey Baker](https://www.linkedin.com/in/greysteil "Grey Baker"), their VP Engineering, and [Philip Harrison](https://www.linkedin.com/in/harrisonphilip "Philip Harrison"), one of their engineers, to understand what how they operate their two APIs and what challenges they went through.

After three years GoCardless have learnt a great deal about managing APIs. According to Grey Baker, their overarching learning outcome from this experience of building and scaling an API business is that “**the actual API change process is by far the hardest part of the process**”. Building the API requires some insight, however is not earth shattering from a technology point of view. The real skill is evolving your learning as a business into your API. 

Currently GoCardless offers two distinct APIs:

* [GoCardless V1](https://www.apichangelog.com/api/gocardless), which is all about **simplicity**, is focused on the SMB market and has had [some change taking place](https://www.apichangelog.com/changes/4441b2f0-8a78-4914-95e2-3bc45cc90b08), however is still 100% backward compatible. 
* [GoCardless Pro](https://www.apichangelog.com/api/gocardlesspro), which has a richer **feature set**, is targeted at the larger clients who require additional functionality from the service.

Currently to have these two APIs operating they need to maintain a compatibility layer. Because managing both APIs is not always easy they’re planning on converging them over the coming six months. The first one operates of [JSON Schema](http://json-schema.org/ "JSON Schema") and has larger abstractions than the Pro service. 

Major key learnings are:

* There’s a need to differentiate between the **scale of change** on different customers.
* Changing from a flat to a nested representation **does not change function but does change usage**.
* You should **do pagination as early as possible** because it’s a pain to implement it at a later stage.
* **Set fixed dates for incremental changes**. Outline the dates early in header information to ensure.
* **Have a clear communication channel with your developers**, ideally knowing each developer down to the contact details, version of API used and method last called.

GoCardless is also a heavy API consumer, as it has to interact with various external services. To better manage their consumers they internally use JSON schema to provide very strict contracts between services. They’ve also created a mock server so that their API consumers can be better tested against the JSON schema.
