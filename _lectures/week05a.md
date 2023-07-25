---
title: "Week 05a - 07.25 Tue"
lecture_date: 2023-07-25
description: "Retrospective, H01 assigned, work on team02"
ready: true
layout: default
parent: lectures
slides: 
---

# Announcements

## New participation assignment P10

There is a new participation assignment [P10](https://ucsb.instructure.com/courses/10130/assignments/148214) which is your first CATME survey.
- This is the first of several peer evaluations (one per sprint)
- A Sprint is a period of work; a sprint ends and a new one starts when you do an Agile Retrospective, which we will do today.
- The first one is for information only; but after this week, they may affect your grades for assignments you complete
- As long as your peer evals are close to the mean for the group, everything is ok.
- But if they are way below, it indicates that not all is well within the group, i.e. there is at least a perception that you may not
  be contributing in a way the group is happy with.
- That's something important to discuss and address sooner rather than later.
- We'll see the CATME results and discuss in section on Friday.
- Comments and rating are anonymized, but the content and rating is shared with the individual that you rated (after the deadline.)

## New homework assignment H01

There is a new homework assignment, [H01](https://ucsb-cs156.github.io/m23/hwk/h01/)
* This will provide a brief introduction to JavaScript before we start team03, coming soon, where we start to work with the frontend
* The due date is on Gradescope; you have a week, but *it will be better if you get this done sooner rather than later* so that you are prepared
  for team03.
* So, please start on H01 as/when you are finishing up team02, or you are blocked, e.g.

  * waiting for office hours because you stuck on something
  * done with your PRs, and there's nothing currently to code review

  Or, if you just need a break from team02 work and want to do something else for a while

The point is, you'll find team03 much easier if you've had a chance to complete H01 first.

# Ten minute standup 2:01pm-2:11pm

* Do a written update on the slack channel
* Do an out loud standup
* Signal on #help-lecture-discussion that your team is done (by team number, not table number)
  - If all teams finish before 2:11pm, we'll continue earlier.

# Database tips: 2:11pm- 2:15pm

* How to reset the db on localhost: `mvn clean`
* [How to reset the db on dokku](https://ucsb-cs156.github.io/topics/dokku/postgres_database.html#resetting-the-database) 
* When should I do this?
  - If you are getting strange `SQL` errors in your backend console output
  - Especially if you get these after making a change to an `@Entity` class.

In real world applications, this is done with something called *database migration frameworks*.

That's a topic we've tried to introduce into this course a few times (unsuccessfully so far).

If someone would like to take on a CMPSC 192 or CMPSC 196 independent study on this topic in Fall, let me know.

# Agile Retrospective Intro (2:20-2:40)

# Today (outline)

The most important aspect of Agile: The Retrospective

We "inspect and adapt".

* Pause all work/submission for team02/team03.
* Focus only on the retro, and do not rush through it.
* A retro that lasts less than 30 minutes raises questions about whether it is a good faith effort.
* Give it the time that it needs.

# Where did Agile come from?

* The old Waterfall method didn't work well: <https://www.tutorialspoint.com/sdlc/sdlc_waterfall_model.htm>
* During the 90s, folks inspected and adapted, leading to the [Agile Manifesto](https://agilemanifesto.org/)

# Retrospective: the heart of Agile

The core principle of Agile is "inspect and adapt".  
* It was "inspecting and adapting" that led the original authors of the [Agile Manifesto](https://agilemanifesto.org/) to their ideas.
* It has been by "inspecting and adapting" that the Agile philosophy continues to grow and develop.

Inspect and Adapt is, in many ways, linked to the *Scientific Method*; 
* we observe
* we form a hypothesis
* we do an experiment

All in the service of doing a better job of software development.

In a retro, the team stops, pauses, reflects, and most importantly *comes up with an actionable change* for their practice.

# Today's Retro (2:40 - 3:15)

* Start by having everyone take 5 minutes to read through this article: [https://ucsb-cs156.github.io/topics/agile/agile_retros.html](https://ucsb-cs156.github.io/topics/agile/agile_retros.html)
  - Really read it!  It has the instructions for the most important activity in today's class
 
* Then take 5 minutes to read your fellow team members feedback (login to <https://catme.org>)
 
* Next, choose a leader for your retro. It should be someone that has read the instructions and is comfortable leading the group. 
* Then, locate the Google Drive folder for your team.  It should be linked in your Slack channel with a `gdrive` link this:

<img width="260" alt="image" src="https://user-images.githubusercontent.com/1119017/166498621-8fc7d61a-4d76-404d-9514-ea4672667ad9.png">

Check that each member of the team is able to access the folder.

In that folder, create a folder called `Retros` and in that folder, create a document `Retro1`

Then follow the instructions in the [https://ucsb-cs156.github.io/topics/agile/agile_retros.html](https://ucsb-cs156.github.io/topics/agile/agile_retros.html) article for  Stop/Start/Continue retro.

In the document, write down who your retro leader is.

At the end of the process, you should have in your document:
* Name of person leading the retro at the top, and a list of who participated
* A document with three parts, "stop/start/continue", and items from each member under the three categories
* Dot voting (three votes per team member participating) on the items in the document.
* A summary at the bottom on an "experiment" in the form "If we change X we hope to see Y result"
  - This should be related to one of the top three items by votes that your group agreed on.
* A brief explanation of how you will know whether your experiment was or was not a success.

# After the retro is done

* Ask a staff member to look over your GDrive document; they'll check it to make sure it has the required elements:
  - items from each member under start/stop/continue
  - dot voting
  - an experiment, including the criteria by which you can know whether the experiment was a success

# Next steps if there's more time

* Continue work on team02
* Start homework assignment [H01](https://ucsb-cs156.github.io/m23/hwk/h01/) (Intro to JavaScript).
  

### Staff use only

The information in the dropdown is for staff use only; you are welcome to look at it, but it's just
the details of what preparation needs to happen for today's lecture. Not all that interesting, unless you
want a peek behind the scenes.

<details markdown="1">
<summary>
Preparation for first retro  
</summary>

* Create folder such as `cs156-m23-teams` inside staff Google Drive folder
* Create one folder per team inside that folder named `m23-9am-1`, `m23-9am-2`, etc.
* Create `Retro1` document inside each of those folders
* Paste content inside each and change the heading as appropriate:
  ```
  # Retro 1—m23-9am-2—07/25/2023

  Team members:
  * replace with team member 1's name
  * replace with team member 2's name
  * replace with team member 3's name
  * replace with team member 4's name
  * replace with team member 5's name, or delete
  * replace with team member 6's name, or delete
  ```
* Pull up roster of teams that has UCSB emails
* For each team folder:
  - Share the team's folder with the members of that team (i.e. paste in the emails to Share)
  - Copy link to folder and paste on Slack channel with the label `GDrive`
* For each team slack channel, send this message:
  ```
  @channel One small thing to do before class today if possible (< 5 minutes)
  Please see the link labelled GDrive at the top of this channel.
  Please verify that when logged in with your UCSB Google account, that you can open this folder.
  You should see a document inside called "Retro1".
  Inside that document is a list where should enter your name.
  This will serve as a check that everyone has write access to this document before class today.
  If you have trouble, please post a note on the channel, and mention @phtcon
  ```
* Before class, double check that there are no issues with accessing the folders  
</details>
