---
desc: "Deploying a Spring Boot/React/OAuth/Postgres app on Dokku"
description: "Deploying a Spring Boot/React/OAuth/Postgres app on Dokku"
assigned: 2023-05-02 14:00
due: 2023-05-09 23:59
github_org: ucsb-cs156-s23
num: jpa03
title: jpa03
ready: true
starter: https://github.com/ucsb-cs156-s23/STARTER-jpa03
layout: default
parent: lab
teams_url: https://ucsb-cs156.github.io/s23/info/teams/
example_running_app: 
office_hours_page: https://ucsb-cs156.github.io/s23/office-hours
software_install_url: https://ucsb-cs156.github.io/s23/info/software.html
---

# NOT READY YET

# NOT READY YET

# NOT READY YET

# NOT READY YET

# NOT READY YET

# NOT READY YET

# NOT READY YET

# Instructions for jpa03

If you run into problems, let us know on the `#jpa03-help` channel on the slack.

{% include drop_down_style.html %}

This is an **individual** lab on the topic of deploying
Java web apps that use OAuth and Databases, using Dokku.

You may cooperate with one or more pair partners from your team to help in debugging and understanding the lab, but each person should complete the lab separately for themselves.

# Goal

By the end of this lab, you'll have deployed your own copy of the starter code repo (<{{page.starter}}>) on both localhost
and Dokku.  

This app is a full-stack web app with:

* A front-end built in React (under the directory `./frontend`)
* A back-end built in Spring Boot (the code for this is under the directory `./src`, plus the `pom.xml` at the top level
* OAuth integration; this allows the app to have a "login/logout" feature based on Google Accounts (e.g. your UCSB Google Account)
* A SQL database, which runs using H2 (an in-memory database) on localhost, and using Postgres when running on Dokku.
* Automatic generation of javadoc and storybook web pages for both
  the production code (`main` branch) and all branches that have 
  open pull requests targetting the `main` branch.

This app is not intended as a coherent app to solve a real-world problem,
but as a code base that demonstrates many of the techniques you 
would need in such an app.   The legacy code apps that we'll work
with in this course have a similar structure.

# Preliminaries

You'll need an environment where you can test this lab out on localhost before deploying.

* The best choice is your own laptop if you have one available
* The best known alternative is using Github Codespaces
* CSIL is not a good choice; you'll probably exceed your disk or file quota if you try.

For working on your own machine, you'll need the following:

* Java 17
* Maven
* git
* Heroku CLI
* Node 14
* npm 8.3

See guides for installing these on your machine at this link:
* <{{page.software_install_url}}>


# Step 1: Understanding what we are trying to do

## What are we trying to accomplish in this lab?

This lab, similar to `jpa02` has little to no programming.  The point of the lab is to walk you through the steps you need to 
take to deploy full-stack Spring Boot/React apps on Dokku, configuring them for Google OAuth (for logins) and a Postgres database.

Unlike the simple "backend only" `Hello World` type app 
from jpa02, in this assignment, the app is a full-stack 
app with:

There are quite a few configuration steps that are needed,
and we want to get you used to those before we start
introducing the coding challenges as well.

# Step 2: Create your repo

You should already have a repo under the course organization 
<tt>{{page.github_org}}</tt> called 
<tt>{{page.num}}-<i>githubid</i></tt>
created for you by the staff, where <tt><i>github</i></tt> 
is your github id.

If not, create one for yourself following that naming convention;
it should initially be public, and empty (no `README`, license or
`.gitignore`.)

Clone that repo somewhere and cd into it.

Then add this remote:

<tt>git remote add starter {{page.starter}}</tt>

That sets up `starter` as a remote with the code from this github repo: <{{page.starter}}>

Then do:

```
git checkout -b main
git pull starter main
git push origin main
```

# Step 3: Configure your app for localhost as documented in the README.md

The next step is to read through the [README.md]({{page.starter}}/blob/main/README.md) and configure your app as indicated there.

This includes configuration for Google OAuth, and GitHub pages.

The configuration step includes copying the `.env.SAMPLE` file to `.env`.

The `.env` file  should *not* be committed to GitHub. 

The instruction to configure this app for OAuth are linked to from
the `README.md` in the starter repo itself, so will not repeat
them here.  Follow those instructions (which may, in turn, refer
you to instruction inside the `docs` folder of the repo.)

## The `.env` file  should *not* be committed to GitHub

I already made this point, but I really, really want to emphasize it.

One of the values in the `.env` file is called a client *secret* for a reason.  

If it leaks, it can be used for nefarious purposes to compromise the security of your account; so don't let it leak!

Never, ever, commit those to GitHub, and try to only share them in DMs on Slack (not in public channels).

Security starts with making smart choices about how to handle credentials and tokens. The stakes get higher when you start being trusted with credentials and tokens at an employer, so learning how to handle these with care now is a part of developing good developer habits.

The staff reserve the right to deduct points if we find that you have committed your `.env` file to GitHub.

## About OAuth

OAuth is a protocol that allows you to delegate the login/logout
functionality (user authentication) to a third party such as
Google, Facebook, GitHub, Twitter, etc.  If you've ever used
a website that allows you to "Login with Google" or "Login With Facebook", then chances are good that app was built using OAuth.

Indeed, you've already encountered an examples of GitHub OAuth earlier in the course when you used your GitHub account to log into the <https://ucsb-cs-github-linker.herokuapp.com>

## Follow the instructions in the README

The instructions in the README include instructions
for deploying to both localhost, and to Dokku.  

Follow those instructions, consulting the material below and the
material in jpa02 as needed, until you have the application
working on both localhost and Dokku.

You'll be following this sequence of instructions many
times during this course, so this assignment is here to help you get used to that process.

## Also set up GitHub Pages

In the file `docs/github-pages.md` there are instructions for setting up GitHub Pages to publish the documentation for this repo.  Follow these instructions.

## Green check ✅, not red X ❌

GitHub Actions should be running on the main branch with
a green check, not a red X.  If there are problems there,
address those as best you can before submitting.

## Reminder about running your web app on `localhost`

To get this demo app running on `localhost`, we need to do the following:

* Do the OAuth Configuration steps linked to from the README to get a `GOOGLE_CLIENT_ID` and `GOOGLE_CLIENT_SECRET` value
  and put them in your `.env` file
* Add your own UCSB email address, `phtcon@ucsb.edu`, and your mentors email (see <{{page.teams_url}})
* Add your own UCSB email address after `phtcon@ucsb.edu`, and your mentor's email (see <{{page.teams_url}}>) separated by commas (no spaces) like this:
  
  ```
  ADMIN_EMAILS=phtcon@ucsb.edu,mentorsemail@ucsb.edu,youremail@ucsb.edu
  ```

* Then, use `mvn compile` to make sure that the code compiles.
* Next, try `mvn test` to be sure that the test cases pass.
* Then, run the following two commands separately in their own shells
  * In the first, launch the React frontend using `npm start` in the frontend directory. This should start the frontend on port 3000
  * In the second, launch the Spring Boot backend using `mvn spring-boot:run`.  This should start a web server on port 8080

The `mvn spring-boot:run` command is a shortcut that is provided for us to be able to run the jar file.  It does pretty much the same thing as 
if we ran the `.jar` file and specified the class containing our `main` on the command line.

When the app is up and running, try logging in on your localhost
implementation with your UCSB Google Account.  

# Step 4: Create a new Dokku App


In this step, we'll deploy our Spring Boot application to the public internet using Dokku.

The name of your app will be the same
as the name of your repo, e.g. (e.g. <tt>{{page.title}}-cgaucho</tt>)

Follow the instructions here:

* <https://ucsb-cs156.github.io/topics/dokku/getting_started.html>

You will also need to configure the Dokku app with
* environment variables as described here: <https://ucsb-cs156.github.io/topics/dokku/environment_variables.html>
* a postgres database as described here: <https://ucsb-cs156.github.io/topics/dokku/postgres_database.html>

You may also need to look at the logs to debug what's going wrong:
* <https://ucsb-cs156.github.io/topics/dokku/logs.html>


# What if it doesn't work?

If it doesn't work:

* Check on the Slack channel <tt>#help-{{page.num}}</tt> to see if there are any known issues. 
* Ask folks on your own team for help first on your team's slack channel.
* Post a specific question on the <tt>#help-{{page.num}}</tt> slack channel—note what you were trying to do, what you expected, and what happened instead.  Screenshots or copy/pasted console output is helpful!
* Come to office hours (posted here: <{{page.office_hours_pages}}>)
* Ask during class on `#help-lecture-discussion`


# Step 5: Add link to running app to your README.md file

Near the top of your README.md file, there should be a place
for a link to the running app (i.e. the running app on Dokku)

When you have it running, **put the link to this app near the
top of your README file**.

Then: **delete any "TODO comment" that was
there telling you to do this.**


# Step 6: Submit on Canvas

Here's a checklist to look over before submitting on Canvas:

1. On the main page for the repo: is the app "green on CI"? i.e. does the `main` branch have a green check for the Github Actions scripts?
2. On the main page for the repo: is there a link to the apps Github Pages site on the main page for the repo?  (i.e. the site whose URL is something like `https://ucsb-cs156-s23.github.io/jpa03-cgaucho`)?
3. Does the Github Pages site link take you to a page with links to
   javadoc and storybook?
4. Do those javadoc and storybook links work?
5. In the README.md file: is there a link to the running app?
6. Does OAuth work on the running app, i.e. can I log in with my Google login?
7. Did you remember to add the instructor, your mentor, your fellow teamm members, and yourself to the "test users" in your OAuth Consent Screen that you created? 
8. Did you deploy a database, and if so, do the CRUD operations work when you log in?

If so, then you are ready to submit on Canvas.  

* Submit the link to your repo, not the link to your running app.


# Grading Rubric:

* (10 pts) Basic Logistics
  - Having a repo with the correct name in the correct organization with the starter code for this lab
  - There is a post on Canvas for this assignment that has the correct content
* (10 pts) README has a link to your repo.
* (20 pts) Having a running web app at <tt>https://{{page.num}}-<i>githubid</i>.dokku-xx.cs.ucsb.edu</tt>
* (20 pts) Running web app has the ability to login with OAuth through a Google Account.
* (20 pts) Github Pages are set up correctly.
* (20 pts) GitHub Actions runs correctly and there is a green check (not a red X) on your main branch

Note that the Rubric above is subject to change, but if it does:
* You'll be notified during a class meeting 
* You'll have an additional week from the date of the announced change to get your repo in shape with the new requirements.
