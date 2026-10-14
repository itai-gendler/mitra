---
references:
- kind: code
  role: implementation
  target: src/features/availability/client/Availability.ts
- kind: code
  role: implementation
  target: src/features/entries/EntryType.ts
- kind: doc
  role: intent
  target: docs/availability.md
  title: Availability
---

# Availability

Time the user sets aside on a regular basis, such as working hours, shaded behind events and tasks in the week view in its calendar's color. It always repeats, belongs to one calendar, and is kept by Mitra; only busy availability is written to the calendar's provider, as busy events.

## Information kept

- **Name** — an optional label that runs along the day's edge
- **Calendar** — the calendar it belongs to
- **Place** — an optional place, shown with the name
- **Start** — when each window begins
- **End** — when each window ends
- **Time zone** — the zone its times are written in
- **Repeat** — its repeat rule, weekly to begin with
- **Busy or free** — Free, the default, keeps it inside Mitra; Busy also shows the time as taken to others
- **Visibility** — what the busy events written for it disclose to people the calendar is shared with
