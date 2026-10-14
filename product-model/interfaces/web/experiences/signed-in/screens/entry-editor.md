---
entities:
- entity: event
  shows: [Title, Calendar, Description, Location, Color, Start, End, All day, Time zone, Repeat, Busy or free, Visibility, Reminders, Links, Organized by someone else]
  collects: [Title, Calendar, Description, Location, Color, Start, End, All day, Time zone, Repeat, Busy or free, Visibility, Reminders]
- entity: task
  shows: [Title, Calendar, Description, Location, Color, Start, End, All day, Time zone, Repeat, Due date, Estimate, Progress, Visibility, Reminders, Links, Checklist, Organized by someone else]
  collects: [Title, Calendar, Description, Location, Color, Start, End, All day, Time zone, Repeat, Due date, Estimate, Progress, Visibility, Reminders]
- entity: availability
  shows: [Name, Calendar, Place, Start, End, Time zone, Repeat, Busy or free, Visibility]
  collects: [Name, Calendar, Place, Start, End, Time zone, Repeat, Busy or free, Visibility]
- entity: participant
  shows: [Email, Name, Role, Organizer, Reply]
  collects: [Email]
- entity: subtask-link
  shows: [Subtask, Bigger task]
- entity: dependency
  shows: [Waiting entry, Entry to finish first, Broken]
- entity: calendar
  shows: [Name, Color, Read-only]
references:
- kind: code
  role: implementation
  target: src/features/entries/client/EventDetails.ts
- kind: code
  role: implementation
  target: src/features/entries/client/EntryDetailsWhen.ts
- kind: doc
  role: intent
  target: docs/entries.md
  title: Entries
---

# Entry editor

One event, task or piece of availability with everything its calendar can hold: its color, calendar and type, its title and time, its time zone and repeat, and the rows below them. Rows the calendar cannot store are left out, and a read-only calendar shows everything as text. Every change is saved as it is made.
