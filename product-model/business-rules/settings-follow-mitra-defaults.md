---
appliesTo:
- type: capability
  id: change-general-settings
- type: capability
  id: change-calendar-settings
- type: capability
  id: change-entries-settings
- type: capability
  id: change-notifications-settings
references:
- kind: code
  role: implementation
  target: src/features/settings/client/Setting.ts
- kind: doc
  role: intent
  target: docs/settings.md
  title: Settings
---

# A setting left alone follows Mitra's default

Only the settings a user changed are kept, so an improved default in a later version reaches everyone who left it alone; choosing the default value counts as leaving it alone.
