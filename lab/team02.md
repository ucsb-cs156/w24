---
description: Spring Boot OAuth and CRUD operations
assigned: 2023-04-20 15:00
due: 2023-05-05 23:59
layout: default
title: team02
ready: true
layout: default
parent: lab
course_org: https://github.com/ucsb-cs156-s23
course_org_name: ucsb-cs156-s23
starter_repo: https://github.com/ucsb-cs156-s23/STARTER-team02
starter_repo_ssh: git@github.com:ucsb-cs156-s23/STARTER-team02.git
course_software: https://ucsb-cs156.github.io/s23/info/software.html
canvas_url: TBD
sample_deployed_app: https://ucsb-cs156-s23.github.io/STARTER-team02
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

```
issue00_set_up_prod_deployment.md
issue01_set_up_qa_deployment copy.md
issue02_configure_github_pages.md
issue11_create_database_table.md
issue12_add_list_all_and_post_endpoints.md
issue13_add_get_for_single_item.md
issue14_add_put_for_single_item.md
issue15_add_delete_for_single_item.md
issue90_submitOnCanvas.md
```

These are the issues you need to create and put on your Kanban board, but there is a twist:

* The issues marked `issue11` through `issue15` need to be repeated for each of six database tables
* The database tables are: 
  - `Restaurant`
  - The three things you added in the team02 exercise
  - Two more tables that you come up with on your own (with at least three fields in each)

You can do this by hand, or you can use some automation to help:
* Copy the files `issue11` through `issue15` to files with other names e.g. `issue21` through `issue26` 
* Inside the files, do a search and replace on "Restaurant" to change it to "Hotel", for example
* Commit the files and then run workflow `90-create-issues`

This will put the issues in your collection.   It will not create duplicate issues with the same title;
the title is whatever is on the first line in the file.

## Working on the issues

Most of the issues have hints inside the issue text themselves, but there is some additional material below that may help.


## Big Picture: what is team02 all about?

From a high-level standpoint, you'll be resolving these 30 issues (6 db tables, 5 issues per database table = 30 issues)
* Adding six database tables 
* Setting up the RESTful API backend CRUD endpoints for all six of those tables
* Adding backend test coverage for all of that

For this assignment, we will work directly with the backend via Swagger.

In the next assignment, we'll start looking how how to link the frontend from team01 with the backend from team02.

# More details on team02

In this team project, our starter code has a  frontend and backend, however we are still focusing only on the backend part.  The front end provides only
a place for us to login with our Google account.

We are focusing on learning these new Spring Boot backend concepts:

* Creating SQL database tables using `@Entity` and `@Repository`
* Using the Lombok annotations: `@Data`, `@NoArgsConstructor`, `@Builder`, etc.
* Implementing controller routes for CRUD operations (Created, Read, Update, Destroy)
* Writing unit tests for controller CRUD operations, including the use of:
  - Spring `MockMvc`
  - Mockito methods for creating mocks of repositories and services (`when`, `verify)
  - the idea of "dependency injection"

In addition, we'll practice further with a few concepts that we touched on in `jpa03`, but may not have fully fleshed out:
- Set up of the documentation repos, the `-docs` and `-docs-qa` repos
- Working with feature branches, issues, a Kanban board, pull requests, and GitHub actions scripts
- Working with code coverage and mutation testing

## The starting code

Your starter code provides Spring Boot code with the ability to do CRUD operations on two database tables:

* UCSBDates
* UCSBDiningCommons

These tables are set up to match the data that is available through two public APIs that are provided by UCSB and documented at
<https://developer.ucsb.edu>.

The `UCSBDates` tables has three columns, and is intended to store data like that shown here:


The `UCSBDiningCommons` table has six columns, and is intended to store data like that shown here:


## Your task: add CRUD for additional database tables


You'll be adding CRUD operations for six additional database tables; one per team member:

On the Kanban board, you'll find five issues for each of these tables:

* Add database table (the `@Entity` and `@Repository` classes, no test classes)
* Add GET endpoint to list all database records, and a POST  endpoint to create new database records, plus tests (this, and all of the rest, are done in the Controller and Controller test classes)
* Add GET endpoint to get a single database row by its id. (plus tests)
* Add PUT endpoint to update a single database row by its id. (plus tests) 
* Add DELETE endpoint to delete a single database row by its id. (plus tests)

You should choose one of these database tables, and then assign yourself the five issues that pertain to that database table.

For all of these, we suggest using an *autogenerated `Long`* as the `@Id` field.  
   
### Two types of id values

Every database table has a *primary key* marked in a Spring Boot `@Entity` class with the annotation `@Id`.

This value must be unique in the database table; no two rows can have the same primary key.

There are two strategies for dealing with this requirement, though we suggest
suggest using option 1 below, an *autogenerated `Long`* as the `@Id` field for all of your examples,
unless you really want to try the alternative.

1. Autogenerated ids, which start at `1` and then increment automatically.   The `UCSBDate` entity in the starter code is an example.  The code looks liek this:

   ```
   @Id
   @GeneratedValue(strategy = GenerationType.IDENTITY)
   private long id;
   ```
   
   As an aside: you may wonder what happens when we run out of numbers.  Since these `id` numbers are typically stored in a 64-bit Java `Long`, the maximum number is: `9,223,372,036,854,775,807L`.   
   * If you stored 1 Million records per second, 24 hours a day, 7 days a week, it would take you [292 thousand years](https://www.google.com/search?q=9%2C223%2C372%2C036%2C854%2C775%2C807+%2F+1000000+%2F+60+%2F+60+%2F+24+%2F+365&rlz=1C5CHFA_enUS888US889&sxsrf=APq-WBtGUMS1ceirZg3u9OrjxeaktzoWaw%3A1643567397963&ei=Jdn2Yen0Oc3EkPIP3du9gA4&ved=0ahUKEwipm63Xjdr1AhVNIkQIHd1tD-AQ4dUDCA4&uact=5&oq=9%2C223%2C372%2C036%2C854%2C775%2C807+%2F+1000000+%2F+60+%2F+60+%2F+24+%2F+365&gs_lcp=Cgdnd3Mtd2l6EANKBAhBGAFKBAhGGABQ4w1Y9A9gxxZoAXAAeACAAZcBiAGYA5IBAzAuM5gBAKABAcABAQ&sclient=gws-wiz) to cycle through this many id numbers.  
   * That's also over 18,000 records for every square meter on the face of the planet earth.  Not sure what database table needs that many records.

   
2. Using a value already in the data that is inherently unique.  For example, we might use perm number as an id field for a table of students.

   The `UCSBDiningCommons` entity in the sample code shows an example, where the `code` field is guaranteed to be unique; no two dining commons
   will have the same `code` value:
   
   ```
   @Id
   private String code;
   ```
   
It is important to understand that when you set up an `@Repository` class, the types that you pass to `CRUDRepository` as shown below must match the type of the `@Entity` and the type of the `@Id` field, as in these examples:

1. `UCSBDateRepository` uses `CrudRepository<UCSBDate, Long>` because the `@Id` field of `UCSBDate` is a `Long`:

    ```
    @Repository
    public interface UCSBDateRepository extends CrudRepository<UCSBDate, Long> {
    ...
    ```
   
2. `UCSBDiningCommonsRepository` uses `CrudRepository<UCSBDate, String>` because the `@Id` field of `UCSBDiningCommons` is a `String`:

    ```
    @Repository
    public interface UCSBDiningCommonsRepository extends CrudRepository<UCSBDiningCommons, String> {
    ...
    ```
   
## What you'll do: Process

From a process standpoint, this project works the same as team01:

Here's how that will play out in detail:
1. To start, each of you should clone your team's `team02-teamname` repo, which should already have a Kanban board set up for it.
2. Then, divide up the six database tables among the team members.  I suggest that you do this on your team slack channel in a single post, and then "pin" that post to your channel.
   That post might look something like this:

   ```
   Adam:  Restaurants
   Brianna: Hotels
   Chris:  Movies
   Danny: Coffee Shops
   Erin: Energy Drinks
   Fay: Books
   ```
   
5. Now look on the Kanban board.  You should find that there are five issues on the Kanban board for your specific database table:   
   
   * create_database_table
   * add_list_all_and_post_endpoints
   * add get for single item
   * add put for single item
   * add delete for single item 

   You should find all of the stories for your database item, and assign them to yourself; but drag *only one* into the In Progress column (and if you are already assigned to one of the set up tasks, don't even drag that one yet!  
   
   Typically, you should be assigned to only one item at a time in the In Progress column.  The exception is if you drag an item to In Progress, make some progress on it, and then need to stop working on it for a while because you are blocked, or something else urgently needs your attention.  But that should be the exception, not the normal way of doing things.
   
6. Now work on your issues as you did in team01; dragging them to "In Review" once they are ready for code review, and to "Done" when they are merged.
7. Near the end of the project there are a few "clean up tasks" for your team.    Those are marked as such on the Kanban board.   One of the last of those is to submit on Gauchospace for your team to note that your team is ready for the work to be graded.


### Implement CRUD operations for a database table


To add an SQL database table in Spring Boot, you typically add two files:

* A Java class that is annotated with `@Entity`; each instance of this class represents a single row in the database table
* A Java class that is annotated with `@Repository`; each instance of this class represents a database table.

There is more information in the issues on the Kanban board to guide you through the rest of the process.

# More Hints

We may add more hints about working with the team02 code as we discover what
problems studnets run into.

In the meantime, use the `#help-team02` channel to ask questions.

# A note about open source

Note that this assignment is open source.

The repos are public *on purpose*.
* You are encouraged to consult with one another within and across teams where it helps
  your learning.
* That does not mean that you can cheat by just copying code from another team.
* You are *not* permitted to just look at another team's code, even though you "can".
* It does mean that you should try to solve the problems as best you can, but you may 
  consult with members of other teams as you work.  In that context, you may look at 
  other team's code.

This isn't hard.   You all *know* when you are are looking at other team's work to
try to learn, versus when you are just looking at it as a shortcut to learning.

I'm trusting you to do the right thing.   This is practice for when, later on, you are
all working on different assignments.

# Understanding how to create the `@Entity` class


For example of `@Entity` classes, consult these files in the starter code:

* [UCSBDate.java](https://github.com/ucsb-cs156-s22/STARTER-team02/blob/main/src/main/java/edu/ucsb/cs156/example/entities/UCSBDate.java)
* [UCSBDiningCommons.java](https://github.com/ucsb-cs156-s22/STARTER-team02/blob/main/src/main/java/edu/ucsb/cs156/example/entities/UCSBDiningCommons.java)


You'll see that these files have a particular structure, with these annotations:

UCSBDate.java:

```
@Data
@AllArgsConstructor
@NoArgsConstructor
@Builder
@Entity(name = "ucsbdates")
public class UCSBDate {
```

UCSBDiningCommons.java:

```
@Data
@AllArgsConstructor
@NoArgsConstructor
@Builder
@Entity(name = "ucsbdiningcommons")
public class UCSBDiningCommons {
```

What do these annotations do?

* `@Data` is an annotation from a package called [Lombok](https://projectlombok.org/).  Lombok automatically generates code for some of the tedious things
   that can be automated: getters, setters, `toString`, `hashCode` and `equals`.  It also implements a constructor for all "required arguments", though that one is not always very convenient to use if we have lots of fields.
* `@AllArgsConstructor` and `@NoArgsConstructor` are additional [Lombok](https://projectlombok.org/) annotations that define additional constructors for us.  The  `@NoArgsConstructor` is particularly important, since it's a requirement of many pieces of Java Software that classes implement a no-args constructor (it's part of what it means to be a *Java Bean*.)
* `@Builder` create a class and some methods that make it easy to build objects with a syntax like this:
  ```
  UCSBDiningCommons commons = UCSBDiningCommons.builder()
        .name("Carrillo")
        .code("carrillo")
        .hasSackMeal(false)
        .hasTakeOutMeal(false)
        .hasDiningCam(true)
        .latitude(34.409953)
        .longitude(-119.85277)
        .build();
  ```
* `@Entity(name = "ucsbdiningcommons")` is the annotation that says this will be a row in a database table; the parameter sets the name of the table.

With these annotations in place, it's a simple matter of defining private fields for each of the columns in the database table.


# Details: `@Repository` class

For the repository class, see the examples:

* [UCSBDateRepository](https://github.com/ucsb-cs156-s22/STARTER-team02/blob/main/src/main/java/edu/ucsb/cs156/example/repositories/UCSBDateRepository.java)
* [UCSBDiningCommonsRepository](https://github.com/ucsb-cs156-s22/STARTER-team02/blob/main/src/main/java/edu/ucsb/cs156/example/repositories/UCSBDiningCommonsRepository.java)


Note that these are both `interface` files and not classes.

Normally, if you  create an `interface`, you also need to create a  class that implements that interface.

However, Spring Boot will *automatically generate the code for you*.  

In addition, if you need certain kinds of queries, you can specify methods in your interface to implement those queries.

The rules for translating method naming conventions into 
generated code are complicated: we will not go over all of them in lecture, and you are not expected to memorize or learn them all, and
*you probably won't need that for this assignment* (though you may need to know it later in the course.)

In any case, if/when you do need to understand that, here is some documentation is here to help get you started: <https://docs.spring.io/spring-data/jdbc/docs/current/reference/html/#jdbc.query-methods>

# Details: Controller methods and tests

The examples for the Controller Methods are tests are in these files:

* Controllers:
  - [UCSBDatesController.java](https://github.com/ucsb-cs156-s22/STARTER-team02/blob/main/src/main/java/edu/ucsb/cs156/example/controllers/UCSBDatesController.java)
  - [UCSBDiningCommonsController.java](https://github.com/ucsb-cs156-s22/STARTER-team02/blob/main/src/main/java/edu/ucsb/cs156/example/controllers/UCSBDiningCommonsController.java)
* Controller Tests:
  - [UCSBDatesControllerTests.java](https://github.com/ucsb-cs156-s22/STARTER-team02/blob/main/src/test/java/edu/ucsb/cs156/example/controllers/UCSBDatesControllerTests.java)
  - [UCSBDiningCommonsControllerTests.java](https://github.com/ucsb-cs156-s22/STARTER-team02/blob/main/src/test/java/edu/ucsb/cs156/example/controllers/UCSBDiningCommonsControllerTests.java)

You should be able to find the code you need for each of the methods, and use it as a model to create the code for your database table.

If you need additional guidance, ask on the `#help-team02` channel, and we'll try to steer you in the right direction.



## Submission/Grading

* Grading for this assignment is manual; someone on your team will submit the url to the [Canvas link for {{page.title}}]({{page.canvas_url}}) when the team thinks the site is ready for grading.

# Appendix

This contains notes that were added (and shared on the course slack) after the assignment was published.

## Different remotes for `prod` and `qa

Here’s something that may not have been clear: when you are setting up your prod and qa instances of team02, you can define different remotes for them.   

Instead of calling them both `dokku`, you could call them `prod` and `qa`.   For example:

```
git remote add prod dokku@dokku-00.cs.ucsb.edu:team02-prod
git remote add qa dokku@dokku-00.cs.ucsb.edu:team02-qa
```

Then, you always push from the `main` branch to `prod`:

```
git checkout main
git pull origin main
git push dokku main
```

But on `qa`, you can push any branch including a feature branch you are working on, like this.

Suppose, for example, that you are about to opened a pull request for `Chris-HotelControllerGet`, which you've tested
on `localhost`, but you want to be sure that it works when you deploy to `dokku` before you make (or merge) a PR.

Here's how to deploy the `Chris-HotelControllerGet` branch on your `qa` site:

```
git checkout Chris-HotelControllerGet
git pull origin Chris-HotelControllerGet
git push dokku Chris-HotelControllerGet:main
```

The syntax `branchName:main` (e.g. in `git push dokku Chris-HotelControllerGet:main`) 
means 
* push **from** the local branch `branchName` 
* but on the remote end, push it **to** the `main` branch (which is the one that dokku deploys)
