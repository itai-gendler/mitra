---
domain: notifications
references:
- kind: code
  role: implementation
  target: src/features/reminders/NotificationSubscription.ts
- kind: doc
  role: intent
  target: docs/reminders.md
  title: Reminders
---

# Device

A browser or installed app where the user allowed notifications. Every device gets all of the user's reminders.

## Information kept

- **Name** — a name the user may give it
- **This device** — marks the device the user is looking from
- **Language** — the language its notifications are written in
- **Time zone** — the zone its notifications state times in
