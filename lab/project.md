---
title: project
desc: "Legacy Code Project instructions"
assigned: 2023-11-07 14:00
due: 2023-11-29 11:59
github_org: ucsb-cs156-f23
layout: lab
layout: default
parent: lab
num: project
nav_order: 300
f23_9am_1: https://github.com/orgs/ucsb-cs156-f23/projects/55
f23_9am_2: https://github.com/orgs/ucsb-cs156-f23/projects/52
f23_9am_3: https://github.com/orgs/ucsb-cs156-f23/projects/54
f23_10am_1: https://github.com/orgs/ucsb-cs156-f23/projects/57
f23_10am_2: https://github.com/orgs/ucsb-cs156-f23/projects/53
f23_10am_3: https://github.com/orgs/ucsb-cs156-f23/projects/56
f23_10am_4: https://github.com/orgs/ucsb-cs156-f23/projects/51
proj_courses_slack_url: tbd
proj_happycows_slack_url: https://ucsb-cs156-s23.slack.com/archives/C058QUC16QP
proj_gauchoride_slack_url: https://ucsb-cs156-s23.slack.com/archives/C0595EWELLA
---

# The Assignment, Briefly.

In this project:

* You will be assigned a legacy code base, and a set of issues 
  (new features, refactorings, bug fixes)
* The list of issues contains more work than we expect you will need to complete
  in order to get a perfect score on the project, so don't worry that you have
  to finish them all; *you do not have to finish them all*.
* Each issue you complete earns points for your team after it is:
  * code reviewed and approved by a member of your team that didn't work on it
  * code reviewed and approved by a member of the course staff (instructor, TA, LA)
  * merged into the main branch of your repo.
* Issues earn different numbers of points: typically, 5, 10 or 20 depending on 
  the complexity of the issue (more on this below).
* There may be a few issues that are marked as "must do".  You *must
  complete these* or their point values will be subtracted from the points you
  earn. These are assigned point values in advance.  
* For other issues,
  points are assigned after completion. If you want to ask for a point
  estimate, you may do so, but keep in mind that actual points can differ
  from estimated points.
* Unlike in previous team projects, where your Issues list and 
  Kanban board may have been
  pre-populated with issues by the staff,
  in the legacy code phase, populating the Kanban board
  is the responsibility of the team.  More on that below.
* The aim of the team is to earn 100 points before the deadline.  This forms the 
  most important part of you project grade, which is 25% of your course grade.
* Another part of your project grade is your "CATME multiplier", which is a number
  based on your peer evaluations.  This number is typically 100 unless your team
  has rated you significantly below the team average
* Points beyond 100 can count as extra credit as explained below.

# Points beyond 100


If you accumulate more than 100 project points, the additional points may count as extra credit, at a rate of 1 extra credit point for each 10 points over 100 earned, up to a maximum project grade of 110.  For example:

| Points Earned | Project Grade |
|---------------|---------------|
|    80         |    80         |
|    90         |    90         |
|   100         |  100          |
|   105         |  100.5        |
|   110         |  101          |
|   115         |  101.5        |
|   150         |  105          |
|   180         |  108          |
|   ≥200        |  110          |

Your final project grade is maxed out at 110 total project points--any points in excess of 110 will not count towards your grade (though you'll probably learn a lot from having under taken the work to earn them.)


# Sprint Planning for Legacy Code project

Each team already has a Kanban board setup for the legacy code project (see links below).   However unlike in your team01, team02, and team03 projects, it's up to you to populate this yourself.

| 9am | 10am | 
|-----|-----|
| [f23-9am-1]({{page.f23_9am_1}}) | [f23-10am-1]({{page.f23_10am_1}}) | 
| [f23-9am-2]({{page.f23_9am_2}}) | [f23-10am-2]({{page.f23_10am_2}}) | 
| [f23-9am-3]({{page.f23_9am_3}}) | [f23-10am-3]({{page.f23_10am_3}}) | 
|                         | [f23-10am-4]({{page.f23_10am_4}}) | 


You should add the `In Review` column if it is not already present.

Then, you should populate your todo column with issues, start assigning them to your team, and start working.   I'll cover where these issues come from in a moment.

You may not get through all of the Sprint planning today, but by the end of discussion section on Wednesday:
* Each of the six team members should be assigned to an issue in the todo column
* The previous bullet point shoudl *remain true* until your team reaches 100 points

Teams accumulate points when PRs are merged into main
* That is only done by the course staff for these projects.
* Each PR requires at least one code review from a team member, and at least one code review from a staff member
* The staff estimate points. Most issues are 5 to 10 points.
  - 5 points for very straightforward issues addressing a single concern
  - 10 points for issues that require a bit more work, but are nevertheless reasonably straightforward application of skills from team01, team02, team03.
  - 20 points is rare, and is reserved for issues that may be more complex, and/or require students to go significantly beyond the skills from previous course assignments.
* Note that breaking down issues into smaller chunks works to your benefit in multiple ways:
  - Easy to code review and merge (fewer merge conflicts), so faster point accumulation
  - Three 10 points issues and three 5 points issues adds up to 45 points; combining all of those together might only get you 20.
  - But the aim here should not be to "game the points". It should be to "get the issues implemented", in incremental "right sized" pieces.
  - If you do that, the points will take care of themselves.  
  
Points belong to the whole team, not to individuals
* Work as a team, and help each other.
* We do want to see every team member contribute
* Ultimately, it's a team project and a team grade.
* Having said that, really low CATME scores might result in a grade reduction.
 
  
## Where do issues come from?

For issues, you'll need to do a bit more work that in the previous team projects.

Here is where you'll get issues from:
* The three starter code repos have issues lists (as shown in the table below).
* These have been copied to your repo
* These issues come in different sizes 
  - A handful of these may be small easy issues. 
  - However, many (most?) of these issue *may not translate one-to-one into issues for your Kanban board*.
  - Instead, you are encouraged to try to *break the larger ones down into smaller issues*, each of which could be a single PR; more on this below.
  - This Sprint Planning meeting is where you can do some of that.
  - You may even need to add "issues about issues", e.g. an issue that says: "break issue #34 from proj-happycows into multiple issues on our team's repo".  Such an issue doesn't result in a PR, but it can still be moved across the Kanban board from `To Do`, to `In Progress`, to `In Review`, to `Done`.
* Your team's own ideas for features, based on the notes your team took last Wednesday during meetings with
  - Mike Fogelsanger for proj-gauchoride
  - Prof. Mattanjah deVries for proj-happycows
  <!-- - Prof. Phill Conrad for proj-courses -->

## Existing issues

Staff may add to these issues over the course of the project; when we do, we'll post an announcement in the project slack channels.

| Project |  Starter Code Repo | Issues Link | Project Slack Channel |
|---------|--------------------|-------------|-----------------------|
| proj-gauchoride | [Starter Code Repo](https://github.com/ucsb-cs156/proj-gauchoride) | [Issues](https://github.com/ucsb-cs156/proj-gauchoride/issues) | [`#proj-gauchoride`]({{page.proj_gauchoride_slack_url}}) |
| proj-happycows | [Starter Code Repo](https://github.com/ucsb-cs156/proj-happycows) | [Issues](https://github.com/ucsb-cs156/proj-happycows/issues) | [`#proj-happycows`](https://ucsb-cs156-s23.slack.com/archives/C058QUC16QP) |
<!-- | proj-courses | [Starter Code Repo](https://github.com/ucsb-cs156/proj-courses) | [Issues](https://github.com/ucsb-cs156/proj-courses/issues) |  [`#proj-courses`](https://ucsb-cs156-s23.slack.com/archives/C058BPFQZ42) | -->

## You are encouraged to keep each PR small.

For example, implementing a new feature may require
* A new React Component (with tests and storybook entries, and perhaps fixtures to support those)
* A new React Page
  - This page might start out with a simple PR that establishes a placeholder with text "New feature coming soon", and a trivial set of tests and a storybook entry
  - It might later get data from the backend and display it using a component, and be linked to from the navigation bar.
* A new database table (or a new column in an existing database table, requiring modifications to an `@Entity` and/or `@Repository` class
* New API backend endpoints, which require controller methods and tests.

Each of these could (and arguably should be) a separate PR!  This helps to keep PRs small, which makes code review easier, and also helps the team to divide up work among the team members.

Still, you may need to document in the issues what the dependencies are (e.g. "do issue 12 and 13 before starting 14").

# Legacy Code Background information

For each of the teams, there is already:
* A repo, seeded with the starter code from previous quarters
* A prod and qa dokku instance
* A Kanban board

For each, I've set up Google OAuth client id and client secret.
<!-- I've also set up the `UCSB_API_KEY` and `MONGODB_URI` for the `courses` project.   -->
You are welcome to use `dokku config:show app-name` to get these values and use them for your localhost setup.

Links are provided below.

# Links


## 9am - gauchoride

* Customers: Mike Fogelsonger (Director of Veterans and Military Services) and Student Health (who will be taking over the application.)  Drivers, and Riders of the service.

| Team | Repo | Github Pages | Prod | QA |
|--|--|--|--|--|
| f23-9am-1 | [repo](https://github.com/ucsb-cs156-s23/proj-gauchoride-f23-9am-1) | [pages](https://ucsb-cs156-s23.github.io/proj-gauchoride-f23-9am-1/) | [prod](https://proj-gauchoride.dokku-01.cs.ucsb.edu) | [qa](https://proj-gauchoride-qa.dokku-01.cs.ucsb.edu)
| f23-9am-2 | [repo](https://github.com/ucsb-cs156-s23/proj-gauchoride-f23-9am-2) | [pages](https://ucsb-cs156-s23.github.io/proj-gauchoride-f23-9am-2/) | [prod](https://proj-gauchoride.dokku-02.cs.ucsb.edu) | [qa](https://proj-gauchoride-qa.dokku-02.cs.ucsb.edu)
| f23-9am-3 | [repo](https://github.com/ucsb-cs156-s23/proj-gauchoride-f23-9am-3) | [pages](https://ucsb-cs156-s23.github.io/proj-gauchoride-f23-9am-3/) | [prod](https://proj-gauchoride.dokku-03.cs.ucsb.edu) | [qa](https://proj-gauchoride-qa.dokku-03.cs.ucsb.edu)
| f23-9am-4 | [repo](https://github.com/ucsb-cs156-s23/proj-gauchoride-f23-9am-4) | [pages](https://ucsb-cs156-s23.github.io/proj-gauchoride-f23-9am-4/) | [prod](https://proj-gauchoride.dokku-04.cs.ucsb.edu) | [qa](https://proj-gauchoride-qa.dokku-04.cs.ucsb.edu)

 
## 10am - happycows

* Customer: Prof. Mattanjah de Vries, Distinguished Prof. of Chemistry, UCSB, and students in his classes.

| Team | Repo | Github Pages | Prod | QA |
|--|--|--|--|--|
| f23-10am-1 | [repo](https://github.com/ucsb-cs156-s23/proj-happycows-f23-10am-1) | [pages](https://ucsb-cs156-s23.github.io/proj-happycows-f23-10am-1/) | [prod](https://proj-happycows.dokku-04.cs.ucsb.edu) | [qa](https://proj-happycows-qa.dokku-04.cs.ucsb.edu) |
| f23-10am-2 | [repo](https://github.com/ucsb-cs156-s23/proj-happycows-f23-10am-2) | [pages](https://ucsb-cs156-s23.github.io/proj-happycows-f23-10am-2/) |[prod](https://proj-happycows.dokku-05.cs.ucsb.edu) | [qa](https://proj-happycows-qa.dokku-05.cs.ucsb.edu) |
| f23-10am-3 | [repo](https://github.com/ucsb-cs156-s23/proj-happycows-f23-10am-3) | [pages](https://ucsb-cs156-s23.github.io/proj-happycows-f23-10am-3/) |[prod](https://proj-happycows.dokku-06.cs.ucsb.edu) | [qa](https://proj-happycows-qa.dokku-06.cs.ucsb.edu) |
| f23-10am-4 | [repo](https://github.com/ucsb-cs156-s23/proj-happycows-f23-10am-4) | [pages](https://ucsb-cs156-s23.github.io/proj-happycows-f23-10am-4/) |[prod](https://proj-happycows.dokku-07.cs.ucsb.edu) | [qa](https://proj-happycows-qa.dokku-07.cs.ucsb.edu) |
 
<!-- ## 7pm - courses

* Customer: All UCSB Students, Faculty, Staff and Admins
* Central issues collection: <https://github.com/ucsb-cs156/proj-courses/issues>
  - You can get issues from here to add to your own kanban boards

| Team | Repo | Github Pages | Prod | QA |
|--|--|--|--|--|
| s23-7pm-1 | [repo](https://github.com/ucsb-cs156-s23/proj-courses-s23-7pm-1) | [pages](https://ucsb-cs156-s23.github.io/proj-courses-s23-7pm-1/) | [prod](https://proj-courses.dokku-09.cs.ucsb.edu) | [qa](https://proj-courses-qa.dokku-09.cs.ucsb.edu) |
| s23-7pm-2 | [repo](https://github.com/ucsb-cs156-s23/proj-courses-s23-7pm-2) | [pages](https://ucsb-cs156-s23.github.io/proj-courses-s23-7pm-2/) | [prod](https://proj-courses.dokku-10.cs.ucsb.edu) | [qa](https://proj-courses-qa.dokku-10.cs.ucsb.edu) |
| s23-7pm-3 | [repo](https://github.com/ucsb-cs156-s23/proj-courses-s23-7pm-3) | [pages](https://ucsb-cs156-s23.github.io/proj-courses-s23-7pm-3/) | [prod](https://proj-courses.dokku-11.cs.ucsb.edu) | [qa](https://proj-courses-qa.dokku-11.cs.ucsb.edu) |
| s23-7pm-4 | [repo](https://github.com/ucsb-cs156-s23/proj-courses-s23-7pm-4) | [pages](https://ucsb-cs156-s23.github.io/proj-courses-s23-7pm-4/) | [prod](https://proj-courses.dokku-12.cs.ucsb.edu) | [qa](https://proj-courses-qa.dokku-12.cs.ucsb.edu) |
  -->
