---
references:
- kind: code
  role: implementation
  target: src/app/ThemeSetting.ts
- kind: code
  role: implementation
  target: src/infrastructure/i18n/LanguageSetting.ts
- kind: code
  role: implementation
  target: src/features/relations/client/ConnectorLinesSetting.ts
- kind: doc
  role: intent
  target: docs/settings.md
  title: Settings
---

# Device settings

The settings that belong to the browser or app a user is on rather than to their account, so a phone and a laptop can differ.

## Information kept

- **Theme** — Match the system, Light or Dark
- **Language** — one of seven languages, each with the countries and areas it is written in, which decides how dates, times and weeks read
- **Connector lines in the week view** — whether lines join subtasks and dependencies in the week view
- **Connector lines in the month view** — whether lines join subtasks and dependencies in the month view
- **Connector lines in the timeline** — whether lines join subtasks and dependencies in the timeline
- **Reminder notifications** — whether this browser may alert the user: not asked yet, Allowed or Blocked
