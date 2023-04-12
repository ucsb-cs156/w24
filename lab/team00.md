---
description: Introducing React
assigned: 2022-09-27 17:00
due: 2022-10-05 19:59
layout: default
title: team00
ready: true
layout: default
parent: lab
course_org: https://github.com/ucsb-cs156-s23
course_org_name: ucsb-cs156-s23
starter_repo: https://github.com/ucsb-cs156-s23/STARTER-team00
starter_repo_ssh: 
course_software: https://ucsb-cs156.github.io/s23/info/software.html
canvas_url: https://ucsb.instructure.com/courses/7876/assignments/93523
---

# {{page.title}} - {{page.description}}

# NOT READY YET
# STILL WORKING ON THIS
# NOT READY YET
# NOT READY YET
# DON'T START THIS YET
# NOT READY YET
# NOT READY YET
# CHECK BACK LATER
# NOT READY YET
# NOT READY YET
# STILL WORKING ON THIS
# NOT READY YET
# NOT READY YET
# DON'T START THIS YET
# NOT READY YET
# NOT READY YET
# CHECK BACK LATER
# NOT READY YET

## First team programming assignment: Introduction to React

This is a team programming assignment.  Each team has it's own repo to complete this assignment, and you will work as a team.

In this assignment, you'll be given the starter code for this web app, which you should go explore a bit right now:

* <https://ucsb-cs156-s23.github.io/demo-react-example/>

You'll see that there is a home page, and a menu with links to three pages, one for each of three towns:

* Arroyo Grande
* Avila Beach
* Los Alamos

Your job as a team is to add six more towns to this menu, linking to six new pages.  We'll walk you through it step by step.

Here are links to the repos:

| 5pm | 6pm | 7pm |
|-----|-----|-----|
| [{{page.title}}-{{site.qxx}}-5pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-1) | [{{page.title}}-{{site.qxx}}-6pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-1) | [{{page.title}}-{{site.qxx}}-7pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-1)  |
| [{{page.title}}-{{site.qxx}}-5pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-2) | [{{page.title}}-{{site.qxx}}-6pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-2) | [{{page.title}}-{{site.qxx}}-7pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-2)  |
| [{{page.title}}-{{site.qxx}}-5pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-3) | [{{page.title}}-{{site.qxx}}-6pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-3) | [{{page.title}}-{{site.qxx}}-7pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-3)  |
| [{{page.title}}-{{site.qxx}}-5pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-4) | [{{page.title}}-{{site.qxx}}-6pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-4) | [{{page.title}}-{{site.qxx}}-7pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-4)  |
{:.table .table-sm .table-striped .table-bordered}


## Submission/Grading

* Grading for this assignment is manual; someone on your team will submit the url to the [Canvas link for team00]({{page.canvas_url}}) when the team thinks the site is ready for grading.


## Step 0: Understand the assignment

The first step is that everyone on the team should read through this entire assignment's web page.

No, really.  Read it all the way through.  Right now.

You need the big picture before you start getting down into the weeds.

### What you'll be doing

In this assignment, you'll work as a team to:

* Pull the starter code into your team's team00 repo.
* Deploy the starter code to GitHub Pages.
* Divide up a list of tasks that need to be done to modify the app.
* Carry out those tasks as a group.

This will require some coordination among the six of you.


## Step 1: Choose the towns, and divide up some tasks

Each of you should choose a town (other than the three listed.)  It doesn't have to be your hometown; it can be
anywhere, and it doesn't have to be in California.

Choose your town, and record your choice on the Slack.

## Step 2: Set up the repo for the team

Next, choose one person that will carry out the following task while sharing their screen; the rest of you should follow along.  If you are on zoom, go into a breakout room for your team, and follow along there.

* Clone your teams team00-teamName repo.
* Add a remote for the starter code:
  
  <tt>git remote add starter {{page.starter_repo_url}}</tt>

* Pull in the starter code and push it to the main branch
  ```
  git pull starter main
  git push origin main
  ```

* Now make a one line change in the file: `frontend/src/App.js`:

  On this line:

  ```
  <BrowserRouter basename="/demo-react-example">
  ```

  change `STARTER-team00` to `team00-s23-5pm-1` or whatever your team's name is

  Commit this change to the main branch, and push.

  You should see that this kicks off a GitHub Action (look at the Actions tab in your repo) that publishes the
  site to the gh-pages branch.

  Once that finishes, you'll need to enable GitHub Pages, which is the next step

* Enable GitHub Pages for your repo by going to the Settings tab, finding Pages, and making it look like this:
  