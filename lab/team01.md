---
description: React CRUD operations
assigned: 2023-04-20 15:00
due: 2023-04-28 23:59
layout: default
title: team01
ready: true
layout: default
parent: lab
course_org: https://github.com/ucsb-cs156-s23
course_org_name: ucsb-cs156-s23
starter_repo: https://github.com/ucsb-cs156-s23/STARTER-team01
starter_repo_ssh: git@github.com:ucsb-cs156-s23/STARTER-team01.git
course_software: https://ucsb-cs156.github.io/s23/info/software.html
canvas_url: TBD
sample_deployed_app: https://ucsb-cs156-s23.github.io/STARTER-team01
kanban_setup: https://ucsb-cs156.github.io/s23/hwk/p06/
---

# {{page.title}} - {{page.description}}


## Team Programming Assignment: React CRUD operations

This is a team programming assignment.  Each team has it's own repo to complete this assignment, and you will work as a team.

In this assignment, you'll be given the starter code for this web app, which you should go explore a bit right now:

* <{{page.sample_deployed_app}}>

You'll see that there is a link called Restaurants which leads to a set of web pages
where you can do CRUD operations (Create, Read, Update, Destroy) on Restaurants.

You'll be working to add similar operations for three additional things, as explained
in the participation activity <{{page.kanban_setup}}>

Here are links to the repos:

| 5pm | 6pm | 7pm |
|-----|-----|-----|
| [{{page.title}}-{{site.qxx}}-5pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-1) | [{{page.title}}-{{site.qxx}}-6pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-1) | [{{page.title}}-{{site.qxx}}-7pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-1)  |
| [{{page.title}}-{{site.qxx}}-5pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-2) | [{{page.title}}-{{site.qxx}}-6pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-2) | [{{page.title}}-{{site.qxx}}-7pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-2)  |
| [{{page.title}}-{{site.qxx}}-5pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-3) | [{{page.title}}-{{site.qxx}}-6pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-3) | [{{page.title}}-{{site.qxx}}-7pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-3)  |
| [{{page.title}}-{{site.qxx}}-5pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-4) | [{{page.title}}-{{site.qxx}}-6pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-4) | [{{page.title}}-{{site.qxx}}-7pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-4)  |
{:.table .table-sm .table-striped .table-bordered}


## Submission/Grading

* Grading for this assignment is manual; someone on your team will submit the url to the [Canvas link for {{page.title}}]({{page.canvas_url}}) when the team thinks the site is ready for grading.


## Step 1: Understand the assignment

Read through <{{page.kanban_setup}}> if you haven't already.

The rest of this explains how to proceed.

## Step 2: Set up the repo for the team

Next, choose one person that will carry out the following task while sharing their screen; the rest of you should follow along.  If you are on zoom, go into a breakout room for your team, and follow along there.

* Clone your teams <tt>{{page.title}}-teamName</tt> repo.
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

  change `STARTER-team01` to `team01-s23-5pm-1` or whatever your team's name is

  Commit this change to the main branch, and push.

* One more one line change in `frontend/package.json`

  Change this:
  
  ```
  "homepage": "https://ucsb-cs156-s23.github.io/STARTER-team00/",
  ```
  
  to this (substituting in your team name, not the one shown):
  
  ```
  "homepage": "https://ucsb-cs156-s23.github.io/team01-s23-7pm-3/",
  ```

  You should see that commiting and pushing these changes 
  kicks off a GitHub Action (look at the Actions tab in your repo) that publishes the
  site to the gh-pages branch.

  Once that finishes, you'll need to enable GitHub Pages, which is the next step


## Step 3: Set up Github pages

Enable GitHub Pages for your repo by going to the Settings tab, finding Pages, and making it look like this:
  
<img width="545" alt="image" src="https://user-images.githubusercontent.com/1119017/231609350-e5947a84-1ff2-497b-bc89-dce00cfdb757.png">

Then, on your {{page.title}} Github repo page, find the place at right that looks like this:

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

Now, you are ready to start coding to work on your issues.

First come up with a branch name, and a branch naming convention.
* If your name is Chris, and you are adding hotelFixtures, you might call your branch `Chris-HotelFixtures`
* Or: if you are working on issue7, you might call it `issue7-Chris`
* Discuss the branch naming convention with your team on your team's slack channel
  before starting.

To create your branch, cd into your cloned repo, and use this command:

```
git checkout main
git pull origin main
git checkout -b Chris-hotelFixtures
```

This creates a new branch `Chris-hotelFixtures` that is branched off a fresh copy of the main branch.

You'll do all of your work in this branch, and when you are done, you'll do a *Pull Request* to get your code into the `main` branch.  

* *Note that using this workflow is a required part of the assignment*.   
* We are practicing a workflow (the GitHub feature-branch/pull-request workflow) that will become super important later in the course, and even more important when you work on real world projects.

## Step 6: Work on your issues

I will add more details here about the specific issues
* adding the fixture
* adding the CRUD utilities
* adding the form
* adding the table
* adding the Create and Edit pages
* adding the index and details pages

But for the most part, you'll just follow the example code for Restaurants.

Be sure that for each file you add, you also look under stories and tests, not just main!

<summary markdown="1">
<details>
Step 6a: Adding the fixture
</details>

The model to follow here is [`frontend/src/fixtures/restaurantFixtures.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/fixtures/restaurantFixtures.js)

The purpose of the fixtures file is to serve as a source of examples objects.  It has several use cases:
* "A single source of truth" to document the fields that you are expecting in an object of this type.
* A source of example data for the Storybook stories
* A source of data to be used in tests

The fixtures files are one of the few cases where we implement code, but don't also implement a test to go along with it.

To create your fixtures file, create a file with a similar name, e.g.
* `hotelFixtures.js`
* `bandFixtures.js`
* `bookFixtures.js`
* etc...

First, lets understand the code inside `restaurantFixtures.js`:

Inside the file, at the top level, we see this (with some code omitted so we can focus on the big picture):

```javascript
const restaurantFixtures = {
   // code omittted  
};

export { restaurantFixtures };
```

This sets the variable `restaurantFixtures` to a Javascript object (delimited by a set of curly braces, `{ }`), and then exports that variable so that 
you can import the variable in another file with code like this (from [`RestaurantForm.stories.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/stories/components/Restaurants/RestaurantForm.stories.js)

```
import { restaurantFixtures } from 'fixtures/restaurantFixtures';
```

Diving a bit deeper into the `restaurantFixtures` object, but still omitting some detail, we see that the
structure of the object is a set of key/value pairs.  The two keys in this case are `oneRestaurant` and `threeRestaurants`.
In each case, the values are arrays (delimited in Javascript by a set of square brackets, `[ ]`).  Keys are followed by a colon (':')
and then the value.  Key/value pairs are separated by commas. 

```js
const restaurantFixtures = {
    oneRestaurant:
    [
      // details omitted
    ],

    threeRestaurants:
    [
      // details omitted
    ]
};
```

Finally, we can look inside `oneRestaurant` and see that the value of `oneRestaurant` is an array containing a single object
representing the fields in a restaurant:

```js
oneRestaurant:
    [
      {
       "id": 1,
        "name": "The Habit",
        "address": "888 Embarcadero del Norte",
        "city": "Isla Vista",
        "state": "CA",
        "zip": "93117",
        "description": "Burgers and Fries"      
      }
    ],
```

Note that in the current starter code `STARTER-team01`, our implementation only provides for `id`, `name`, and `description`.  The intent is to eventually implement the fields `address`, `city`, `state`, and `zip` as well.  For the fixtures you create, it is only necessary to put in fields for `id` and the three fields you intend to implement as part of your CRUD operations.

The value of `threeRestaurants` is similar, so we won't describe it in detail, but look it over before continuing to make sure you understand the code.

Now, you are ready to create a fixtures file for your object.  For the instructions, we'll assume that you are creating fixtures for a hotel;
adjust the instructions accordingly for your object.

1. Start with a copy of `restaurantFixtures.js`
2. Do a search/replace on `restaurant`, replacing it with `hotel` (or whatever).
3. Replace the object inside what was `oneRestaurant` but is now, for example, `oneHotel`, with one that has the key/value pairs of the fields you
   want for your object.  Keep the `id` field (which should be an integer), but replace the other fields of `restaurant` with key/value pairs
   that are appropriate for your object.  You need a minimum of three fields beyond `id`; you can implement more if you like, 
   but since this is just an exercise, I suggest you keep it simple.
4. Now replace the objects inside `threeHotels` with three objects that are different from (and have different id values) from the ones
   in your `oneHotel` object.  I suggest that you keep the sample ids as `2`, `3, `4`, since that will make coding the tests later 
   easier&mdash;the example tests expect the id of one of the fixtures to be `2`, `3` and `4`.  But it's your choice. Just know that if you
   choose different id numbers, you'll need to adjust the testing code later accordingly.
</summary>


### Make Good Commit Messages

As you work on your page, make commits whenever something is working.
* Use your initials at the start of your commit message (e.g. `cg` for "Chris Gaucho")
* Separate your initials from your message with a hyphen
* Your message should describe what you did

Examples:

* `git commit -m "cg - added hotelFixtures`
* `git commit -m "cg - added HotelCreate page"`

Having meaningful commit messages is a component of your grade for this assignment, so please do put some thought into what you write.

As you make commits, push them to your branch, for example:

```
git push origin Chris-hotelFixtures
```

A few handy commands:
* `git status` shows what branch you are on, among other things
* `git branch -a` shows all current branches
* `git fetch` updates information about branches by pulling new branch names from GitHub



## Step 7: Do a pull request

As you do your pull request, drag the issue on the Kanban board into the "In Review" column.

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

Then:
* get a new issue from TODO
* assign it to yourself (and if applicable to your pair partner), and
* drag it into In Progress
* and start working in a new branch

You may need to create a branch *from* your previous branch (instead of from `main`) if you
are building on code in an earlier PR.

## Step 8: Merging the Pull Requests

At this step, you should coordinate with one another again.

The aim here is for each of you to merge *someone else's pull request* (not your own).

Note that because each of you were making changes in `App.js` and in `AppNavbar.js`, there is a potential for
*merge conflicts*. Fortunately, these will be easy to resolve!  But the process for resolving them can be a little tricky,
so we'll go over it in lecture.

As each pull request is merged into the main branch, you should see the page populate on the
running app on Github Pages.

When all six are merged into the main branch and appearing in the app, your team is done with this assignment.

## Step 9: Submission/Grading

* Grading for this assignment is manual; someone on your team will submit the url to the [Canvas link for team00]({{page.canvas_url}}) when the team thinks the site is ready for grading.

# End of assignment


# Links to running webapps

| 5pm | 6pm | 7pm |
|-----|-----|-----|
| [{{page.title}}-{{site.qxx}}-5pm-1](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-5pm-1) | [{{page.title}}-{{site.qxx}}-6pm-1](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-6pm-1) | [{{page.title}}-{{site.qxx}}-7pm-1](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-7pm-1)  |
| [{{page.title}}-{{site.qxx}}-5pm-2](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-5pm-2) | [{{page.title}}-{{site.qxx}}-6pm-2](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-6pm-2) | [{{page.title}}-{{site.qxx}}-7pm-2](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-7pm-2)  |
| [{{page.title}}-{{site.qxx}}-5pm-3](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-5pm-3) | [{{page.title}}-{{site.qxx}}-6pm-3](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-6pm-3) | [{{page.title}}-{{site.qxx}}-7pm-3](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-7pm-3)  |
| [{{page.title}}-{{site.qxx}}-5pm-4](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-5pm-4) | [{{page.title}}-{{site.qxx}}-6pm-4](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-6pm-4) | [{{page.title}}-{{site.qxx}}-7pm-4](https://ucsb-cs156-{{site.qxx}}.github.io/{{page.title}}-{{site.qxx}}-7pm-4)  |
{:.table .table-sm .table-striped .table-bordered}

# Links to Pull Requests

| 5pm | 6pm | 7pm |
|-----|-----|-----|
| [{{page.title}}-{{site.qxx}}-5pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-1/pulls) | [{{page.title}}-{{site.qxx}}-6pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-1/pulls) | [{{page.title}}-{{site.qxx}}-7pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-1/pulls)  |
| [{{page.title}}-{{site.qxx}}-5pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-2/pulls) | [{{page.title}}-{{site.qxx}}-6pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-2/pulls) | [{{page.title}}-{{site.qxx}}-7pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-2/pulls)  |
| [{{page.title}}-{{site.qxx}}-5pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-3/pulls) | [{{page.title}}-{{site.qxx}}-6pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-3/pulls) | [{{page.title}}-{{site.qxx}}-7pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-3/pulls)  |
| [{{page.title}}-{{site.qxx}}-5pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-4/pulls) | [{{page.title}}-{{site.qxx}}-6pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-4/pulls) | [{{page.title}}-{{site.qxx}}-7pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-4/pulls)  |
{:.table .table-sm .table-striped .table-bordered}

# Links to Repos

| 5pm | 6pm | 7pm |
|-----|-----|-----|
| [{{page.title}}-{{site.qxx}}-5pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-1) | [{{page.title}}-{{site.qxx}}-6pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-1) | [{{page.title}}-{{site.qxx}}-7pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-1)  |
| [{{page.title}}-{{site.qxx}}-5pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-2) | [{{page.title}}-{{site.qxx}}-6pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-2) | [{{page.title}}-{{site.qxx}}-7pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-2)  |
| [{{page.title}}-{{site.qxx}}-5pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-3) | [{{page.title}}-{{site.qxx}}-6pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-3) | [{{page.title}}-{{site.qxx}}-7pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-3)  |
| [{{page.title}}-{{site.qxx}}-5pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-4) | [{{page.title}}-{{site.qxx}}-6pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-4) | [{{page.title}}-{{site.qxx}}-7pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-4)  |
{:.table .table-sm .table-striped .table-bordered}
