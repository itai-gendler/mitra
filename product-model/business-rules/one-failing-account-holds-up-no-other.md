---
appliesTo:
- type: capability
  id: sync-calendars
- type: entity
  id: integration
references:
- kind: code
  role: implementation
  target: src/integrations/server/SyncPacer.ts#SyncPacer
---

# One failing account holds up no other

When syncing an account fails, the others sync as usual and the failing one is tried again after at least a minute.
