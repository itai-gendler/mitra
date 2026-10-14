---
actors:
- user
references:
- kind: code
  role: implementation
  target: src/features/availability/client/commands.ts#CreateAvailability
- kind: doc
  role: intent
  target: docs/availability.md
  title: Availability
---

# Set up working hours

## Goal

Shade the user's usual working week behind their events and tasks.

## Success criterion

The week view shows availability at the hours the user actually works.
