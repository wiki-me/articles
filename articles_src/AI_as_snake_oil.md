# The Why and How of Not Treating AI as Snake Oil

I see AI gets added to open source projects. and it seems fairly frequent.

But there is some skepticism about the benefits of AI, one systematic review of research [found](https://cmr.berkeley.edu/2025/10/seven-myths-about-ai-and-productivity-what-the-evidence-really-says/) "AI's productivity gains are highly context-dependent" . one study [found](https://arxiv.org/pdf/2507.09089) AI slows down developer even when they think it speeds them up:

>Before starting tasks, developers forecast that allowing AI will reduce completion
time by 24%. After completing the study, developers estimate that allowing AI
reduced completion time by 20%. Surprisingly, we find that allowing AI actually
increases completion time by 19%—AI tooling slowed developers down.

A [update](https://metr.org/blog/2026-02-24-uplift-update/) for 2026 argued that they can't really measure how AI effects performance reliably due to among other things developers not wanting to work without AI:

>Unfortunately, given participant feedback and surveys, we believe that the data from our new experiment gives us an unreliable signal of the current productivity effect of AI tools. The primary reason is that we have observed a significant increase in developers choosing not to participate in the study because they do not wish to work without AI, which likely biases downwards our estimate of AI-assisted speedup. We additionally believe there have been selection effects due to a lower pay rate (we reduced the pay from $150/hr to $50/hr)

in the [ARC-AGI Series](https://arcprize.org/arc-agi) of AI benchmarks meant to test [fliud intelligence](https://en.wikipedia.org/wiki/Fluid_and_crystallized_intelligence) humans still [outperform](https://arcprize.org/leaderboard) AI on the the arc-agi 2 version of the benchmark. scores on arc-agi 3 are very low.

the bottom line is that automatically assuming that using AI is better is wrong. I suggest regularly benchmarking the outcome of AI against human output or non AI algorithms in [randomized controlled trails](https://en.wikipedia.org/wiki/Randomized_controlled_trial). for example  if you are creating a platform the [shows you the news](https://www.reddit.com/r/opensource/comments/1tfm90j/condenseit_selfhosted_ai_news_digest_mit_licensed/) a random group of users could be asked to rate information from their favorite news website. the ratings could then be compared with the ratings of AI outputs. or maybe AI should be rated against the posts on the fediverse or mastodon with the most "likes" or upvotes in the last 24h that have the hashtag "news" or some other hashtag. or some other traditional or simple algorithm.
