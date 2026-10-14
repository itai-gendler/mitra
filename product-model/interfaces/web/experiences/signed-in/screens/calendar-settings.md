---
entities:
- entity: user
  shows: [Default view, Hide done tasks, Hide availability]
  collects: [Default view, Hide done tasks, Hide availability]
- entity: device-settings
  shows: [Connector lines in the week view, Connector lines in the month view, Connector lines in the timeline]
  collects: [Connector lines in the week view, Connector lines in the month view, Connector lines in the timeline]
references:
- kind: code
  role: implementation
  target: src/features/settings/client/DialogSettings.ts
- kind: doc
  role: intent
  target: docs/settings.md
  title: Settings
---

# Calendar settings

How the views show things: the default view, hiding done tasks and availability, and the connector lines of each view.
