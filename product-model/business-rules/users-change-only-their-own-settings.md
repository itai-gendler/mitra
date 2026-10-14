---
appliesTo:
- type: entity
  id: user
  effect: changes
  facts: [Home time zone, Added time zones, Default calendar, Default view, Hide done tasks, Hide availability, Default duration, Snap to, Default event reminder, Default task reminder, Previously visible calendars]
permits:
- self: true
references:
- kind: code
  role: implementation
  target: src/features/identity/server/user.ts#userRouter
---

# A user changes only their own settings and time zones

Account settings, the default calendar and the time zones of the week view belong to the user and follow them to every device.
