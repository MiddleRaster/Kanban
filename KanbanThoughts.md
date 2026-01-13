---
layout: default
title: Thoughts on Kanban and Queueing Theory
---

# Thoughts on Kanban and Queueing Theory

I have observed that a lot of people misunderstand Scrum.
Too often they do what has been called "ScrummerFall" or "Cargo-cult Scrum," the most common failing being taking their current process and merely applying the Scrum-ish terms to whatever they're doing now.

I'm seeing the same thing, if not more so, in Kanban, most notably when people claim to be doing Kanban but don't have any WIP limits.
I think it's worse in Kanban because queueing theory is so very counterintuitive.
Proof:  we have traffic jams, lots of them, all the time.
If we intuitively understood queueing theory, that wouldn't be the case.

So, let's start off with a simple quiz:  which of the following are true and which are false?
1. **Shipping more frequently is the goal.**
2. **High team utilization is a good thing.**
3. **The more productive a team is, the sooner you can ship.**
4. **Projects will be more successful if you get them right the first time.**

I'll answer each of these as we go along, but if you want to see the answers now, click [here](Answers.html).

## Kanban Beginnings

The word "Kanban" comes from Japanese, where it means "signal" or "signboard." 
It came from the Toyota Production System, developed in the auto manufacturing industry between 1948 and 1975.

The main idea is this:  the American way to produce car parts (say, hoods) is to set up this huge machine and let it stamp out a bazillion hoods, because once it got going, it was nice and reproducible.
But if you stopped it, you'd have that warm-up time again where it was producing less-than-perfect hoods, until it was warmed up.
So, in the American way, you make a pile of hoods (inventory) and have them on hand for when you make the rest of the car.

At the time, Japanese cars were not of high quality, but Kanban really turned that around.
The idea is exactly the opposite of having a big pile of inventory and instead building just what you need, just when you need it:  just-in-time or JIT.
And they did it with these signal cards.
For example, if you are a worker in a factory making cars and you need a radiator, you go to the radiator station, take the one radiator that's there and replace it with a card for the radiator-maker that says, "Make another radiator."
The same thing happens with all the other parts.

And that allows you to be responsive to the market:  if you need to start building supercharged-turbocharged-EV-hybrid cars all of a sudden, you're in a good position to do so.
Now, doing just-in-time isn't easy. When they first started on this path, it took Toyota engineers and technicians two weeks to set up the press machine to stamp out hoods, but after a while, they got the setup time down to an hour.
That's a great story, because Japanese cars are of extremely high quality now.
But how does this apply to software?

For starters, it answers the first question of our quiz:  "is shipping more frequently the goal?" 

No.  **Responsiveness or shorter cycle time is the goal.**

For example, you could ship a product every week, but still have 3-year-long pipeline: not responsive. 
Alternatively, you should ship a product every week, and have a 2-day-long pipeline:  very responsive.

This is our first queueing theory fact:  cycle time and throughput are separate characteristics of a queue.

## Kanban Features

1. Kanban has a series of **columns**, containing queueus of work, represented by **cards in priority order**.
2. Kanban has **WIP limits**:  that is, "work-in-progress" limits on each activity's column(s). These WIP limits limit how much work can be in your column(s). Electronic Kanban boards will prevent you from pulling a card if you're at the limit. If you're using a whiteboard, then it's set by policy that must be obeyed.
3. Kanban is **pull-model**:  work isn't pushed at you. Instead, when you're freed up, you pull the most important thing to do from your backlog, that is, the column to the left of your column(s).

Here's how I like to set up my team's Kanban board:

<table style="table-layout:fixed; width:100%;">
  <tr>
    <td style="width:120px; vertical-align:top;">
      <div style="border:1px solid black; padding:6px; height:500px;">
        <strong>Backlog</strong><br>
        <em>WIP: ∞</em><br>
        🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>
        <br><br><br><br><br><br><br>
      </div>
    </td>
    <td style="width:200px; vertical-align:top;">
      <div style="border:1px solid black; padding:6px; height:500px;">
        <strong>UX</strong><br>
        <em>WIP: 25</em>
        <table style="width:100%; table-layout:fixed;">
          <tr>
            <td style="width:50%; vertical-align:top;">
              <strong>Working</strong><br>
              🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>
              <br><br><br><br><br><br><br><br><br>
            </td>
            <td style="width:50%; vertical-align:top;">
              <strong>Done</strong><br>
               🟨 <br> <br> <br> <br>
              <br><br><br><br><br><br><br><br><br><br><br>
            </td>
          </tr>
        </table>
      </div>
    </td>
    <td style="width:200px; vertical-align:top;">
      <div style="border:1px solid black; padding:6px; height:500px;">
        <strong>Dev</strong><br>
        <em>WIP: 25</em>
        <table style="width:100%; table-layout:fixed;">
          <tr>
            <td style="width:50%; vertical-align:top;">
              <strong>Working</strong><br>
              🟨 <br>🟨 <br>🟨 <br>
              <br><br><br><br><br><br><br><br><br><br><br><br><br>
            </td>
            <td style="width:50%; vertical-align:top;">
              <strong>Done</strong><br>
              🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>
              <br><br><br><br><br><br><br>
            </td>
          </tr>
        </table>
      </div>
    </td>
    <td style="width:120px; vertical-align:top;">
      <div style="border:1px solid black; padding:6px; height:500px;">
        <strong>QA</strong><br>
        <em>WIP: 25</em><br>
        🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>🟨 <br>
        <br><br><br><br><br>
      </div>
    </td>
    <td style="width:120px; vertical-align:top;">
      <div style="border:1px solid black; padding:6px; height:500px;">
        <strong>Final Done</strong><br>
        <em>WIP: ∞</em><br>
        🟨 <br>🟨 <br>
        <br><br><br><br><br><br><br><br><br><br><br><br><br><br>
      </div>
    </td>
  </tr>
</table>

### How Cards Flow Through the System

Let's follow a card through the system; let's follow the top priority card in the product backlog.

So if and only if there is capacity from a UX worker, that is, if and only if the number of cards in both of the UX activity's columns is less than the WIP limit, then the UX worker pulls the card from the backlog and puts it in the UX "working" column.
When he (or she (I'll use "he" throughout as it's less typing)) is done with it, he moves it to UX's "Done" column.

So, the germane fact is that no one *pushes* work onto a worker:  it's a *pull-model*.
Now, if UX is still not at its WIP limit, the UX worker can pull yet another card and work on it.
But if UX is at the WIP limit, then he's *blocked* and is idle.

Continuing, a dev sees the card in UX's done pile and iff he has capacity (that is, if number of the cards in the dev columns is below the WIP limit), then he pulls the card into dev's "working" column and starts working on it.
Again notice it's all pull-model.
When he's done, it goes in dev's "done" pile, and he's ready to pull another, if he's below the WIP limit.
If there isn't another card to pull out of UX's "done" pile, then he's *starved* for work and again is idle.

The same process continues to the QA activity, except that when QA is done with a card, it goes onto the "Final Done" pile.

### Calculating Cycle time

Cycle time is the time from when a card is first pulled from the backlog until it's put into the Final Done pile.

While a card is sitting in the product backlog, it doesn't count against cycle time, because there's been no work done on it, not even design:  each card is just a story and maybe some "done" criteria.

It's like someone starts a stopwatch when the card is pulled from the backlog and stops the watch when putting the card in the final done column.
And in fact, in reality, with a physical Kanban board, it's a good idea to write the date and time on the card when it's pulled from the backlog and again when it's moved to the final done pile.
The difference between these two timestamps is the cycle time for that card.

## Kanban Simulator Exercise

When I was a dev-instructor at *StupendousCorp*, when teaching our Agile/Estimations/Kanban class, I would talk about cycle time and queueing theory, and though people nodded, I could tell from what they said they didn't really gret it.
No further explaining was going to help, so I wrote a Kanban simulator.

So, here's an exercise. Suppose you have a tiny team with 1 UX person, 1 Dev person and 1 QA person.
And suppose the UX work gets 3 cards done in a day, dev gets 2 cards done per day, and QA does 1 card per day.

Clearly, **throughput is completely determined by the slowest step**, which in this somewhat contrived case is QA.
So I'm setting up some bottlenecks.

Your task is to minimize cycle time, but do so cost-effectively.
One way to shorten cycle time is to hire more people, but that's expensive and you don't have budget. So you can't do that.
You've already hired the best people you can find, so more training or other techniques to increase QA's output are not going to work.

All you can fiddle with is the WIP limits. Go ahead and play with the [Kanban Simulator](KanbanSimulator.html), until you have cycle time (also called "Sojourn time") minimized.

Click [here](Answers2.html) to see if you got it right.

Here's the important bit:  **changing the WIP limits didn't change the throughput** - it's still 0.97 cards per day (it's not exactly 1.00 because of "entrance effects":  it takes a day or two for the first card even to get to the bottleneck at QA).

So, UX (or dev) being idle doesn't hurt the throughput. But it presents an opportunity.




