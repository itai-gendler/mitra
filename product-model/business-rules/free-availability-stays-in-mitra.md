---
appliesTo:
- type: entity
  id: availability
references:
- kind: code
  role: implementation
  target: src/integrations/Integration.ts#Integration
- kind: doc
  role: intent
  target: docs/integrations/caldav.md
  title: CalDAV
---

# Only busy availability is written to a provider

Availability is kept by Mitra. Free availability is never written to any account; busy availability in a CalDAV, Google or Apple calendar is written as repeating busy events with its name, or "Busy", its place and its visibility, kept in step with it, put back when changed elsewhere, and taken back when it turns free, is deleted, or its calendar is turned off or disconnected. Changes to a single day of it are not carried over.
