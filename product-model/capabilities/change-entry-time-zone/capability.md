---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/entries/server/entries.ts#entriesRouter
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: code
  role: implementation
  target: src/features/entries/EntryTimeZone.ts
- kind: code
  role: implementation
  target: src/features/time/client/TimeZonePicker.ts
- kind: doc
  role: intent
  target: docs/time-zones.md
  title: Time zones
---

# Change entry time zone

Pick another time zone for an entry in the row with the globe. The entry keeps its clock times in the new zone. The list starts with the zones of the country the language is set for, marks home with a house and the current zone with a pin, and finds a zone by city, country, name or offset. Notion and Tempo calendars keep no zone of their own.
