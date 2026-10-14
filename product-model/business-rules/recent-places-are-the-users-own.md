---
appliesTo:
- type: capability
  id: edit-entry
- type: entity
  id: event
  effect: reads
  facts: [Location]
- type: entity
  id: task
  effect: reads
  facts: [Location]
references:
- kind: code
  role: implementation
  target: src/features/locations/server/recentLocations.ts
- kind: code
  role: implementation
  target: src/features/locations/server/locations.ts
- kind: doc
  role: intent
  target: docs/location.md
  title: Location
---

# Recent places come from the user's own calendars

The location field suggests places used recently in the user's own calendars only; nobody sees another user's places. Searches reach the geocoder through the Mitra server, never from the browser.
