---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/availability/client/commands.ts#CreateAvailability
- kind: doc
  role: intent
  target: docs/availability.md
  title: Availability
---

# Add availability

Add availability to the default calendar with Add Availability in the command palette: working hours from Monday to Friday, 9:00 to 17:00, when that calendar has none yet, otherwise a window on today's weekday. It is saved at once and its editor opens in the week view. Notion, Tempo and read-only calendars cannot hold availability.
