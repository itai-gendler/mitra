---
appliesTo:
- type: capability
  id: move-calendar-entries
- type: capability
  id: copy-calendar-entries
references:
- kind: code
  role: implementation
  target: src/features/migration/server/SourceMigration.ts
---

# Entries leave a read-only calendar only as copies

A read-only calendar can be copied from but not moved out of, and nothing can be moved into it.
