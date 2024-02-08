---
title: team03
desc: "Team Project: React CRUD frontend"
assigned: 2024-02-07 09:00
due: 2024-02-20 11:59
github_org: ucsb-cs156-w24
layout: lab
layout: default
parent: lab
num: team03
nav_order: 203
ready: true
starter: https://github.com/ucsb-cs156-w24/STARTER-team03
deployment: https://team03.dokku-00.cs.ucsb.edu/
storybook: https://ucsb-cs156-w24.github.io/STARTER-team03/storybook/
canvas: https://ucsb.instructure.com/courses/17178/assignments/192317
---

Canvas link: <{{page.canvas}}>

{% include drop_down_style.html %}

# {{page.title}}&mdash;{{ page.desc }}

## What are we learning in team03

In this team project, our starter code has a frontend and backend, and we are focusing only on the frontend; you will likely not have to make any modifications to the backend (other than copying your backend code from
team02.)

We are focusing on learning these new React concepts:

* Adding new items to the navbar
* Adding components for new placeholder pages
* Adding routes in `App.js` to link urls to pages
* Creating a component that uses the `OurTable` component to create a table
* Changing the placeholder page so that it loads data using the `useBackend` hook to fetch data
* Using the `ButtonColumn` feature of `OurTable` to add a delete button
* Using `npm test` to run unit tests
* Using `npm run coverage` to run test coverage
* Using `npx stryker run` to run mutation coverage
* Using `npm run storybook` to visualize frontend components in isolation


## Repos for team03

Here are the links to the repos for team03

| 4pm | 5pm | 6pm | 7pm|
|-----|-----|-----|----|
|[{{page.title}}-{{site.qxx}}-4pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-4pm-1)|[{{page.title}}-{{site.qxx}}-5pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-1)|[{{page.title}}-{{site.qxx}}-6pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-1)|[{{page.title}}-{{site.qxx}}-7pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-1)|
|[{{page.title}}-{{site.qxx}}-4pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-4pm-2)|[{{page.title}}-{{site.qxx}}-5pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-2)|[{{page.title}}-{{site.qxx}}-6pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-2)|[{{page.title}}-{{site.qxx}}-6pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-2)|
|[{{page.title}}-{{site.qxx}}-4pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-4pm-3)|[{{page.title}}-{{site.qxx}}-5pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-3)|[{{page.title}}-{{site.qxx}}-6pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-3)|[{{page.title}}-{{site.qxx}}-6pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-3)|
|[{{page.title}}-{{site.qxx}}-4pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-4pm-4)|[{{page.title}}-{{site.qxx}}-5pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-5pm-4)|[{{page.title}}-{{site.qxx}}-6pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-6pm-4)|[{{page.title}}-{{site.qxx}}-6pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/{{page.title}}-{{site.qxx}}-7pm-4)|

## Project boards (also called Kanban boards):

| 4pm | 5pm | 6pm | 7pm|
|-----|-----|-----|----|
| [team03-{{site.qxx}}-4pm-1](https://github.com/orgs/{{page.github_org}}/projects/59) | [team03-{{site.qxx}}-5pm-1](https://github.com/orgs/{{page.github_org}}/projects/63) |[team03-{{site.qxx}}-6pm-1](https://github.com/orgs/{{page.github_org}}/projects/67) | [team03-{{site.qxx}}-7pm-1](https://github.com/orgs/{{page.github_org}}/projects/71) |
| [team03-{{site.qxx}}-4pm-2](https://github.com/orgs/{{page.github_org}}/projects/60)| [team03-{{site.qxx}}-5pm-2](https://github.com/orgs/{{page.github_org}}/projects/64)|[team03-{{site.qxx}}-6pm-2](https://github.com/orgs/{{page.github_org}}/projects/68)| [team03-{{site.qxx}}-7pm-2](https://github.com/orgs/{{page.github_org}}/projects/72)|
| [team03-{{site.qxx}}-4pm-3](https://github.com/orgs/{{page.github_org}}/projects/61)| [team03-{{site.qxx}}-5pm-3](https://github.com/orgs/{{page.github_org}}/projects/65)|[team03-{{site.qxx}}-6pm-3](https://github.com/orgs/{{page.github_org}}/projects/69)| [team03-{{site.qxx}}-7pm-3](https://github.com/orgs/{{page.github_org}}/projects/73)|
| [team03-{{site.qxx}}-4pm-4](https://github.com/orgs/{{page.github_org}}/projects/62) | [team03-{{site.qxx}}-5pm-4](https://github.com/orgs/{{page.github_org}}/projects/66) |[team03-{{site.qxx}}-6pm-4](https://github.com/orgs/{{page.github_org}}/projects/70) | [team03-{{site.qxx}}-7pm-4](https://github.com/orgs/{{page.github_org}}/projects/74) |

For team03, the Kanban board is populated by the staff before you start using the Github Actions workflow [`99-team02.yml`](
{{page.starter}}/blob/main/.github/workflows/99-team02.yml); if your Kanban is not yet populated,
please check in with the staff.

## Dokku prod deployments

These deployments should track the `main` branch.  **You will need to manually redeploy** after you merge each pull request, with these commands (adapted for your team; the example shows 7pm-1):

```
dokku git:sync team03 https://github.com/ucsb-cs156-w24/team03-w24-7pm-1 main
dokku ps:rebuild team03
```

| 4pm | 5pm | 6pm | 7pm|
|-----|-----|-----|----|
| 4pm-1: <https://{{page.title}}.dokku-01.cs.ucsb.edu> | 5pm-1: <https://{{page.title}}.dokku-05.cs.ucsb.edu> | 6pm-1: <https://{{page.title}}.dokku-09.cs.ucsb.edu> |  7pm-1: <https://{{page.title}}.dokku-13.cs.ucsb.edu> |
| 4pm-2: <https://{{page.title}}.dokku-02.cs.ucsb.edu> | 5pm-2: <https://{{page.title}}.dokku-06.cs.ucsb.edu> | 6pm-2: <https://{{page.title}}.dokku-10.cs.ucsb.edu> |  7pm-2: <https://{{page.title}}.dokku-14.cs.ucsb.edu> |
| 4pm-3: <https://{{page.title}}.dokku-03.cs.ucsb.edu> | 5pm-3: <https://{{page.title}}.dokku-07.cs.ucsb.edu> | 6pm-3: <https://{{page.title}}.dokku-11.cs.ucsb.edu> |  7pm-3: <https://{{page.title}}.dokku-15.cs.ucsb.edu> |
| 4pm-4: <https://{{page.title}}.dokku-04.cs.ucsb.edu> | 5pm-4: <https://{{page.title}}.dokku-08.cs.ucsb.edu> | 6pm-4: <https://{{page.title}}.dokku-12.cs.ucsb.edu> |  7pm-4: <https://{{page.title}}.dokku-16.cs.ucsb.edu> |

## Work on your own laptop, not CSIL

You should be working with a Java and Node (Javascript) setup on your
own laptop by this point, not on CSIL.

For advice on what to install, see:
* <https://ucsb-cs156.github.io/w24/info/software.html>

If this presents a difficulty, please contact the instructor ASAP so that some arrangement can be made for your situation.

## What are we doing in team03?

In this team project, you'll continue the work you started in team02.

The starter code has examples of:

* Implementing backend CRUD operations for two database tables  (this is exactly like team02)

* Implementing a user-friendly frontend for the CRUD operations
  for these two database tables using Javascript and React (this is the new part)

It also has an example of temporary placeholder pages for CRUD operations, which is an intermediate step towards the full CRUD frontend code.

Basically, the task of team03 is to use this example code to build frontends for the backends you built in team02.

## Understanding what you are building

The best way to understand what you are building is to play with a
deployment of the starter code.

You can try out an example of the user-friendly CRUD frontend at the link below;
it's a deployment of the starter code repo <{{page.starter}}>. If you login
with your UCSB email, you should have admin access (provided you are
a registered student this quarter), and you should be able to do CRUD operations
on two database tables, `Restaurants` and `UCSBDates` (more information
on this later in this project writeup).

* <{{page.deployment}}>

I suggest you take a moment to experiment with various pages of that app.
Here are some things to explore:

* When not logged in, you'll have no access to the CRUD operations
  for the app.  But when you login, you should see two new items
  on the menu for `Restaurants` and `UCSBDates`.
* All registered students should have admin access when logging in with
  their UCSB email.  This will allow you to add new records and
  edit existing ones.
* If you have another Google email, you can log in with that; you should
  see that you have read only access to the two database tables.
* You'll also see a menu item called `Placeholder`.  This is example code
  for making a set of "placeholder pages", which are a useful intermediate
  step when building a new set of pages for the table (more on that later).
* The initial page that comes up at the `Restaurants` or `UCSBDates` link
  is called the *Index Page*.  It lists all of the records in the table.
  Note that you can sort by any column by clicking in the header.
* There is a link at the top of each page that takes you to
  the *Create Page* where you can create new database records. Try it out.
* When you create a new record, you are redirected back to the *Index Page*.
* There are also buttons that allow you to Delete or Edit a record. Try
  them as well. Note that the Delete button leaves you on the Index page,
  while the Edit button takes you to a separate Edit page.  Note that
  the URL changes.

What you'll be doing (as a team) is adding additional menu items alongside `Restaurants` and `UCSBDates`, providing similar CRUD operations for four, five or six of these tables (the sames ones from team02):

* `UCSBDiningCommonsMenuItem`
* `UCSBOrganization`
* `RecommendationRequest`
* `MenuItemReview`
* `HelpRequest`
* `Articles`

You'll reuse the backend files you built for team02; copying them over
is one of the first steps in the lab. Then you'll build a frontend in Javascript using the React framework.

## Understanding the Starter Code

A React frontend is built using *Components*.  In our code base,
each React component is in a separate file under one of these two directories:

* `frontend/src/main/pages`: each of these components provides a single web page of the application.  These components are registered in a file called `frontend/src/App.js` which maps frontend routes (i.e. URLs) to the React Component that provides that page.
* `frontend/src/main/components`: each of these components is a portion of a page.

So the files under `pages` and `components` are technically both "React Components"; the page files are a "special case" of components that are
mapped to routes in `App.js`.

Typically, we try to factor out as much of the user interface code as possble into the component files, especially any code that can be reused.

Page files typically are responsible for getting and or posting data to/from backend APIs and communicating with components that make up the page.

Data can be passed into components through `props`, the parameters that each component takes.  By convention, these are passed in a Javascript object,
which is why you see `{}` around the names of the parameters to React Components.

Data is typically returned from components via "callback functions" that are passed into the components as part of their props.

Finally, note that under both `frontend/src/main/components` and `frontend/src/main/pages`, you'll see that the code is sometimes organized into subdirectories(folders); this is at the discretion of the coder, but it does make finding things easier, so it is a recommended practice.  Consistent naming conventions also help keep the code organized.

## Tests and Stories

For each React component, whether it's under `components` or `pages`, we have tests and stories.

* The tests are automated unit tests, similar to the JUnit tests we wrote for our Java code.  Just as we used JUnit for Java, for our React code we use a framework called Jest, along with tools for test coverage, and mutation testing (Stryker).
* The stories are for a tool called Storybook. Storybook allows both interactive testing (i.e. human testing) of React Components in isolation
from other components; think of it as "live unit testing".  It also provides
a way to document our catalog of Components.  Storybook fills the same niche for frontend programming that Swagger fills for backend programming.

As you work through the issues on the Kanban board for this project, you'll
see that for each React component we develop, we are also going to implement
tests and stories for each one.

You can experiment with the published storybook for the Starter code at
this link:

* <{{page.storybook}}>

Note that when you interact with pages in the app, they are connected
to a real backend with a real database.  By contrast, when you interact
with the pages and components in the storybook, all of the interactions
are "mocked":

* For `GET` requests, we load data from mock endpoints to test the component in
isolation.
* For `POST,PUT,DELETE` requests, we log the calls using `console.log` and/or `window.alert` so that can see what the component would have sent to the backend.

We can set up multiple "stories" for each component with different values
for the mocked GET calls, as well as different values of the "props"(parameters) passed into each React component.

This has several benefits:
* Writing the stories helps to identify and document the APIs and prop values on which our React components depend.
* It also gives us a way to interactively test the component under various conditions, similar to what we do with Unit tests, but with the advantage that we can see what's happening directly in our browser
* Finally, when bugs arise in the real application, we can use Storybook in combination with Swagger to determine whether the problem is in the backend, the frontend, or the communication between the two.

## Assigning the database tables to your team

The tables you'll need to divide up among the team members are the same ones
as in team02.  You can assign team members to the same tables, or you can
switch it up; that's up to you.

The six tables are:

* `UCSBDiningCommonsMenuItem`
* `UCSBOrganization`
* `RecommendationRequest`
* `MenuItemReview`
* `HelpRequest`
* `Articles`

I suggest you divide up these tables on your Slack channel first.
There is also an issue on the Kanban board to update this in the `README.md`
of your team03 repo.

## The examples: Restaurant and UCSBDate

The two database tables in the starter code are these:

* `Restauarants`, which represents data about a restaurant; just
  a name and description, such as:

  ```json
    {
            "id": 2,
             "name": "Cristino's Bakery",
             "description": "Takeout only.  It may look mostly like a bakery with Mexican pastries, but it also has amazing burritos and tacos",
        },

        {
            "id": 3,
             "name": "Freebirds",
             "description": "Burrito joint, and iconic Isla Vista location"
        },

        {
            "id": 4,
             "name": "Ca' Dario Cucina Italiana",
             "description": "White tablecloth Italian restaurant, with great pasta and pizza"
        },
  ```

* `UCSBDate`, which represents dates from the UCSB calendar.

  The UCSBDates table is intended
  as a place to store dates such as these
  The ideas is to store each date as a single record, like this:
  ```json
  [
    {
      "quarter": "20234",
      "name": "firstDayOfClasses",
      "datetime": "2023-09-28T00:00:00",
    },
    {
      "quarter": "20234",
      "name": "lastDayOfClasses",
      "datetime": "2023-12-08T00:00:00",
    },
    {
      "quarter": "20234",
      "name": "firstDayOfFinals",
      "datetime": "2023-12-09T00:00:00",
    },
    // etc.
  ]
  ```
  <details markdown="1">
  <summary>
  More details about this table
  </summary>
  Quarters are represented by a five digit number where the first four
  digits are the year, and the final digit is either 1, 2, 3, or 4, for
  Winter, Spring, Summer and Fall, respectively.  This may seem like a
  weird format, but it's the one used internally by systems like GOLD.
  The `yyyyq` format  has the advantage that when you sort, the quarters come out in the right order.  That would not be true if you sorted `['F22', 'W23', 'S23','w24', 'w24']` in lexicographic order; they would come out `['F22', 'w24', 'w24','S23', 'W23']` which is an order that makes no sense.

  For reference only,
  here's a complete list of UCSBDates for w24. This list is in the original
  format used by the
  [UCSB Developer API's Academic Quarter Calendar](https://developer.ucsb.edu/content/academic-quarter-calendar). Note that in the format, each record is for
  a single quarter, while in our table, each record represents a single date.


  ```json
  {
    "quarter": "20234",
    "qyy": "w24",
    "name": "FALL 2023",
    "category": "FALL",
    "academicYear": "2023-2024",
    "firstDayOfClasses": "2023-09-28T00:00:00",
    "lastDayOfClasses": "2023-12-08T00:00:00",
    "firstDayOfFinals": "2023-12-09T00:00:00",
    "lastDayOfFinals": "2023-12-15T00:00:00",
    "firstDayOfQuarter": "2023-09-24T00:00:00",
    "lastDayOfSchedule": "2023-12-15T00:00:00",
    "pass1Begin": "2023-05-15T09:00:00",
    "pass2Begin": "2023-05-22T08:30:00",
    "pass3Begin": "2023-09-11T09:00:00",
    "feeDeadline": "2023-09-15T00:00:00",
    "lastDayToAddUnderGrad": "2023-10-18T00:00:00",
    "lastDayToAddGrad": "2023-12-08T00:00:00",
    "lastDayThirdWeek": null
  }
  ```
  </details>

## An aside about the placeholder  pages

You may have noticed a menu item called `Placeholder` on the
starter code deployment here (login and try it out if you haven't yet):

* <{{page.deployment}}>

Normally, we would not want real users to see placeholder pages such as
these in a real app; but there are times that we might want them to be
in the `main` branch of our code so that we can start integrating a new
feature early.

One way to resolve this is with the use of something called [Feature Toggles](https://en.wikipedia.org/wiki/Feature_toggle).  Feature toggles allow
us to configure an app to run in different modes in different deployments,
and are sometimes used to release a new feature in stages.  It can be put
into the `main` branch, but enabled in some developer and qa deployments
and disabled in others.  The important things to keep in mind are:
* The app should be tested with the feature both on and off before PRs
  are merged to `main`
* This allows a new feature to be incorporated into the `main` branch in
  stages until it is finally ready to show to customers.
* Sometimes, feature toggles can be on a user-by-user basis, so that
  a new feature can be introduced to some "early adopter" users that
  have a higher tolerance for things that are still in an early state;
  this allows early feedback about new features, which is a key
  part of the Agile software design philosophy.

Note that we are not using feature toggles in team03 (at least not as of
w24, though it would be a nice thing to incorporate into a future version
of the project.)   But I wanted to be clear about how this "placeholder" code
might be handled if this were a real-world code base, and not an
exercise.

## Understanding the issues on the Kanban board

The Kanban boards for team03 are set up here:

| Team | Kanban Board |
|------|--------------|
|w24-4pm-1 | <https://github.com/orgs/ucsb-cs156-w24/projects/59>|
|w24-4pm-2 | <https://github.com/orgs/ucsb-cs156-w24/projects/60>|
|w24-4pm-3 | <https://github.com/orgs/ucsb-cs156-w24/projects/61>|
|w24-4pm-4 | <https://github.com/orgs/ucsb-cs156-w24/projects/61>|
|w24-5pm-1 | <https://github.com/orgs/ucsb-cs156-w24/projects/63>|
|w24-5pm-2 | <https://github.com/orgs/ucsb-cs156-w24/projects/64>|
|w24-5pm-3 | <https://github.com/orgs/ucsb-cs156-w24/projects/65>|
|w24-5pm-4 | <https://github.com/orgs/ucsb-cs156-w24/projects/66>|
|w24-6pm-1 | <https://github.com/orgs/ucsb-cs156-w24/projects/67>|
|w24-6pm-2 | <https://github.com/orgs/ucsb-cs156-w24/projects/68>|
|w24-6pm-3 | <https://github.com/orgs/ucsb-cs156-w24/projects/69>|
|w24-6pm-4 | <https://github.com/orgs/ucsb-cs156-w24/projects/70>|
|w24-7pm-1 | <https://github.com/orgs/ucsb-cs156-w24/projects/71>|
|w24-7pm-2 | <https://github.com/orgs/ucsb-cs156-w24/projects/72>|
|w24-7pm-3 | <https://github.com/orgs/ucsb-cs156-w24/projects/73>|
|w24-7pm-4 | <https://github.com/orgs/ucsb-cs156-w24/projects/74>|

The issues on your Kanban board can be grouped as follows:

* Project Scope issues (6 issues): These are one-time tasks, and should be divided among
  the team members in some reasonably equitable fashion, at the discretion of
  the team.  Note that 'equitable' doesn't necessarily mean 'equal'; not all of
  these issues involve an equal amount of work.  It's more a sense among the
  team members that the workload is being shared in a "fair" way, whatever
  that means to the members of your team.
  - Add table to README.md (table of who is doing which table)
  - Set up GitHub Pages
  - Set up Team prod deployment
  - Set up Team qa deployment
  - Adjust links in README.md (links to prod and qa deployments, etc.)
  - Submit for grading on Canvas (on behalf of team)

* Database Table Scope issues (48 issues, 8 per table): These are repeated for each database table
  - Backend Controller and Tests (copying from team02)
  - Fixtures (example data for testing)
  - Form Component (an HTML form for data entry)
  - Table Component (a HTML Table for visualizing lists of data)
  - Copy Placeholder pages; add to App.js/AppNavbar.js
  - Create Page (a page where admins can create new items in the table)
  - Edit Page (a page where admins can edit existing records)
  - Index Page (a page where any logged in user can list all items,
    and where admins can click to create, edit, or delete items)

Note that if you have fewer than 6 team members, you should go ahead
and close the issues for database tables that your team is not
implementing; you can also remove them from the Kanban board.

## Copying your team02 work into the starter code.

You'll start with the starter code `STARTER-team03`, and then add to it the files you created in team02 to implement
the database tables and backend CRUD operations

These will likely include, for each of the database tables you created in team02:
* A Java class for the `@Entity`
* A Java class for the `@Repository`
* A Java class for the Controller
* A Java class containing Controller tests

The first pull request you make should simply copy those files from your team02 repo into the appropriate directories.

I suggest one pull request per team member, rather than one giant pull request for the entire team, but that's up to you.

Historically, when teams have tried the one "giant pull request" approach, it sometimes works, but often a problem with one of the database tables holds up
all the rest.

Generally speaking, small, focused PRs are easier to get green on CI, code review and get merged, vs. large sprawling ones.

## General workflow for frontend code

To test the backend and frontend together:

* At top level of repo, run `mvn spring-boot:run` in one window (you'll need to configure your `.env` file with `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, and `ADMIN_EMAILS`)
* In a separate terminal window, cd into `frontend`, type `nvm use 16.20.0` and then run `npm start`

Remember that the first time you do that, you must first do:

```
nvm use 16.20.0
npm install
```

Here are some other commands, all things you do in the `frontend` directory
after first doing `nvm use 16.20.0; npm install` once in that session:

* Run tests locally: `npm test`.
* Run tests from one file locally: `npm test -- RestaurantsEditPage`
* Quickly test coverage locally: `npm run coverage`
* Check linting locally: `npx eslint --fix .`
* Check mutation coverage locally (slow): `npx stryker run`
* Check mutation coverage of single file (faster): `npx stryker run -m frontend/src/main/pages/Restaurants/RestaurantsEditPage.js`
* To run storybook locally: `npm run storybook`.

## Adding the placeholders

When adding the placeholders, you'll be making changes to `App.js`, `AppNavbar.js`, and `AppNavbar.test.js`.

You may end up with merge conflicts, but they should be easy to resolve.

The fact that you'll end up with merge conflicts here is a feature, not a bug:it's helpful to get some experience with how to resolve those in a context where:

* The merge conflicts are real, not contrived
* They are straightforward to resolve

Having some experience in resolving these will help you later on when you encounter more complex merge conflicts.


## Carrying out your issues

Now, take on each of the issues for your table on the Kanban board.

There are suggestions about how to proceed below.

Make a new branch each time, and do a separate pull request for each issue. In some cases, you may need to start your branch from a previous one.

As you finish each issue:
* Do a pull request, and ask for code reviews
* Check that the CI/CD tests are green. If they aren't fix that before starting the next issue.
* Once CI/CD is green, you do *not have to wait* for the code review and the PR to be merged before staring the next issue;
  you can just make a new branch off the previous branch and continue coding.
* However, we strongly encourage you to work with your team to try to get PRs merged as quickly as possible. Don't let them pile up.

Also, and I can't emphasize this enough: keep each PR small.   We are trying to get you into that habit, because it will pay off in the project phase, and in real world practice.

When all of your issues are either complete, or at least have open pull requests, turn your attention to helping the team to get finished.

# When done with your issues: check in with the team

* See if there are code reviews that you can help with
* See if anyone else on the team needs help with their tasks

# What comes after team03

After team03, we start the legacy code projects.

# Asking for help

If you need additional guidance, ask on the `#help-team03` channel, and we'll try to steer you in the right direction.

# When you are done

When all branches are merged to main, all tasks on Kanban board in the done column, please submit on Canvas as you did for team02.  Link coming soon.

# Videos

The following videos for team03 contain helpful information about carrying out the various steps.

Note that these are from an earlier quarter so if you find that you don't have access, let the instructor know; they may need to adjust the permissions.

Also, there may be slight differences between the assignment in earlier quarters and the assignment this quarter; in case of any discrepency, follow the
instructions in this file and in the issues on your Kanban board.  You can
also seek clarification on the #help-team03 channel.

List of videos:
* [Intro to Front End](https://gauchocast.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=6a3feb86-018d-4ff9-9212-ae8e015108de) (1 hr 14 minutes)
* [Adding Delete Button](https://gauchocast.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=76f95008-fe11-4d69-9463-ae9201678437) to Table (18 minutes)
* [FrontEnd Testing part 1](https://gauchocast.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=ef93222e-3712-4adc-872d-ae9300054f55) (20 minutes) (npm run coverage)
* [FrontEnd Testing part 2](https://gauchocast.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=3601f9cc-6bc1-4225-b1ff-ae9300055dc3) (14 minutes) (npm run coverage continued)
* [FrontEnd Testing part 3](https://gauchocast.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=3aa343d8-5aea-4390-9ab6-ae9300121554) (19 minutes) (eslint and stryker)
