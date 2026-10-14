---
type: web
actors:
- user
- visitor
entryPoints:
- web: /week
references:
- kind: code
  role: implementation
  target: src/app/server.ts
- kind: code
  role: implementation
  target: src/features/calendar/client/PageCalendar.ts
- kind: doc
  role: intent
  target: docs/install-app.md
  title: Install the app
---

# Mitra web app

The app people open in a browser, or install from the browser as an app with its own window. It shows the user's calendars in five views, with a sidebar of calendars and planning, an entry editor, a command palette and settings. Installed on a computer, it also opens calendar files and subscription links.
