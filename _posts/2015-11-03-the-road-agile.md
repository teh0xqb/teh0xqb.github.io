---
layout: post
title:  "The Road To Agile"
image: 'https://cdn-images-1.medium.com/max/2000/1*PaE1yvKD9cfmhQckhqpnOA.jpeg'
date:   2015-11-03 00:06:31
tags:
- agile
description: ''
categories:
- Software Development
serie: learn
---

The Road to Agile — Part 1
===

##### Practices for Project Management during Software Development.

Some of you may have read my previous post — Halloween Horror stories on software development. They keep us up at night. I have been in a lot of, um, interesting work environments, where I don’t have a lot of control on the plan or strategy that the company has.

I have also heard a lot about the theory behind Agile Software practices. The agile buzzword has a special place in my heart. I have only seen glimpses of it during my career. Management usually misuses it. Developers usually know that it’s good for their health. The reality is that I’ve never seen the whole thing in action.

I have introduced its concepts partially, only to achieve partial results. It’s time to take matters into my own hands and explore once and for all how to achieve an unified agile workflow. I document my findings here.

---

### Part I: Training And Preparation

#### The Stakeholders and Product Owner

Get the business side, the development team, and all stakeholders[1] on board. Decide on a product owner — someone who has the final word on the product features, requests, and business needs.

Only one product owner please. I have been in teams where we tried having two. One would make a decision, while the other one wouldn’t know about it. Recipe for disaster. The product owner might know the most about the product. From time to time he might need input from someone else. It’s the product owner’s responsibility to do his research and come back to you to discuss a feature.

Make sure your development team can help make decisions. They should be able to discuss these user stories with the product owner. Now and during the whole process, if needed (an interesting note on empowering the team on the Appendix).

We all have heard that using a whiteboard is a very helpful exercise. Using cards and is a lot better than starting out with any project management software.

[1] Stakeholders: people that might be affected, have a say, or will work on the project.

#### User Stories and The Backlog

Acquire all the required features. You have to sit down with the project owner. Be it your CTO, a client you are working for, a product manager. Sit down, and discuss the system or application throughly. Each feature that you can think of. Draw some mocks with pen and paper.
The product owner might want to deliver them in his own format. The final draft of these will be written as User Stories. The format for the user stories is as follows:

> **Who**, **What**, [optional:] **Why**?

As an example,

> As a *[customer|client|vendor|power]* user, I can scroll down the search result list and, as I approach the end of the list, new items will be added.

[Optional, why:] because we want lazy loading — we don’t have to wait for or look all the results at once. Or… for technical reasons: loading all results at once takes more time and processing power.

The why is not always necessary. It helps the development team discuss the reasoning behind the feature. It should allow the team to examine or change the user story.

Now, insert these stories into a backlog — a long list or queue, where the items on top are of most priority. The items on top should be explained in concrete detail so that a member of the development team can work with it.

## Agree with the team on the definition of ‘Done’

You want to estimate tasks and add deliverables to your user stories, but based on what? Task code completion? Feature deployed to production? Your team needs to be able to establish to what extent you are completing a task. This helps confirm the benefits of the process, while ensuring predictability for task completion.

A feature might take a certain amount of time to get to a Q/A stage, but are there additional steps for deployment? Does done means in production? Or in a test environment?

Agile software practices usually involve writing the tests before or during feature development. If you finish a task, it means the feature is implemented and all the tests are written.

Your company might be on its early stages, and might have to create its own definition of what done means. This is a good sample criteria of what done could mean:

- Code produced (all ‘to do’ items in code completed)
- Code commented, checked in and run against current version in source control
- Peer reviewed (or produced with pair programming) and meeting development standards
- Builds without errors
- Unit tests written and passing
- Deployed to system test environment and passed system tests
- Passed UAT (User Acceptance Testing) and signed off as meeting requirements
- Any build/deployment/configuration changes implemented/documented/communicated
- Relevant documentation/diagrams produced and/or updated
- Remaining hours for task set to zero and task closed

From [All About Agile](http://www.allaboutagile.com/definition-of-done-10-point-checklist/).

Make sure the whole team understands this before creating any estimates. There should be no doubts on what being “done” is.

### The Work Breakdown Structure (WBS) and Initial Guesstimates

Create programmer tasks from the User Stories. Break bigger tasks into subtasks, until you are able to visualize them to completion. You may use a spreadsheet or a project management tool to do this (any comments on tools are welcome).

The estimates are based on size and risk. Let’s start with size. We will use a sequence that forces developers to compare size between subtasks. Use the fibonacci sequence up to 13:

>**1, 2, 3, 5, 8, 13**

Find the smallest subtask of them all. Assign to it a 1. Find the biggest one, that still looks manageable, assign that a 13. Then proceed to find a subtask that is double the size or complexity of one that has 1, assign it a 2.

Get the idea?

A feature you have implemented before has less risk than a task you have no idea of where to start. Let’s use 1 to 3 for risk, instead of the fibonacci sequence. The reason will seem clear later.

Assign risk values, from 1 to 3, using the same process as above. As an example, a subtask can have a size of 2 and risk value of 3. A task is riskier because it consists on doing something you haven’t done before. In contrast, a task with risk 1 is something that you have implemented in the past.

\* Refer to Planning Poker and Buckets under the Appendix section for a side note on estimates

Now that you have every subtask with two values — size and risk. Apply the following formula to each one:

![alt thingy](https://cdn-images-1.medium.com/max/800/1*TsAXjskHv-pjN8rLgfG6MA.jpeg)

Kidding! Just multiply the size by risk. Estimated complexity = size * risk. You finally end up with subtasks that have an estimate on how complex the task is. Add up the subtasks values to the parent tasks, but leave the subtasks with their given values. Add the total to their corresponding user story as well.

**Danger! Warning!** You might be tempted to create estimates based on time. Resist this temptation. If you create an estimate on time, it will be very hard to compare tasks. Also, it might tempt management to use the time you estimated, add it up, divide into days, and hold you to these as a deadline. Even worse, the manager or someone of power might be tempted to make you time your tasks per hour using a stopwatch (a desktop app). This will clutter your desktop and, if you are a software developer, you already have 15 apps open at a time.

**Note**: You might be tempted to create estimates based on time. Avoid this. This warning is listed twice on purpose.

## Prepare the Sprint

This step is meant to separate the user stories into sprints. A sprint is a fixed period of time where you lock the development team to complete the required features. You work on a project by participating on a series of sprints. While on the actual sprint, there are no big changes in features nor long meetings. There should be no extra tasks that might distract developers from completing their work.

Start with sprints that lasts from two weeks to a month. After planning it might seem like too much overhead to use it for just a week’s worth of work.

Add user stories that you feel comfortable achieving, from top to bottom of the backlog, to the sprint. Add tasks that make sense to achieve in the given timeframe. Don’t worry if you think you’ll complete less of these.

After making conservative choices on the user stories to include, add a couple of extra ones under the “Stretch”. These user stories were the next items in the backlog. They are optional to complete. If you were to finish all the user stories during a sprint you would have to finish early. The idea is to keep the sprint length consistent so that you can make future user stories more predictable.

Finally, add up the total estimated complexity of all the user stories added to the sprint. We’ll use this later, as we start the sprint.

Phew! That is a lot to digest. If you followed this, you have a set of features ready to work with. You have estimates on how complex or big these tasks are, everybody is part of the process.

Having done all this, you still need to do the actual work: sprint! Working on the sprint and getting insight after the sprint will be the topic of a next post.

---

## Appendix

#### On Team responsibilities and Project Managers

>The Scrum team makes its own decisions during the Sprint. The team is empowered. Every time a manager steps in and makes a decision for the team, they remove some responsibility from the team. If a manager keeps doing this, the team gradually — piece by piece — loses ownership, along with their commitment.
As a manager, the team must be given support, guidance, coaching and assistance. Not instructions. If necessary, the team should be helped to reach its own decisions. Facilitation becomes a key skill for agile managers.
From [All About Agile](http://www.allaboutagile.com/how-to-implement-scrum-in-10-easy-steps-step-6-sprint/). See Sources section below.

### Estimation Games and Exercises

If you have any doubts regarding estimates, don’t do it by yourself if you can. That’s why very clever people have invented Planning Poker and the Buckets approach. These are two techniques used to estimate. Won’t go into a lot of detail (you may Google the whole process) but want to give a good idea of what these are:

With Planning Poker, the product owner, stakeholders, and the developers each hold cards with the given Fibonacci sequence values. The dealer throws a task, written on a card, into the table. Everybody puts down, without showing, a card with their estimate on how big the task is. After everybody has put down their estimates, everybody turns their cards and sees if they are in agreement. If there’s very different values, the extremes discuss why they thing it is a bigger task or why it seems to be simple. After the discussion (a short one), players throw their cards again following the same process. When they reach agreement, they assign that estimate to the task.

The buckets is an abstraction on how to look at estimates. Instead of trying to visualize how each task relates to each other, you basically have a bucket labeled with each Fibonacci sequence entry or possible size (from 1 to 13, or more), and each feature/task in a card. You start putting the tasks/cards in its bucket, switching the cards between buckets when you realize that one task seems to actually be bigger in size than the next. So if you believe that the smallest task you have is a 1, put that one in the 1 bucket. Put the hardest in the 13 bucket, etc.

### Backlog with deliverables instead of tasks

I have read opinions stating that it is better to organize and break down the tasks if you look at them as deliverables. The point behind this is that its easier to understand what to estimate when you say state what you’ll deliver to complete the user story.

I have yet to do this myself, in order to explain it in detail. Agile patterns are varied and, between Scrum, XP, and other pure agile methodologies, it’s hard to decide what to implement or leave behind.

---

##### Wikipedia article: Agile Software Development
https://en.wikipedia.org/wiki/Agile_software_development

##### All About Agile
http://allaboutagile.com

##### Mountain Goat Software — Agile Summaries and FAQs
https://www.mountaingoatsoftware.com/agile/new-to-agile-or-scrum

##### The Art and Science of Ruby — Three things you need to know to produce an accurate estimate
http://theartandscienceofruby.com/2015/09/08/three-things-you-need-to-know-to-produce-an-accurate-estimate/

##### Wikipedia: The Project Management Triangle
https://en.wikipedia.org/wiki/Project_management_triangle
