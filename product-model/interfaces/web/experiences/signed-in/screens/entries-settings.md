---
entities:
- entity: user
  shows: [Default calendar, Default duration, Snap to]
  collects: [Default calendar, Default duration, Snap to]
references:
- kind: code
  role: implementation
  target: src/features/settings/client/DialogSettings.ts
- kind: doc
  role: intent
  target: docs/settings.md
  title: Settings
---

# Entries settings

How new entries start out: the default calendar, the default duration and the step dragging snaps to.
