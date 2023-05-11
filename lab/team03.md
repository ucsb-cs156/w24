---
description: Spring Boot OAuth and CRUD operations
assigned: 2023-05-11 15:00
due: 2023-05-22 23:59
layout: default
title: team03
ready: true
layout: default
parent: lab
course_org: https://github.com/ucsb-cs156-s23
course_org_name: ucsb-cs156-s23
starter_repo: https://github.com/ucsb-cs156-s23/STARTER-team03
starter_repo_ssh: git@github.com:ucsb-cs156-s23/STARTER-team03.git
course_software: https://ucsb-cs156.github.io/s23/info/software.html
canvas_url: https://ucsb.instructure.com/courses/7876/assignments/103963
sample_deployed_app: https://ucsb-cs156-s23.github.io/STARTER-team03
---

# {{page.title}} - {{page.description}}


## Team Programming Assignment: Spring Boot CRUD backend

This is a team programming assignment.  Each team has it's own repo to complete this assignment, and you will work as a team.

Here are links to the repos:

| 5pm | 6pm | 7pm |
|-----|-----|-----|
| [{{page.title}}-{{site.qxx}}-5pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-1) | [{{page.title}}-{{site.qxx}}-6pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-1) | [{{page.title}}-{{site.qxx}}-7pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-1)  |
| [{{page.title}}-{{site.qxx}}-5pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-2) | [{{page.title}}-{{site.qxx}}-6pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-2) | [{{page.title}}-{{site.qxx}}-7pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-2)  |
| [{{page.title}}-{{site.qxx}}-5pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-3) | [{{page.title}}-{{site.qxx}}-6pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-3) | [{{page.title}}-{{site.qxx}}-7pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-3)  |
| [{{page.title}}-{{site.qxx}}-5pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-4) | [{{page.title}}-{{site.qxx}}-6pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-4) | [{{page.title}}-{{site.qxx}}-7pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-4)  |
{:.table .table-sm .table-striped .table-bordered}

## Set up already done

We are omitting instructions for some of the setup steps that were already done:

* Creating a kanban board
* Setting up the repos with the starter code

## Initial Kanban board population

You will see under the `/issues` directory that there are these files:

These are the issues you need to create and put on your Kanban board.

You should edit the issues that have `2nd model` and `3rd model` in the title to 
replace those titles with the actual titles of the 2nd and 3rd models
that your team chose (in addition to `Restaurant`) for team03.

Once the issues are edited and committed (you can do this on the main branch):
* Commit the files and then run workflow `90-create-issues`.
* That will create as issues in your repo
* Then you can put them on the Kanban board.

BE SURE TO COORDINATE WITH THE TEAM so that only one person submits the `90-create-issues` job.
* The job is supposed to check for duplicate issues, and not add the issue if it is a duplicate.
* However, that doesn't seem to be working
* So it's important to only run the job once; otherwise, you'll have to clean up the mess of duplicate issues by closing the duplicates.

## Working on the issues

Most of the issues have hints inside the issue text themselves, but there is some additional material below that may help.

## Big Picture: what is team03 all about?

From a high-level standpoint, you'll be doing the following:

* Copying your backend of CRUD operations for three database models from team02
* Copying your frontend of CRUD operations for three database models from team01
* Connecting the frontend and the backend with new code, based on the code you find
  in this starter code for UCSBDates.

If you need additional guidance, ask on the `#help-team03` channel, and we'll try to steer you in the right direction.


## Submission/Grading

* Grading for this assignment is manual; someone on your team will submit the url to the [Canvas link for {{page.title}}]({{page.canvas_url}}) when the team thinks the site is ready for grading.