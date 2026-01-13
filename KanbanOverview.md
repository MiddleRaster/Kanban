---
layout: default
title: Kanban Overview
---

# Kanban Overview

## Kanban Features

1. Kanban has a series of **columns**, containing queues of work, represented by **cards in priority order**.
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

## How Cards Flow Through the System

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
