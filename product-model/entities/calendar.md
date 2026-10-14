---
domain: calendars
relations:
- entity: event
  verb: holds
  cardinality: one-to-many
- entity: task
  verb: holds
  cardinality: one-to-many
- entity: availability
  verb: holds
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/features/sources/Source.ts#Source
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# Calendar

One row of the sidebar's Calendars tab: a calendar stored in Mitra, or one of a connected account. It holds events, tasks or both, and availability wherever its provider takes part. Whether it is turned on decides whether Mitra syncs and stores it at all; hiding it only changes what the user sees.

## Information kept

- **Name** — the user's name for it, which syncing never overwrites
- **Provider name** — the name its provider gives it; a rename there renames it in Mitra
- **Color** — the color the user picked, else the provider's, else one Mitra derives from its address
- **Holds** — events, tasks or both, as its provider allows
- **Read-only** — whether its provider takes no changes from Mitra, as for a subscription or a calendar shared to view only
- **Hidden** — whether its entries are kept out of every view
- **Order** — its place within its integration

## States

### Turned off

Known to Mitra but neither synced nor stored. Calendars that appear in an account after it was connected arrive here.

### Importing

Turned on, with its entries still being imported for the first time or again.

### Imported

Turned on and fully imported; from here on it only syncs what changed.
