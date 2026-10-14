---
kind: person
acts: external
relations:
- entity: integration
  verb: owns
  cardinality: one-to-many
- entity: device
  verb: owns
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/features/identity/User.ts#User
- kind: code
  role: implementation
  target: src/features/settings/UserSettings.ts
- kind: code
  role: implementation
  target: src/features/time/UserTimeZones.ts#UserTimeZones
- kind: doc
  role: intent
  target: docs/settings.md
  title: Settings
---

# User

A person with calendars on a Mitra server: the one person of a server without sign-in, or each person who signs in once sign-in is turned on. Nobody sees another user's calendars, entries or places.

## Information kept

- **Name** — the name the sign-in provider gives, updated at every sign-in
- **Email** — the email address the sign-in provider gives, updated at every sign-in
- **Home time zone** — the zone they belong to, first the zone of the first device they open Mitra on
- **Added time zones** — the other zones the week view shows beside theirs, each with an optional label of their own
- **Default calendar** — the calendar new entries go to unless they pick another
- **Default view** — the view Mitra opens on: Week unless they choose Month, Year, Timeline or Table
- **Hide done tasks** — whether done and cancelled tasks stay off the week, month and year views and the Planning tab
- **Hide availability** — whether availability stays off the week view
- **Default duration** — how long a new entry lasts when it is given no length, from 15 minutes to 2 hours, an hour unless changed
- **Snap to** — the step dragging and resizing land on: 5, 10, 15 or 30 minutes, 15 unless changed
- **Default event reminder** — the reminder new timed events start with, 30 minutes before unless changed or None
- **Default task reminder** — the reminder new timed tasks start with, at the time of the task unless changed or None
- **Previously visible calendars** — which calendars were showing before they chose to show only one
