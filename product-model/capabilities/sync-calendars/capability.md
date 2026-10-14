---
availability:
- {place: 'web::signed-in'}
domain: calendars
references:
- kind: code
  role: implementation
  target: src/integrations/server/Synchronizer.ts
- kind: code
  role: implementation
  target: src/integrations/server/SyncPacer.ts#SyncPacer
- kind: code
  role: implementation
  target: src/integrations/caldav/server/CalDAVSyncEngine.ts
- kind: doc
  role: intent
  target: docs/integrations/README.md
  title: Integrations
---

# Sync calendars

Keep every turned-on calendar of a connected account in step with its provider, both ways, in the background. Mitra checks more often while someone has it open and backs off when nobody does: CalDAV and Apple every 10 seconds while open, Google, Notion and Tempo about once a minute, subscriptions every 15 minutes, and every account every 5 minutes while nobody has Mitra open. When the user opens Mitra, every account that is due syncs straight away. Mitra calendars have nothing to sync.
