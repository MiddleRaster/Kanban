---
layout: default
title: Thoughts on Kanban and Queueing Theory
---

I have observed that a lot of people misunderstand Scrum.
Too often they do what has been called "ScrummerFall" or "Cargo-cult Scrum," the most common failing being taking their current process and merely applying the Scrum-ish terms to whatever they're doing now.

I'm seeing the same thing, if not more so, in Kanban, most notably when people claim to be doing Kanban but don't have any WIP limits.
I think it's worse in Kanban because queueing theory is so very counterintuitive.
Proof:  we have traffic jams, lots of them, all the time.
If we naturally understood queueing theory, that wouldn't be the case.

So, let's start off with a simple quiz:  which of the following are true and which are false?
1. **Shipping more frequently is the goal.**
2. **High team utilization is a good thing.**
3. **The more productive a team is, the sooner you can ship.**
4. **Projects will be more successful if you get them right the first time.**

I'll answer each of these as we go along, but if you want to see the answers now, click [here](answers.html).

## Kanban Beginnings

The word "Kanban" comes from Japanese, where it means "signal" or "signboard." 
It came from the Toyota Production System, developed in the auto manufacturing industry between 1948 and 1975.

The main idea is this:  the American way to produce car parts (say, hoods) is to set up this huge machine and let it stamp out a bazillion hoods, because once it got going, it was nice and reproducible.
But if you stopped it, you'd have that startup time again where it was producing defective hoods.
So, in the American way, you make a pile of hoods (inventory) and have them on hand for when you make the rest of the car.

At the time, Japanese cars were not of high quality, but Kanban really turned that around.
The idea is exactly the opposite of having a big pile of inventory and instead building just what you need, just when you need it:  just-in-time or JIT.
And they did it with these signal cards.
For example, if you are a worker in a factory making cars and you need a radiator, you go to the radiator station, take the one radiator that's there and replace it with a card that says, "Make another radiator."
The same thing happens with all the other parts.
And that allows you to be responsive to the market:  if you need to start building Supercharger-turbo-EV-hybrid cars all of a sudden, you're in a good position to do so.

Now, doing just-in-time isn't easy. When they first started on this path, it took Toyota engineers and technicians two weeks to set up the press machine to stamp out hoods, but after a while, they got the setup time down to an hour.

That's a great story, because Japanese cars are of extremely high quality now.
But how does this apply to software?

## Kanban Features

1. Kanban has a series of **columns**, containing queueus of work, represented by **cards in priority order**.
2. Kanban has **WIP limits**:  that is, "work-in-progress" limits on each activities column(s). These WIP limits limit how much work can be in your column(s). Electronic Kanban boards will prevent you from pulling a card if you're at the limit. If you're using a whiteboard, then it's set by policy that must be obeyed.
3. Kanban is **pull-model**:  work isn't pushed at you. Instead, when you're freed up, you pull the most important thing to do from your backlog.

Here's how I like to set up my team's Kanban board:

<table>
  <tr>
    <td>
      <div style="border:1px solid black; padding:6px;">
        <strong>Backlog</strong><br>
        <em>WIP: ∞</em><br>
        🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br> <br> <br> <br> <br> <br> <br>
      </div>
    </td>
    <td>
      <div style="border:1px solid black; padding:6px;">
        <strong>UX</strong><br>
        <em>WIP Limit: 25</em>
        <table>
          <tr>
            <td><strong>Working</strong><br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br> <br> <br> <br> <br> <br> <br> <br> <br></td>
            <td><strong>Done</strong><br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br> <br><br> <br> <br> <br> <br> <br> <br> <br> <br> <br></td>
          </tr>
        </table>
      </div>
    </td>
    <td>
      <div style="border:1px solid black; padding:6px;">
        <strong>Dev</strong><br>
        <em>WIP Limit: 25</em>
        <table>
          <tr>
            <td><strong>Working</strong><br>🟨 Story<br>🟨 Story<br>🟨 Story<br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br></td>
            <td><strong>Done</strong><br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br> <br> <br> <br> <br> <br> <br></td>
          </tr>
        </table>
      </div>
    </td>
    <td>
      <div style="border:1px solid black; padding:6px;">
        <strong>QA</strong><br>
        <em>WIP: 25</em><br>
        🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br>🟨 Story<br> <br> <br> <br> <br>
      </div>
    </td>
    <td>
      <div style="border:1px solid black; padding:6px;">
        <strong>Final Done</strong><br>
        <em>WIP:  ∞</em><br>🟨 Story<br>🟨 Story<br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br></td>
      </div>
    </td>
  </tr>
</table>
All done

















