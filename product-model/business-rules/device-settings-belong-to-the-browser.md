---
appliesTo:
- type: entity
  id: device-settings
  effect: changes
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: src/features/settings/client/SettingsStore.ts
- kind: doc
  role: intent
  target: docs/settings.md
  title: Settings
---

# Anyone using a browser changes its device settings

Theme, language, connector lines and notification permission are kept by the browser, not the account, so a phone and a laptop can differ.
