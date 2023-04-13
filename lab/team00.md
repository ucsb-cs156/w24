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
sample_deployed_app: https://ucsb-cs156-s23.github.io/STARTER-team00
---

# {{page.title}} - {{page.description}}

This is a work in progress, but you can get started on it.

Refresh often for updates.

## First team programming assignment: Introduction to React

This is a team programming assignment.  Each team has it's own repo to complete this assignment, and you will work as a team.

In this assignment, you'll be given the starter code for this web app, which you should go explore a bit right now:

* <{{page.sample_deployed_app}}>

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

* One more one line change in `frontend/package.json`

  Change this:
  
  ```
  "homepage": "https://ucsb-cs156-s23.github.io/STARTER-team00/",
  ```
  
  to this (substituting in your team name, not the one shown):
  
  ```
  "homepage": "https://ucsb-cs156-s23.github.io/team00-s23-7pm-3/",
  ```

  You should see that commiting and pushing these changes 
  kicks off a GitHub Action (look at the Actions tab in your repo) that publishes the
  site to the gh-pages branch.

  Once that finishes, you'll need to enable GitHub Pages, which is the next step


## Step 3: Set up Github pages

Enable GitHub Pages for your repo by going to the Settings tab, finding Pages, and making it look like this:
  
<img width="545" alt="image" src="https://user-images.githubusercontent.com/1119017/231609350-e5947a84-1ff2-497b-bc89-dce00cfdb757.png">

Then, on your team00 Github repo page, find the place at right that looks like this:

<img width="412" alt="image" src="https://user-images.githubusercontent.com/1119017/231609798-88b24ed6-86d1-4720-8350-a23c540da265.png">

Click the little gear.

You should then see a page like this.  Click the box that says "Use your GitHub Page Website" and then click Save Changes

<img width="785" alt="image" src="https://user-images.githubusercontent.com/1119017/231609863-47b28701-e626-4917-a2b2-c919e43fa559.png">

Then you should see something like this:

<img width="402" alt="image" src="https://user-images.githubusercontent.com/1119017/231610003-c555c722-ca1e-4bc3-a7a0-fc3c30c56207.png">

If you click the link, it should take you to the deployed web app, similar to the one here:
* <{{page.sample_deployed_app}}>

## Step 4: Each member clone and run


Now, each member of the team should clone the team's repo to your own machine (this won't work on CSIL).

Use `git clone repo-url`, then cd into the repo and open it up in your editor (we suggest VSCode).

Now, if you haven't yet installed node on your machine, follow the instructions here to do so:

* <https://ucsb-cs156.github.io/s23/info/software.html>

Then, `cd frontend` to move into the subdirectory with the React application.

Then type: `npm install`

This should install all of the dependencies of your application.

Then type: `npm start`

This should bring up the application at the url <http://localhost:3000> so that you can test it locally before deploying.

If this doesn't work, ask your teammates for help; if it still doesn't work, ask the staff.

## Step 5: Create a new branch

Now, you are ready to start coding to add your page.

First come up with a branch name, using this convention: `Firstname-City`, for example:
* If your name is Chris, and you are adding a page for `SanDiego`, call your branch `Chris-SanDiego`
* If your name is Taylor, and you are adding a page for `Chico`, call your branch `Taylor-Chico`

To create your branch, cd into your cloned repo, and use this command:

```
git checkout main
git pull origin main
git checkout -b Chris-SanDiego`
```

This creates a new branch `Chris-SanDiego` that is branched off a fresh copy of the main branch.

You'll do all of your work in this branch, and when you are done, you'll do a *Pull Request* to get your code into the `main` branch.  

* *Note that using this workflow is a required part of the assignment*.   
* We are practicing a workflow (the GitHub feature-branch/pull-request workflow) that will become super important later in the course, and even more important when you work on real world projects.

## Step 6: Implement the Page you were assigned

TODO: Add instructions here about how to add the new page;

As you work on your page, make commits whenever something is working.
* Use your initials at the start of your commit message (e.g. `cg` for "Chris Gaucho")
* Separate your initials from your message with a hyphen
* Your message should describe what you did

Examples:

* `git commit -m "cg - added page for San Diego"`
* `git commit -m "cg - added menu item for San Diego page"`

Having meaningful commit messages is a component of your grade for this assignment, so please do put some thought into what you write.

As you make commits, push them to your branch, for example:

```
git push origin Chris-SanDiego
```

A few handy commands:
* `git status` shows what branch you are on, among other things
* `git branch -a` shows all current branches
* `git fetch` updates information about branches by pulling new branch names from GitHub

TODO: Continue from here.
