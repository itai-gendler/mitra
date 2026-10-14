---
entities:
- entity: event
  shows: [Title, Calendar, Start, End, All day, Color, Repeat, Location, Busy or free]
- entity: task
  shows: [Title, Calendar, Start, End, All day, Color, Repeat, Due date, Progress, Overdue]
- entity: availability
  shows: [Name, Place, Start, End, Calendar]
- entity: calendar
  shows: [Name, Color]
- entity: subtask-link
  shows: [Subtask, Bigger task]
- entity: dependency
  shows: [Waiting entry, Entry to finish first, Broken]
- entity: user
  shows: [Home time zone, Added time zones, Default view]
  collects: [Added time zones]
entryPoints:
- web: /week
- web: /month
- web: /year
- web: /timeline
references:
- kind: code
  role: implementation
  target: src/features/calendar/client/PageCalendar.ts
- kind: code
  role: implementation
  target: src/features/calendar/client/Days.ts
- kind: code
  role: implementation
  target: src/features/calendar/client/Weeks.ts
- kind: code
  role: implementation
  target: src/features/calendar/client/Months.ts
- kind: code
  role: implementation
  target: src/features/calendar/client/Timeline.ts
- kind: doc
  role: intent
  target: docs/views/README.md
  title: Views
---

# Calendar views

The week, month, year and timeline views of the user's visible calendars, around one date. The week view also shades availability and shows the hours of the user's other time zones; the month and year views gather things done often into routines; the timeline shows open tasks that have a date, one per row.
