---
availability:
- {place: 'web::signed-in'}
domain: views
references:
- kind: code
  role: implementation
  target: src/features/calendar/client/PageCalendar.ts
- kind: code
  role: implementation
  target: src/features/calendar/client/CalendarLocation.ts#CalendarLocation
- kind: code
  role: implementation
  target: src/features/entries/server/entries.ts#entriesRouter
- kind: doc
  role: intent
  target: docs/views/README.md
  title: Views
---

# Browse calendar

Look through the user's visible calendars in the week, month, year and timeline views: pick a view from the page header or with W, M, Y or L, step by the view's own period, return to today with T, jump to a date with G, scroll and zoom. Switching keeps the date being looked at, and the address holds the view, the date and the open entry.
