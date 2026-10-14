---
entities:
- entity: calendar
  shows: [Name, Color, Hidden, Read-only, Order]
  collects: [Name, Color]
- entity: integration
  shows: [Provider, Order]
- entity: user
  shows: [Name, Email, Default calendar, Previously visible calendars]
references:
- kind: code
  role: implementation
  target: src/app/Sidebar.ts
- kind: code
  role: implementation
  target: src/features/sources/client/Calendars.ts#Calendars
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# Calendars tab

The sidebar's list of the user's calendars under the heading of the integration each belongs to, with each calendar's color, eye and menu, and Add Integration at its foot.
