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
starter_repo_ssh: git@github.com:ucsb-cs156-s23/STARTER-team00.git
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

To add a new page, we first add a file for the new page.  You can look at these files as examples:

* [frontend/src/main/pages/ArroyoGrandePage.js](https://github.com/ucsb-cs156-s23/STARTER-team00/blob/main/frontend/src/main/pages/ArroyoGrandePage.js)
* [frontend/src/main/pages/AvilaBeachPage.js](https://github.com/ucsb-cs156-s23/STARTER-team00/blob/main/frontend/src/main/pages/AvilaBeachPage.js)
* [frontend/src/main/pages/LosAlamosPage.js](https://github.com/ucsb-cs156-s23/STARTER-team00/blob/main/frontend/src/main/pages/LosAlamosPage.js)

Create a similar file in the same directory.

The information you'll need to change it this:

* The name: `export default function AvilaBeachPage() {`
  - Change it to, for example, `GoletaPage` instead of `AvilaBeachPage`
* The `<h1>` (headline) content.
* The `<p>` (paragraph) content describing the town.  This doesn't have to be long; a couple of sentences is fine.
* The `<p>` (paragraph) element showing who added the page.  You can just use your first name and last initial here.

Make this change, and then make sure the application still loads by doing `npm start`.  You won't be able to see your content yet--that happens in the next step after we add a route to your new page).   However, you should still run `npm start` to make sure you didn't break anything; if there is a syntax error, you'll find out
when you run `npm start`.

If all goes well, make a commit for adding this file.  That might look like this (but with your initials instead of xy).  Also note that you are pushing to your branch, not `main`:

```
git add frontend/src/main/pages/GoletaPage.js
git status
git commit -m "xy - add page for Goleta"
git push origin Phill-Goleta
```

### Make Good Commit Messages

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

## Step 7: Add a route to the page you were assigned

Now, open up the file `frontend/src/App.js`.  In this file, we define the mapping from web urls to the pages
that are served.

Find these lines at the top of the file:

```js
import AvilaBeachPage from "main/pages/AvilaBeachPage";
import LosAlamosPage from "main/pages/LosAlamosPage";
import ArroyoGrandePage from "main/pages/ArroyoGrandePage";
```

You should be able to guess what line needs to be added for your page; add that line.

Then, look for these lines of code:

```js
        <Route exact path="/towns/AvilaBeach" element={<AvilaBeachPage />} />
        <Route exact path="/towns/LosAlamos" element={<LosAlamosPage />} />
        <Route exact path="/towns/ArroyoGrande" element={<ArroyoGrandePage />} />
```

Again, you should be able to guess what line needs to be added for your page; add that line.

At this point, if you do `npm start` and open up the app, your page won't appear on the menu, 
but if you manually put in the url for your town, it should show up!

Give it a try, and if it works, do another commit; something like this:

```
git add frontend/src/App.js
git commit -m "cg - added route in App.js for San Diego"
git push origin Chris-SanDiego
```

## Step 8: Add your page to the menu

Now, open up the file `frontend/src/main/components/Nav/AppNavbar.js` and look for this code:

```js
                <NavDropdown.Item as={Link} to="/towns/ArroyoGrande">Arroyo Grande</NavDropdown.Item>
                <NavDropdown.Item as={Link} to="/towns/AvilaBeach">Avila Beach</NavDropdown.Item>
                <NavDropdown.Item as={Link} to="/towns/LosAlamos">Los Alamos</NavDropdown.Item>
```

Again, you can probably figure out from the example what code needs to be added.

So add in the appropriate line of code, and then test using `npm start`.

If it works, you should be able to go to the menu, and select the web page for your town!

If so, then you are done with your branch, and it's time to do a pull request to merge this branch into the `main` branch.  We'll explain how to do that in the next step!

Note that learning the pull request process is *part of the lab*; don't take any shortcuts here!


## Step 9: Do a pull request

The next step is to go to the webpage for your repo on GitHub, and find the "Pull Requests" tab.  It should look like this:

<img width="1297" alt="image" src="https://user-images.githubusercontent.com/1119017/231614969-d48d910a-6a36-491a-93e8-007739ec7210.png">

Click the "New Pull Request" button.   You should then see something like this:

<img width="402" alt="image" src="https://user-images.githubusercontent.com/1119017/231614921-9ce0bb1a-5e17-44e0-a8eb-b329d6efe974.png">


Change it so that the base is `main` and the branch you are comparing to is your branch, like this, and then click the "Create Pull Request" button.

<img width="1297" alt="image" src="https://user-images.githubusercontent.com/1119017/231615304-19380a77-d198-46c2-b3a1-054993b6d52d.png">

You'll then see something like this.  

<img width="902" alt="image" src="https://user-images.githubusercontent.com/1119017/231615432-ed5e95d8-8860-43b3-8c47-c59aa040c959.png">

Your next step should be to change the title (which will be populated with some suggested text from one of your recent commit messages).  Change it to: "Add Los Angeles" (or whatever your town was).

Then, in the big area, using complete sentences, type something like this what you see in the image below:

<img width="897" alt="image" src="https://user-images.githubusercontent.com/1119017/231615702-f3cb8436-209e-405f-a463-f4bbc3d7dd38.png">

Then click "Create Pull Request".

## Step 10: Merging the Pull Requests

At this step, you should coordinate with one another again.

The aim here is for each of you to merge *someone else's pull request* (not your own).

Note that because each of you were making changes in `App.js` and in `AppNavbar.js`, there is a potential for
*merge conflicts*. Fortunately, these will be easy to resolve!  But the process for resolving them can be a little tricky,
so we'll go over it in lecture.

As each pull request is merged into the main branch, you should see the page populate on the
running app on Github Pages.

When all six are merged into the main branch and appearing in the app, your team is done with this assignment.

## Step 11: Submission/Grading

* Grading for this assignment is manual; someone on your team will submit the url to the [Canvas link for team00]({{page.canvas_url}}) when the team thinks the site is ready for grading.

# End of assignment


