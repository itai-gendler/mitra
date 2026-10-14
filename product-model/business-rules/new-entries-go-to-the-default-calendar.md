---
appliesTo:
- type: capability
  id: create-entry
- type: capability
  id: add-availability
references:
- kind: code
  role: implementation
  target: src/features/sources/client/Calendars.ts#Calendars
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# New entries go to the default calendar

A new entry goes to the default calendar while it is showing and can hold the entry's kind; otherwise it goes to the first calendar showing that can. Moving a calendar to the top therefore also makes it the default when none is chosen.
