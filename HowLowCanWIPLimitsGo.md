---
layout: default
title: "How Low Can WIP Limits Go"
permalink: /HowLowCanWIPLimitsGo.html
---

# How Low Can WIP Limits Go?

Some things that drive me nuts:

1. When I hear people say they're doing Kanban but don't have any WIP limits.
2. People think that limiting WIP is all about avoiding multi-tasking (rather than all about cycle time).
3. People are completely clueless on what to set the WIP limits to.

If you've read me post on [Kanban and Queueing Theory](KanbanThoughts.html), you know that the lower the WIP limit, the shorter the cycle time.
And if the team members swarm on the bottleneck(s), the throughput goes up.

So, how low should we go?  Let's think it through.

## WIP limit == # of devs (or other kind of worker:  UX, QA, etc.)

This is my default starting point:  the WIP limit for the dev columns (plural!) are equal to the number of devs.

One common problem that a WIP limit equals to the number of devs solves is a bottleneck at code-reviews:  I hear all the time that devs aren't doing code-reviews (or PRs) for each other.
And I understand it - people want to get their own work done.

Suppose you have 3 columns for dev:  working, code-review, done.
And with a nice tight WIP limit (equal to the number of devs), the once a dev's task is done, he moves his card to the code-review column and then he's blocked by the WIP limit, because pulling a new card into the dev columns would be over the WIP limit.
There's nothing for him to do except to do the code-review for one of the other devs. which is exactly what we want.

If there's no code review to do, he should swarm on the bottleneck, either upstream or downstream, and if he can't tell where the bottleneck is, he can pair with another dev.





