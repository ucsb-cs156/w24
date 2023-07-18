---
title: "Week 04a - 07.18 Tue"
lecture_date: 2023-07-18
description: "Introduction to standup meetings; manual testing team01"
ready: true
layout: default
parent: lectures
slides: 
---

# {{page.title}}: {{page.description}}

* Go over some details about how to approach team01
  - Managing branches
  - Managing Pull Requests
  - Why you should *freeze* a branch once you do a PR from it
* Discuss what a "standup meeting is" 
* Hold our first "standup meeting"

We'll then continue work on team01.

* <https://ucsb-cs156.github.io/m23/lab/team01/>

# Some Details about team01

* We started out assigning individuals to each of four or five APIs (Service/Controller) as a way to getting organized.
* HOWEVER, once your work on that service/controller is finished, *you should pivot to helping the other members of your team* (don't just "leave" or "skip class").
* Specifically, please help with code reviews, pair programming with folks that may need help or support, etc.

# Once you make a PR,  THEN LEAVE THAT BRANCH ALONE.   

Don't continue working on a branch if there's an open pull request for it--unless you are fixing things that are pointed out in a code review.

Instead, make a new branch off of the old branch.

For example, if you have a PR from the `Chris-Form` branch that adds the form you need for the `Chris-CreatePage` branch, do this:


```
git checkout Chris-ZipCodeService
git pull origin Chris-ZipCodeService
git checkout -b Chris-ZipCodeController
```

# What happens if you continue making changes to your branch after you do a PR?

Remember that: 
* A branch is a pointer to a commit
* A PR is a request to pull from one branch into another
* Every time you make a commit to a branch, you update where that branch points
* Meaning: if you continue to make commits to a branch that is the basis of an open PR, that *PR will continue to change*
* That's not good!  You want a PR to be a fixed target.
  - You change the branch that a PR is pointing to if and only if the code review process suggests you need changes
  - Then, branches that branched off of that will need to be *rebased*
  - Rebasing means: clipping off all of the later commits that came after the *old* base, and reapplying them *on top of* the new base.


# What is a Standup meeting?

In a standup meeting, each team member should briefly share, *both* by posting in the slack channel, *and* by saying it out loud for the group assembled and the zoom room, these three things: 

1. What have you done **since the last time** the team met? 
2. What are you **doing now**? 
   - What issue are you currently assigned to in the "in Progress" column on the Kanban board (hopefully its only one)?
   - How is it going?
3. Are you **blocked** on anything?

A fourth question is sometimes added: 

* When do you think you will be **finished** and ready to take on a new issue?

The main purposes of a standup are to:
* Identify blockers so they can be eliminated
* Ensure that each member of the team can make progress between now and the next standup

# Standup DOs and DON'Ts

DO:

* Keep it short (physically standing isn't required, but it can help)
* Give other team members your full attention
* Offer help with blockers (but summary, and promises to follow up, NOT detailed explanations)
* Keep it positive

DON'T:
* Go into *detailed* explanations; instead make a note to follow up with those *after* standup is over
* Be late or skip standup.
* Bring up extraneious issues unless they are blockers (blocking immediate progress)

# Standup are not the only meetings!

A standup should not be the only kind of team meeetings that you have.   

* Your team may need to have other kinds of discussions!
* If the thing you want to discuss doesn't fit into the "formula", suggest to the team that you have a different kind of discussion before or after standup.
* Try to keep standup focused, short, and structured.

# Further notes on a standup meetings

* [https://ucsb-cs156.giFrib.io/topics/agile_standups.html](https://ucsb-cs156.giFrib.io/topics/agile/agile_standups.html)

# Now do your standup, then review your Kanban board as a team

* Each team member, please take a moment to answer the three questions on your Slack channel
  - This is not always done; on real world agile teams
  - We are doing it here to help you get used to the process
  - It also allows the staff to check that everyone is participating (since this is a university course, not a company).  
* Then, go around and have each team member make an oral report to the team 
  - This is the part that's more authentic to real world practice
  - That's why I want you to really, really do it.
  - Ask for a volunteer to go first.
  - Then each person gives their report, and then identifies who goes next.
  - While sharing, each person should ideally unmute (if they are on zoom, or any team member is on zoom) and turn on their camera while sharing.
  - When done, signify who should go next.

# Review your Kanban board as a team

Then, review your kanban board as a team.   

This is not always done during Standup meetings, but it's a good practice.

* Make sure each team member has something in the in-progress column on the kanban board. (Unless they are done with both of their issues, and there are no team level issues left to take care of--in that case, they should help with code reviews.)
* Take care of any code review requests, and merge code that's ready to merge.
* Do not merge code that doesn't pass the CI/ checks; only merge branches that are "green on CI".


# Work on team01

Then, you'll just work as a team or in pairs, individually or in mobs as needed, while getting help from the staff.

# Mobs? Yes, it's a thing

See: <https://en.wikipedia.org/wiki/Mob_programming>

This isn't programming by organized crime figures, but rather the idea of pair programming extended to more than two people; as many as can gather around a shared screen (either a large monitor, or a shared zoom session).

It's been found to be very effective.
* You might think that the overall team productivity would be reduced vs. individuals or pairs splitting up the stories
* Instead, the quality of the code goes up, and far less time is spent fixing bugs, or reworking features because they didn't meet the customer needs.

So you are encouraged to try it if the team (or some part of it) is interested.

# Today's participation activity

We may or may not assign a grade for today's participation, but if we do, this will be the basis:

* 50% did the student make a standup post in the slack channel?
* 50% do they have a story in the in-progress column on the Kanban board?

In general, I'd like to get to the point where it's no longer necessary or helpful to track participation with these 
required participation assignments:
* I do it at first to try to help establish expectations, by tying it to your grade
* My hope is that you eventually start showing up for your team our of a sense of wanting to care for your teammates.
* Team participation will still be part of your grade via Peer Evaluation scores through CATME; just less directly than a daily participation grade.

# Staff members:

Please check the Kanban boards for the three teams to which you are assigned.  Check that:

* Each team member has exactly one issue assigned to them in the In Progress column (not less than one, not more than one)
* If there are issues "In Review", check that there is a Pull Request
* If there are issues that are "Done", if applicable, be sure that a PR has been merged

