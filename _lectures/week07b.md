---
title: "Week 07b - 08.10 Thu"
lecture_date: 2023-08-10
description: "team03, Retro3, release notes, legacy code onboarding"
ready: true
layout: default
parent: lectures
slides: 
---

# Outline for today, Thursday August 8th:

* I'll go over what we're doing today
* I'll also briefly discuss "Release Notes" (there was an example in your email.)
* And: if you haven't done CATME PeerEval2, this is your last chance; do it *during class today*.

# If you haven't submitted team03 on Canvas yet

* Please do a standup update, both in team slack channel, and out loud with your team.
* The deadline for team03 is midnight Monday 08/14, one week from today, STRICT.
* Everyone needs to be ready to start the legacy code project on Tuesday 08/15.

# If you have already submitted team03 on Canvas

* Post an update on #help-lecture-discussion so that the staff is aware
* Do Retro3 (click triangle below for instructions)
* Then you'll be onboarded to your legacy code project; either HappyCows or Gauchoride

<details markdown="1">
<summary>
Details of how to do Retro 3
</summary>

* Review how to do a retro: <https://ucsb-cs156.github.io/topics/agile/agile_retros.html>
* Then, go to your folder on Google Drive (the link should be pinned to your slack channel)
* Create a new document Retro3 similar to Retro1 and Retro2
* Conduct a retro following the same basic instructions from here:
  - <https://ucsb-cs156.github.io/m23/lectures/week05a/#retrospective-the-heart-of-agile>

Before deciding on a new experiment, **have a discussion of the experiment from your last retro**.
- Read the experiment from your Retro2 document.
- In your Retro3 document, make a section "Retro2 Experiment"
- Copy/paste the description of the experiment.
- Then, invite each member of the team to write something on the slack channel indicating whether they thought
  the experiment had a successful outcome, a failed outcome, an indeterminate outcome (can't tell) or a mix,
  and why.  But don't press enter until there's a signal that everyone is finished.
- Then you call all press enter and see what each other wrote.
- Discuss. If possible come to a consensus summary.  If a consensus doesn't emerge after a few minutes of discussion,
  then you can "agree to disagree".
- Write down either a summary of your consensus, or a summary of your differing opinions.

Then, come up with a new experiment for this Retro.  It can be a variation on the old one (i.e. a different approach to the same problem), or could be entirely different (some other aspect of the team's performance.)

</details>

# Legacy code project onboarding

Details coming soon

# Brief Discussion of "Release Notes"


The email below is a sample of what "Release Notes" looks like for a production application.  It's an email to Prof. Mattanjah deVries with an update on the latest new features for HappyCows.  Please take a moment to look it over.

In professional software development, these are typically a bit more formal--our setup is still a bit more informal, but the idea is the same: when there's a new release of the software into production, you want to inform your users about the main changes they will see.   This serves at least two purposes:

* **Functional**: These messages help them to be aware of, and use the new functionality.  Customers can't take advantage of new features if they don't know about them.

* **Marketing**: If you are running a software business, you are always concerned about "churn", which is the business term for when a paying customer stops paying you, and starts giving money to your competitor instead.   These messages need to convey to your customers that you have heard their concerns, and care about making their lives easier, more fun, less stressful—whatever the purpose of the app happens to be.
As we move into the legacy code phase of the course over the next few days, **your PR descriptions will be the source material** for these release notes for either HappyCows or Gauchoride, so it's important that they be written well.  This is why we ask for screenshots, etc. and that the PR descriptions include a description of new features not just from the programmer/developer perspective, but from the end-user perspective.

# Sample Release Notes

```
---------- Forwarded message ---------
From: Phill Conrad 
Date: Wed, Aug 9, 2023 at 9:28 AM
Subject: Happy Cows new release
To: Mattanjah de Vries 
```

Hi Mattanjah:

I've deployed the latest changes to the production version at https://happycows.dokku-00.cs.ucsb.edu/

Here's a summary of changes:

1. There is an instructor reports option on the admin menu.  To see an instructor report, select Instructor Reports from the admin menu, like this:

   <img width="300" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/55e65a78-245e-4c96-87f7-65c191771693">

   Then, you'll see a page like this one, which shows all available reports. (We'll cover how to generate a report in a moment; that's done on the jobs menu.  Later on, we can add a feature so that these are generated automatically on a schedule; right now, it's on demand.)

   <img width="800" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/8f90ef12-6db0-4316-9192-c2d72ff288a8">

   To see a specific report, click on the "View Report" button.

2. The page where an Admin can view a report looks like this. 

   <img width="1391" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/bc1e6004-d973-4dfc-a0f5-6c9796edbd9a">

   * There's a button to take you back to the list of reports.
   * At the top of the page is all of the information we have about the commons itself.
   * Under "Farmers" is a list of all of the farmers in the commons, and data on each one.

   There is also a "Download as CSV button" that will allow you to download the farmers
   part of the report as a CSV file that you can open in Excel, Google Sheets, or any other application that accepts CSV files.
   
   At the moment, only the farmer data is included in the CSV file.  If it would be useful to be able to  download the commons level data too, let us know; we could include it in the same file, or in a different one.
    
3. Manage Jobs page now has option to produce instructor reports.   To generate an instructor report, go to Manage Jobs
    
   <img width="500" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/06ca2cf5-e0f4-4e2c-8589-d23fb182c200">
 
   Then, select either `Instructor Report` (which produces a report for every commons), or
   `Instructor report for specific commons`:

   If you choose "Instructor Report for specific commons" it looks like this.  Select the commons for which you want a report, and click Submit:
   
   <img width="584" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/66d73290-a4f6-406a-86d0-ee7b61f6790b">
 
   Then watch under job status until the report is finished:
    
   <img width="800" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/0a9401f8-e28d-4a1a-8e3c-21a148a37ec1">
 
   Then, navigate to the page for instructor reports, as shown above.
    
4. There is also now the job that can set all cows in a commons to have the same health value, increasing or decreasing as you see fit.   It is accessed from Admin / Jobs

   <img width="300" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/daf276b0-5f97-4505-a721-63dd29dcdd5e">

   Then `Set Cow Health for a Specific Commons`

   <img width="400" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/0f227dd3-55d8-4dca-b828-513e1d570b79">

   Choose a commons and a new health value, and click `Set Cow Health`.

   <img width="400" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/560017c0-788d-4eca-80fb-b21b92fec217">

   Then monitor the job on the jobs page:

   <img width="800" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/9b43815d-a432-45d1-a986-404f15e223e4">

   When finished, the bottom of the output will look like this; the words `Cow Health has been set!` signify that the job is finished,
   as well as the word `Complete` on the status at the top

   <img width="250" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/63ba6a80-7494-4b91-8507-fac2b8bebef3">
   
   <img width="423" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/98002b3f-6dc1-48b7-999d-140acb48ae3c">
   
    
5. Finally, one change you may or may not have noticed, but it turns out to be important: the Admin Jobs page used to show the output from all jobs since the beginning of time.
    
  Since we've had over 1900 jobs since we launched this instance of the Happy Cows app, that page was starting to load very, very slowly, and be unusable, especially on slower machines.   We've reorganized this page so that it only loads the most recent 10 jobs, most recent first, and then there are "next" and "previous" buttons to be able to move forward and backwards if there is a need to see older jobs logs.
    
   <img width="243" alt="image" src="https://github.com/ucsb-cs156/m23/assets/1119017/c2a532ae-a176-4dbd-9db5-5428e2d3cafe">

That's what we have for this release.   Let us know what  new feature you'd like us to prioritize.
    
In a separate email, I'll send you a list of what we have on our list right now, but we always want to prioritize what you think is important for making the game better.

```    
Regards,
Phill
```

# PRs that went into the release notes above

For reference, as you look at the release notes above, here are the PRs that went into these.  

You may like to see how the PR descriptions were summarized into the release notes below.   As you look at this, you'll see that some PR titles/descriptions are better than others (I wrote pretty much all of them, so I'll be the first to acknowledge that some of them are pretty
good, and others are not so great.) 

A question to ponder: What is true about the titles/descriptions that are better, and what makes them better?

* [Jake create set cow health page on frontend for admin #50](https://github.com/ucsb-cs156/proj-happycows/pull/50)
* [Pc report service #57](https://github.com/ucsb-cs156/proj-happycows/pull/57)
* [Pc report jobs #58](https://github.com/ucsb-cs156/proj-happycows/pull/58)
* [Pc report controllers #59](https://github.com/ucsb-cs156/proj-happycows/pull/59)
* [pc - migrate from SpringFox to SpringDoc #60](https://github.com/ucsb-cs156/proj-happycows/pull/60)
* [pc - add ReportHeaderTable.js and storybook entry for it #61](https://github.com/ucsb-cs156/proj-happycows/pull/61)
* [Pc reports page #62](https://github.com/ucsb-cs156/proj-happycows/pull/62)
* [Pc report csv #63](https://github.com/ucsb-cs156/proj-happycows/pull/63)
* [pc - make the jobs page "paged", meaning show only 10 jobs at a time #64](https://github.com/ucsb-cs156/proj-happycows/pull/64)

