---
relations:
- entity: participant
  verb: invites
  cardinality: one-to-many
- entity: subtask-link
  verb: is a subtask through
  cardinality: one-to-many
- entity: dependency
  verb: waits through
  cardinality: one-to-many
- entity: dependency
  verb: is awaited through
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: code
  role: implementation
  target: src/features/entries/EntryType.ts
- kind: doc
  role: intent
  target: docs/entries.md
  title: Entries
---

# Event

An entry that takes place at a time: a meeting, a trip, a holiday, or a worklog booked in Tempo. It always has a start.

## Information kept

- **Title** — the large line under the editor header
- **Calendar** — the calendar it lives in
- **Description** — Markdown text, with headings, lists, links, callouts and tables
- **Location** — a place, typed freely or picked from suggestions, or a single meeting link
- **Color** — its own color, or none to wear its calendar's
- **Start** — when it begins
- **End** — when it ends
- **All day** — whether it covers whole days rather than times
- **Time zone** — the zone its times are written in, a wall clock with no zone, or none for an all-day entry
- **Repeat** — its repeat rule, with the occurrences deleted from the series and the occurrences changed on their own
- **Busy or free** — Busy, the default, marks the time as taken for anyone checking when the user is free; Free shows it without blocking the time
- **Visibility** — Default, Public, Private or Confidential: what people the calendar is shared with may learn of it, saved with the entry for the server and other apps to apply
- **Reminders** — when, before its start, the user is reminded
- **Organized by someone else** — whether its organizer is an address that is not one of the user's own at the calendar's provider
- **Links** — the links its description and location hold, read from them and never kept apart
