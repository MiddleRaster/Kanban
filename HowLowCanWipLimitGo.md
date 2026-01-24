---
layout: default
title: How Low WIP Limits Can Go
---

Things that drive me nuts:

1. When I hear people say they're doing Kanban but don't have any WIP limits.
2. People think that limiting WIP is all about avoiding multi-tasking (rather than cycle time).
3. People are completely clueless on what to set the WIP limits to.

If you've read me post on [Kanban and Queueing Theory](KanbanThoughts.html), you know that the lower the WIP limit, the shorter the cycle time.
And if the team members swarm on bottlenecks, the throughput goes up.

So, how low should we go?  Let's think it through.

## WIP limit == 1 for each worker

This is my default starting point.

One common problem that a WIP limit equals to the number of workers (devs, in this case) solves is code reviews:  I hear all the time that people say that pull requests or code reviews are the bottleneck.
And I understand it - people want to get their own work done.
But with a nice tight WIP limit (equal to the number of devs), the once a dev's task is done, he's blocked by the WIP limit.
There's nothing for him to do except to do the code review (if it's not his own). If there's no code review to do, he should swarm on the bottleneck, either upstream or downstream, and if he can't tell where the bottleneck is, he can pair with another dev.
