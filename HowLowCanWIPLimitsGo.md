---
layout: default
title: "How Low Can WIP Limits Go"
permalink: /HowLowCanWIPLimitsGo.html
---

# How Low Can WIP Limits Go?

Some things that drive me nuts:

1. When I hear people say they're doing Kanban but don't have any WIP limits.
2. People think that limiting WIP is all about avoiding multi-tasking (rather than being all about cycle time).
3. People set the WIP limits to ludicrously high values and then wonder why they aren't seeing shorter cycle time.

If you've read my post on [Kanban and Queueing Theory](/Kanban/KanbanThoughts.html), or played with my [Kanban simulator](/Kanban/KanbanSimulator.html), then you know that the lower the WIP limit, the shorter the cycle time.
And if the team members swarm on the bottleneck(s), the throughput goes up.

So, how low should we go?  Let's think it through.

## WIP limit = # of devs (or other kind of worker:  UX, QA, etc.)

This is my default starting point:  the WIP limit for the dev columns (plural!) is equal to the number of devs.

A WIP limit equal to the number of devs solves a common problem, a bottleneck at code-review:  I hear all the time that devs aren't doing code-reviews (or PRs) for each other.
And I get it; people want to get their own work done.

Suppose you have 3 columns for dev:  working, code-review, done.
And with a nice tight WIP limit (equal to the number of devs), once a dev's task is done, he moves his card to the code-review column and then he's blocked by the WIP limit, because pulling a new card into the dev columns would be over the WIP limit.
There's nothing for him to do except to do the code-review for one of the other devs. which is exactly what we want.

If there's no code review to do, he should swarm on the downstream bottleneck, or if dev is the bottleneck, pair with another dev.

Why are people so hesitant to try what I consider the obvious default?
Because they worry that a dev might be blocked for some reason (and they don't want someone idle, which is wrongheaded anyway: see my section on [utilization](KanbanThoughts.md#utilization)).

But my question is:  if a dev task is blocked (e.g., by a dependency that isn't ready), then why was the story in the ready backlog at all? It *wasn't ready* to go.

Another thing: by being blocked, the dev is forced to get himself unblocked, for example by pairing with the (possibly external) team member who is handing out the dependency, instead of waiting around for the blockage to be resolved (and thus making cycle time go up!).


## WIP limit = (# of devs) / 2

Let's tighten things up a bit more:  the WIP limit is half the number of workers.

In this case, you only need two columns for dev (working, done), because the devs are forced to pair program all the time.
If you pair all the time, it's like you're doing continuous, real-time code-reviews, so you don't need an explicit column for something they're doing all the time anyway.

If the pair is blocked or starved for work, they swarm either downstream or upstream (or both).


## WIP limit = 1

Beyond pairing is mobbing.
The entire team mobs together, working on one story at a time, until it's done.

This is equivalent to 100% swarming at all times and so gives very high throughput.

If you have enough people of each discipline to form two teams, you could have two teams mobbing at once, thus doubling throughput.

The columns are: team working, team done.
Of course, if you're mobbing on everything, you don't really need a Kanban board.


## WIP limit < 1 (Franctional WIP)

Suppose you're doing DevOps, where the Devs own Operations, but there's a QA team involved, in between.

You could set up your columns like this:  dev working -> dev done -> qa working -> qa done -> ops working -> ops done.

You could then assign a "Fractional WIP":  that is, a single number (e.g., 1) that's **split across both the dev columns and the ops columns** (but not QA columns).

Similarly, if you have UX designing in front of dev and QA, but doing UX usability testing after QA's testing, then this would be a single number split across the UX columns before dev and the UX columns after QA.


## Summary

Smaller WIP limits mean shorter cycle times.

At the very least, start with the upper-end WIP limit I recommend: the number of workers in a discipline.
If you want even shorter cycle time, try pairing or mobbing (and be aware that hygiene and interpersonal awareness are more important than ever).

Happy WIP limiting!

Back to [MiddleRaster's Thoughts](https://middleraster.github.io).



