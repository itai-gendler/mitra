---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/settings/client/DialogSettings.ts
- kind: code
  role: implementation
  target: src/app/settings.ts
- kind: doc
  role: intent
  target: docs/settings.md
  title: Settings
- kind: code
  role: implementation
  target: src/features/entries/client/HideDoneTasksSetting.ts
- kind: code
  role: implementation
  target: src/features/availability/client/HideAvailabilitySetting.ts
---

# Change calendar settings

Choose under Settings → Calendar the view Mitra opens on, whether done tasks and availability are hidden, and the connector lines of each view. The default view and the hiding follow the user to every device; the connector lines belong to the device.
