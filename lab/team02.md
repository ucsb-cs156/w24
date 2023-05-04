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

# NOT READY YET
# NOT READY YET
# NOT READY YET
# NOT READY YET
# NOT READY YET
# NOT READY YET
# NOT READY YET


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

## Submission/Grading

* Grading for this assignment is manual; someone on your team will submit the url to the [Canvas link for {{page.title}}]({{page.canvas_url}}) when the team thinks the site is ready for grading.


