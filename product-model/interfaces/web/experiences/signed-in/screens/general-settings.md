---
entities:
- entity: device-settings
  shows: [Theme, Language]
  collects: [Theme, Language]
references:
- kind: code
  role: implementation
  target: src/features/settings/client/DialogSettings.ts
- kind: doc
  role: intent
  target: docs/settings.md
  title: Settings
---

# General settings

The theme and the language of the browser the user is on.
