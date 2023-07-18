---
title: "Week 04a - 07.18 Tue"
lecture_date: 2023-07-18
description: "Introduction to standup meetings; manual testing team01"
ready: true
layout: default
parent: lectures
slides: 
---

# jpa02 and jpa03 due Midnight tomorrow night

* 26 of 33 students have submitted on Canvas. (I would have hoped for 33/33)
* 13 of 33 students have submitted on Canvas. (I would have hoped for 33/33)

jpa03 requires a lot of separate steps, and they are steps you must be very familiar with for team02.
So you need to finish this asap.  Work on it today after standup if you are not finished with it.

We also need to finish team01 asap, by Friday at the latest.  

Every group of CS156 students says: 
* Make sure we are completely prepared for the legacy code projects with some PAs to learn Spring, React, mvn, npm, etc.
* Also: Start the legacy code projects earlier
* But also: lots of folks are slow to complete the earlier PAs.
  
We can't have it both ways.  Let's get through these easier assignments so we can get to the good stuff.

# {{page.title}}: {{page.description}}

* Go over some details about how to approach team01
  - Managing branches
  - Managing Pull Requests
  - Why you should *freeze* a branch once you do a PR from it
* How to manually test team01
* Deadline, and early/on-time/late submission of team01
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

# Manual testing of team01

To manually test team01, you can:

* Visit: <http://team01-f22.dokku-00.cs.ucsb.edu/swagger-ui/index.html> and try some queries
* Then visit the `/swagger-ui/index.html` link on your page, and compare both what the page looks like, and your results.

What to look for:
* Are the controllers present on your page (note that the link above may have more controllers than you are responsible for implementing)
* Is the documentation of the endpoints accurate in your controller, at least as accurate as what's on the example?
* When you put in queries, do you get the same results?

| Team | Repo | Kanban | Dokku |
|-----|-------|--------|-----|
| m23-9am-1 | [Repo](https://github.com/ucsb-cs156-m23/team01-m23-9am-1) | [Kanban](https://github.com/orgs/ucsb-cs156-m23/projects/1) | <http://team01.dokku-01.cs.ucsb.edu/swagger-ui/index.html> | 
| m23-9am-2 | [Repo](https://github.com/ucsb-cs156-m23/team01-m23-9am-2) | [Kanban](https://github.com/orgs/ucsb-cs156-m23/projects/7) | <http://team01.dokku-02.cs.ucsb.edu/swagger-ui/index.html>  |
| m23-9am-3 | [Repo](https://github.com/ucsb-cs156-m23/team01-m23-9am-3) | [Kanban](https://github.com/orgs/ucsb-cs156-m23/projects/6) |  <http://team01.dokku-03.cs.ucsb.edu/swagger-ui/index.html>  |
| m23-10am-1 | [Repo](https://github.com/ucsb-cs156-m23/team01-m23-10am-1) | [Kanban](https://github.com/orgs/ucsb-cs156-m23/projects/2) |  <http://team01.dokku-04.cs.ucsb.edu/swagger-ui/index.html>  |
| m23-10am-2 | [Repo](https://github.com/ucsb-cs156-m23/team01-m23-10am-2) | [Kanban](https://github.com/orgs/ucsb-cs156-m23/projects/3) |  <http://team01.dokku-05.cs.ucsb.edu/swagger-ui/index.html>  |
| m23-10am-3 | [Repo](https://github.com/ucsb-cs156-m23/team01-m23-10am-3) | [Kanban](https://github.com/orgs/ucsb-cs156-m23/projects/4) |  <http://team01.dokku-06.cs.ucsb.edu/swagger-ui/index.html>  |
| m23-10am-4 | [Repo](https://github.com/ucsb-cs156-m23/team01-m23-10am-4) | [Kanban](https://github.com/orgs/ucsb-cs156-m23/projects/5) |  <http://team01.dokku-07.cs.ucsb.edu/swagger-ui/index.html>  |

# Deploy your main branch every time you merge a PR

Note: if you have already merged a PR for a controller and that controller doesn't show up above, you need to deploy
your main branch to dokku again.

It should be as simple as this:

1. Merge PR
2. Login to your dokku machine
3. Type this (putting in your team name for `m23-xxx-xx`)
   ```
   dokku git:sync team01 https://github.com/ucsb-cs156-m23/team01-m23-xxx-x main
   dokku ps:rebuild
   ```

Once the output is finished, if it doesn't show errors, then the controller should appear on the dokku deployment above.

# Submission of team01, and deadlines

Team01 is now available for submission on Canvas.  

I've set a deadline of Friday 11:59pm for submission on Canvas, as well as some policies around early, on-time, and late submission.

* <https://ucsb.instructure.com/courses/10130/assignments/104121>

I will also be putting up autograders on Gradescope for team01; you will have one full week from when the autograders go online until the deadline for passing the autograder tests.  However, you should still work on the assignment and test it manually in the meantime. I'll go over how to test it manually today in class.

# Sidenote: jpa01 autograder

It appears that some folks got a perfect score on the mutation testing without actually writing any additional tests.

I think this is a bug in the autograder script; I'm going to look into it.

Your current grade on jpa01 will stand; everyone currently has 100, except for one student with a 93.08.

But, if I determine that the autograder was broken, I'll add another assignment and give you at least a week to do it.
(For the student with the 93.08; I'll change their grade to the resubmitted grade if it is higher than 93.08.)

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
* 50% do they have an "issue" in the in-progress column on the Kanban board?
  - or, alteratiavely, if they have no issue in the in progress column, is it because both the service and controller are "done", and all of the team level issues are "done"?

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

