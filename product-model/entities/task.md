---
relations:
- entity: participant
  verb: invites
  cardinality: one-to-many
- entity: subtask-link
  verb: is a subtask through
  cardinality: one-to-many
- entity: subtask-link
  verb: gathers
  cardinality: one-to-many
- entity: dependency
  verb: waits through
  cardinality: one-to-many
- entity: dependency
  verb: is awaited through
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: code
  role: implementation
  target: src/features/entries/TaskStatus.ts#TaskStatus
- kind: doc
  role: intent
  target: docs/planning.md
  title: Planning
- kind: doc
  role: intent
  target: docs/subtasks.md
  title: Subtasks
---

# Task

An entry the user gets done and ticks off. A task's schedule, its start and end, says when they will work on it; its constraints, a due date and an estimate, say what the schedule has to respect. Neither is required: a task without a start is unscheduled and waits in the Planning tab.

## Information kept

- **Title** — the large line under the editor header
- **Calendar** — the calendar it lives in
- **Description** — Markdown text, with headings, lists, links, callouts and tables
- **Location** — a place, typed freely or picked from suggestions, or a single meeting link
- **Color** — its own color, or none to wear its calendar's
- **Start** — when it begins
- **End** — when it ends
- **All day** — whether it covers whole days rather than times
- **Time zone** — the zone its times are written in, a wall clock with no zone, or none for an all-day entry
- **Repeat** — its repeat rule, with the occurrences deleted from the series and the occurrences changed on their own
- **Due date** — when it has to be done: a day, or a day and time
- **Estimate** — how long it will take, kept only while it is unscheduled
- **Progress** — a percentage in steps of 5, set by hand while it has no subtasks and no checklist, else counted from them
- **Planning order** — its place in the Unscheduled list, kept by Mitra alone
- **Visibility** — Default, Public, Private or Confidential, as for an event
- **Reminders** — when, before its start, or before its due date while it is unscheduled, the user is reminded
- **Organized by someone else** — whether its organizer is an address that is not one of the user's own at the calendar's provider
- **Links** — the links its description and location hold, read from them and never kept apart
- **Checklist** — the lines of its description that start with a box, ticked or not
- **Overdue** — whether it is open, does not repeat, and its day, its due date or else the last day of its schedule, has passed

## States

### To Do

Open and not started. A new task starts here.

### Doing

Open and under way.

### Done

Finished: struck through, silent, and counted as complete by the bigger task.

### Cancelled

Dropped: struck through, silent, and left out of the bigger task's progress.
