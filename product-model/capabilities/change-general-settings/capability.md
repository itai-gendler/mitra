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
  target: src/infrastructure/i18n/LanguageSetting.ts
---

# Change general settings

Choose the theme and the language of the browser the user is on, under Settings → General, or from the command palette. The language applies at once without reloading, and its region decides how dates and times read, which day the week starts on and which days are the weekend; Persian lays Mitra out right to left.
