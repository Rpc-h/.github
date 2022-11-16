# Development Process

The purpose of this process is to streamline the development of RPCh.

- [Development Process](#development-process)
  - [Legend](#legend)
    - [Project owners](#project-owner)
    - [Representatives](#representatives)
  - [Daily updates](#daily-updates)
    - [Start of work](#start-of-work)
      - [Text update](#text-update)
      - [Video call](#video-call)
    - [End of working day](#end-of-working-day)
    - [Absence](#absence)
  - [Sprints](#sprints)
    - [Task Grooming](#task-grooming)
      - [External issues](#external-issues)
    - [Sprint Retrospective](#sprint-retrospective)
    - [Epic Prioritization](#epic-prioritization)
    - [Sprint Planning](#sprint-planning)
    - [Fire alarm](#fire-alarm)
  - [Development](#development)
    - [Principles](#principles)
    - [Issue creation](#issue-creation)
    - [Labels](#labels)
    - [Rules](#rules)
    - [Workflow](#workflow)
      - [Daily Development](#daily-development)
      - [Releases](#releases)
    - [Branches](#branches)

## Legend

| Name            | Description                                                                                                |
| --------------- | ---------------------------------------------------------------------------------------------------------- | --- |
| Project Owner   | A HOPR member which ensures epics prioritized are in line with both the short and long term vision of RPCh |     |
| Representatives | Two RPCh members who act as the bridge between RPCh team and the rest of HOPR                              |     |
| Issue tracker   | The sole issue tracker is [GitHub](https://github.com/rpc-h)                                               |

### Project owners

Responsibilities:

- ensure long term vision of RPCh is in line with development

Members:

- Rik
- Sebastian

### Representatives

Responsibilities:

- to be the bridge between RPCh and the rest of HOPR

Members:

- [Steven](https://github.com/nionis)
- [Michal](https://github.com/mjadach-iv)

## Daily updates

### Start of work

#### Text update

For every working day, all tech members are required to write an update on what they will be working on throughout the day. Ideally, the list should be accompanied by github issues or PRs.

_Required:_ `True`

_When:_ Every working day, at start of work

_Where:_ In element channel `RPCh - daily & eod`

#### Video call

For every working, all tech members are required to join the video call with camera. The call is an opportunity for everybody to catch up, call out on things that are blocking them and any other unexpected issues.

_Required:_ `True`

_When:_ Every working day, time determined by google meet invite

_Where:_ Google meet

### End of working day

At the end of every working day, members write an update on what they have accomplished during the day.

_Required:_ `True`

_When:_ Every day, at end of work

_Where:_ In element channel `RPCh - daily & eod`

### Absence

Every Team Member is responsible for letting the rest of the team know about illness/absence/vacation.

- unexpected absence needs to be reported ASAP through email

## Sprints

Sprints are finite timeframes which have defined task priorities which the
team tries to adhere to as much as possible. Outside of emergency requests
the priorities stay the same within a sprint's timeframe.

_Length:_ 2 weeks

_Start:_ first day of the week, mostly Monday

The start and end of a sprint is defined by a set of activities in which
mostly the whole team is involved in:

1. Task Grooming
2. Sprint Retrospective
3. Epic Prioritization
4. Task Planning

### Task Grooming

On the last day of a sprint all tech members shall spend time cleaning up
tasks and PRs on Github. This includes but is not limited to:

- updating progress on tasks
- closing tasks which are actually done
- updating and/or closing PRs to ensure only in-progress PRs are active
- moving tasks on sprint boards to correct columns
- [responding to issues created by externals](#external-issues)
- delete stale/old branches which are not attached to a PR

_Who:_ all tech members individually

_When:_ last day of the sprint or before a vacation

### Sprint Retrospective

In `Retrospective` we aim to summarize the results of the last spring, in order to help us identify and fix issues in our processes and company culture.

For a `Retrospective` a moderator is chosen:

1. If [representatives](#representatives) are present, one of them are chosen.
2. Otherwise, one of the tech members must take on the role of the moderator.

The process is using [EasyRetro](https://easyretro.io/). `Retrospective` follows this schedule:

1. Everybody secretly adds hidden items (max 3) to `What Went Well` column.
2. The moderator reveals the `What Went Well` column.
3. Everybody has ~30 secs to speak about each of their items.
4. Everybody secretly adds hidden items (max 3) to `Problems` column.
5. The moderator reveals `Problems` column.
6. Everybody has ~30 secs to speak about each of their items.
7. Everybody is given 3 votes to vote on the items in the `Problems` category. Voting is hidden.
8. The moderator stops the voting and the most voted items bubble up.
9. The moderator takes 3 top items from the `Problems` category and creates an `Action Item` in the third column out of it with the help of the team. Each `Action Item`:

- defines `What` has to be done
- defines `When` it has to be completed
- defines `Who` is responsible for completing it
- moderator ensures that all action items are created as an issue

_Who:_ all tech members within a meeting

_When:_ last day of the sprint

### Epic Prioritization

The target of prioritization are issues marked as epic.
Priorities are captured on the [Sprint Planning project](https://github.com/orgs/Rpc-h/projects/4/views/1) which only contains epics.

- epics are issues which encapsulate the work that need to be done for X feature/bug
- epics are not bound by sprints and they can be long lived
- closed epics are moved to status `review`
- epics within `review` status are accepted by [Representatives](#representatives) prior to the meeting
  - unaccepted epics are moved back to next sprint with a comment explaining why it wasn't accepted
- ensure newly created [epics](#issue-creation) are well created
  - must use the `epic issue template`
- adapt epic priorities

### Sprint Planning

The task planning follows the `Prioritization` and takes the priorities into
account as much as possible.

- Tasks and PRs which are actively worked on are gathered on [Sprint Planning project](https://github.com/orgs/Rpc-h/projects/4/views/1).
- Epic issues are further refined into tasks which have clear definitions of work and done.
- Ideally each team member has only one task assigned which is in status `in progress`.
- members which are coming back from vacation should already have tasks assigned to them.

_Who:_ all tech members within a meeting

_When:_ first day of the sprint

### Fire alarm

It's possible that throughout the planned sprint, we encounter a bag of issues that need to be resolved ASAP.

1. As soon issue is detected, a [representative](#representatives) needs to take up the task of coordinating how the issue is tackled
2. Member appointed then is responsible for finding the right member within the tech team that has the most knowledge on the current issue, let's say that's Alice
3. Alice investigates issue and may ask other members for help
4. Alice patches issue

## Development

### Principles

- Context is the enemy. Be obvious, not clever.
- Simple is always better. Short, concise.
- Code for maintainability, not perfection.
- Automation-first. Whenever possible, rely on automation.
- Test early, test often. They prevent bad deployments and API regressions.
- All PRs must include the relevant tests required to ensure updated code works as expected.
- All PRs must include the documentation changes which will reflect the updated codebase.

### Rules

- All PR‘s **have to be approved** by at least one member.
- If CI pipeline breaks, you must open an issue for it and attempt to fix it.
- All PR‘s must pass all status checks/tests before merging.
- Releases can be merged back to `main`, but not always necessary.
- When in conflict, chat and engage with the team.
<!-- - When creating a PR, also update the changelog at `CHANGELOG.md` with a one-line high level summary and a reference to the PR or respective issue on Github. -->

### Workflow

#### Daily Development

```


   release/v0.1.0          main          jjpa/solves-channels-1556

         x                   │                       x
         x                   │                       x
         x                   │                       x
         x                   └──────────────────────►┐
         x                   x                       │
         x                   x                       │
         x                   x                       │
         x                   ◄───────────────────────┘
         x                   x                       x
         x                   x                       x
         x                   x                       x
         ◄────────────────────                       x
         x                   x                       x
         x                   x                       x
         x                   x                       x

```

1. A team-member or an external contributor writes code in a **feature branch**,
   or in their own fork. The feature branch describe its goal, and any issue it is
   related to, or whom it's working on it. (e.g. “jjperezaguinaga/fixes-341")

2. Soon after the creation of the branch, create a draft pull-request to
   stay up to date on progress. That way, every push will build the project and
   run the tests on every single push.

3. When the code is ready, mark the pull-request as ready to review, and request
   a code-review from a maintainer. In the case of members, the approval of an
   additional team member is required. Externals require **two** maintainers to
   approve the change.

4. After a different team member reviews the code and indicates approval, the PR
   can be merged. If the history is messy, the PR can be squashed, otherwise, it is
   merged. Use common sense to decide when you should do which one.

5. If a PR is deprioritised and has remained unmerged, the original author is responsible
   for frequenlty merging main into it so it does not diverge, if PR is no longer relevant
   it must be closed.

#### Releases

See [Release Process](./release.md)

### Branches

- `main`: In our case, `main` is a **prerelease** branch - tests _must_
  pass, and code _should_ be stable, but its _acceptable_ to have issues.

- `release/**`: On new internal release, we cut a `release/**`
  branch.
  See [Release Process](./release.md) for more info.
