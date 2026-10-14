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
  target: src/features/identity/server/user.ts#userRouter
- kind: code
  role: implementation
  target: src/features/sources/client/DefaultSourceSetting.ts
---

# Change entries settings

Choose under Settings → Entries how new entries start out: the default calendar, the default duration and the step dragging and resizing land on. The default calendar is the same choice as the filled icon in the sidebar. These follow the user to every device.
