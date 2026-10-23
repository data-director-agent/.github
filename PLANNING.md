# Planning and tracking work

This document describes how the Data Director project plans and tracks its work: what each GitHub
feature is used for, the two-week sprint cycle, and the rules that keep the board truthful. It
applies to every repository in the organisation. It is deliberately small: a handful of fields,
four meetings a month at most, and no estimates beyond a rough size.

Decisions about *what* the project does are governed by [GOVERNANCE.md](GOVERNANCE.md); this
document only covers how the agreed work is organised.

## Contents

- [The pieces and what each is for](#the-pieces-and-what-each-is-for)
- [The project board](#the-project-board)
- [Life of an issue](#life-of-an-issue)
- [The sprint cycle](#the-sprint-cycle)
- [Rules of thumb](#rules-of-thumb)
- [Setting up the board](#setting-up-the-board)

## The pieces and what each is for

Each GitHub feature answers one question. Do not use two features to say the same thing.

| Feature | Answers | Example |
| --- | --- | --- |
| **Issue** | What is one piece of work, and when is it finished? | "Inventory a project's files" |
| **Issue type** (Task, Bug, Feature) | What kind of work is it? | Feature |
| **Sub-issues** | What does a larger piece of work consist of? | An umbrella issue with its steps beneath it |
| **Labels** | Which part of the system, and which theme? | `area: harness`, `security` |
| **Milestone** | Which outcome does it contribute to, and by when? | "MVP foundations" |
| **Project field: Iteration** | Which two-week sprint is it planned for? | Sprint 1 |
| **Project field: Status** | Where is it right now? | In review |
| **Project field: Size** | Roughly how big is it? | M |
| **Project status update** | What is this sprint for, and how did it go? | The sprint goal, posted at planning |
| **Pull request** | What change delivers the issue? | Closes #198 |

Two distinctions matter most:

- **A milestone is an outcome; an iteration is a timebox.** A milestone such as "MVP foundations"
  describes a state of the system and may take one sprint or several. An iteration is simply the
  next two weeks. An issue usually has both.
- **Issue types carry the kind; labels carry the place.** Labels are `area: …` and themes only, as
  listed in each repository's contributor notes. Do not add labels such as `bug` or `enhancement`.

### Milestones

A milestone is a goal a person outside the team would recognise, written as a sentence that is
either true or false of the system. Give it a description that says how to tell it is done and a
due date that falls on the last day of a sprint. Keep two or three open at a time: the current
one, the next one, and at most one further ahead. Work that serves no milestone has no milestone.

A milestone is not a release. Releases are cut by release-please from the commit history and may
happen at any time.

### Umbrella issues

When a milestone needs more than three or four issues, open one umbrella issue (type Feature) that
states the outcome and its definition of done, and attach the steps as sub-issues. The umbrella
issue is closed when its last sub-issue closes and the outcome has been demonstrated.

## The project board

All work is tracked on one organisation-level project, **Data Director**
(<https://github.com/orgs/data-director-agent/projects/1>), which collects issues from every repository. Pull requests are not
added to the board separately: the issue is the unit of work, and a pull request links to it
with `Closes #n`.

### Fields

| Field | Values | Set by |
| --- | --- | --- |
| Status | Inbox, Backlog, Ready, In progress, In review, Done | Automation for Inbox and Done; people for the rest |
| Iteration | Two-week sprints, Monday to Friday of the following week | Sprint planning |
| Size | S (up to a day), M (a few days), L (more than half a sprint) | Whoever moves it to Ready |

Order the Backlog and Ready columns by dragging: the higher an item, the sooner it should be done.
There is no separate priority field.

### Status

| Status | Meaning |
| --- | --- |
| **Inbox** | New and not yet looked at. Every new issue lands here. |
| **Backlog** | Accepted as worth doing; not yet ready to start. |
| **Ready** | Meets the [definition of ready](#definition-of-ready); can be picked up. |
| **In progress** | Someone is assigned and working on it. |
| **In review** | A pull request is open and awaiting review. |
| **Done** | Closed. |

An issue that will not be done is closed as *not planned* with a sentence saying why, not left in
Backlog indefinitely.

### Views

| View | Layout | Filter | Use |
| --- | --- | --- | --- |
| Sprint | Board, columns by Status | `iteration:@current` | Daily work and the review |
| Planning | Table, grouped by Milestone, showing Iteration and Size | `status:Ready,Backlog` | Refinement and sprint planning |
| Inbox | Table | `status:Inbox` | Triage |
| Roadmap | Roadmap, by Iteration | `has:milestone` | Seeing milestones against sprints |
| My work | Table | `assignee:@me -status:Done` | Each person's own list |

The project's Insights hold one chart: a burn-up of the current iteration, counting items by
Status.

## Life of an issue

1. **Filed.** Anyone opens an issue, choosing a form (Bug, Feature or Task), which sets its type;
   an issue filed another way gets its type at triage. Automation adds it to the board with Status *Inbox*.
2. **Triaged** (weekly). A maintainer checks the type, adds `area: …` labels, a milestone if it serves one, a parent
   if it belongs under an umbrella, and moves it to *Backlog*; or closes it as a duplicate or not
   planned. A bug that blocks the current sprint goal goes straight into the current iteration.
3. **Refined.** Before planning, the issue is brought up to the definition of ready and moved to
   *Ready*.
4. **Planned.** At sprint planning it gets the next Iteration.
5. **Started.** Whoever picks it up assigns themselves and moves it to *In progress*.
6. **In review.** The pull request says `Closes #n`; its author moves the issue to *In review*.
7. **Done.** Merging the pull request closes the issue, and automation moves it to *Done*.

### Definition of ready

An issue is *Ready* when:

- it has a type, at least one `area: …` label and a Size;
- its body says what is to be true when it is finished, as acceptance criteria someone else could
  check;
- it is no larger than M, or has been split into sub-issues;
- any decision it depends on has been recorded, or a Task to record it (an ADR or an RFC) comes
  first and is Ready itself;
- nothing outside the project blocks it (otherwise it carries the `blocked` label and stays in
  Backlog).

### Definition of done

An issue is *Done* when:

- the change is merged to `main` with the required checks passing and a maintainer's approval;
- the acceptance criteria are met, and were shown at the sprint review if the change is visible;
- documentation, ADRs and registers that describe the change were updated in the same pull
  request;
- follow-up work that was found along the way is filed as new issues, not left in comments.

## The sprint cycle

Sprints last two weeks, from Monday to the Friday of the following week. Sprint 1 runs from
Monday 26 October to Friday 6 November 2026. (TODO: confirm the start date.)

| When | Event | Length | Output |
| --- | --- | --- | --- |
| Monday, week 1 | Sprint planning | 45 minutes | A sprint goal and the issues in the iteration |
| Weekly, any day | Triage | 15 minutes | An empty Inbox |
| Twice a week | Check-in, written or spoken | 5 minutes each | Blockers raised early |
| Tuesday, week 2 | Refinement | 30 minutes | Enough Ready issues for the next sprint |
| Friday, week 2 | Review and retrospective | 45 minutes | A demonstration, a status update and one or two actions |

TODO: decide which check-ins are spoken and which are written, and where written ones go.

### Sprint planning

1. Look at the open milestones. Choose one sentence that would make the sprint worthwhile: the
   **sprint goal**. It normally advances the current milestone.
2. From the top of Ready, set the next Iteration on the issues that serve the goal. Stop when the
   people available could plausibly finish them, allowing a fifth of the time for reviews, bugs
   and interruptions. Count Sizes as a sanity check only; there is no velocity target.
3. Post a **project status update** (on the board, *Add status update*) with the sprint goal, the
   dates and anything known to put it at risk. Set it to *On track*.

### During the sprint

- Each person has at most two issues *In progress* at once. Finish or hand over before starting a
  third.
- Reviews come before new work: an issue *In review* blocks someone else.
- New work found mid-sprint goes to the Inbox. It enters the current iteration only if it blocks
  the sprint goal, and then something of similar size leaves.
- If the goal becomes unreachable, post a status update set to *At risk* or *Off track* saying
  why, and agree in the next check-in what to drop.

### Review and retrospective

1. **Review.** Walk the Sprint view. Demonstrate what was finished against the goal.
2. **Unfinished work.** For each issue not Done, decide explicitly: move it to the next iteration,
   or clear the iteration and return it to Backlog. Nothing rolls over by default.
3. **Retrospective.** Ask what helped and what got in the way. Agree at most two actions and file
   each as a Task for the next sprint.
4. **Status update.** Post a final status update: whether the goal was met, what moved, and the
   actions. Set it to *Complete* if the goal was met, otherwise to *Off track*.

## Rules of thumb

- **Spikes** are Tasks with a timebox in the title ("Spike (2 days): …"). Their output is a written
  note or an ADR, not production code.
- **Decisions before code.** Where work depends on a fixed format or the Blueprint, the ADR or RFC
  is its own Task, planned in the same or an earlier sprint.
- **Large features** are umbrella issues with sub-issues, not long checklists in one issue body.
- **Draft pull requests** are for showing work early. Mark them ready for review when they meet
  the definition of done.
- **Stale issues** are reviewed when triage has spare time: an issue in Backlog untouched for three
  months is either refreshed or closed as not planned.

## Setting up the board

These steps create the project described above. Most can be done only in the web interface.

1. Create an organisation project named **Data Director** from the blank *Board* template, and
   link the repositories `data-director`, `classmark` and `.github` to it.
2. Edit the **Status** field to have the options Inbox, Backlog, Ready, In progress, In review and
   Done, in that order.
3. Add an **Iteration** field: duration two weeks, starting Monday 26 October 2026. Rename the
   iterations Sprint 1, Sprint 2 and so on.
4. Add a **Size** single-select field with the options S, M and L.
5. Under *Workflows*, enable:
   - *Auto-add to project* for each repository, filter `is:issue`;
   - *Item added to project*: set Status to Inbox;
   - *Item closed*: set Status to Done;
   - *Pull request merged*: set Status to Done;
   - *Item reopened*: set Status to Backlog.
6. Create the views listed under [Views](#views) and the burn-up chart under Insights.
7. Add the existing open issues (`gh project item-add`), then triage them as a one-off exercise.
8. Write the project README, linking to this document.
