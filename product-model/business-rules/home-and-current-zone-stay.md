---
appliesTo:
- type: capability
  id: remove-time-zone
- type: capability
  id: make-home-time-zone
references:
- kind: code
  role: implementation
  target: src/features/time/UserTimeZones.ts#UserTimeZones
- kind: doc
  role: intent
  target: docs/time-zones.md
  title: Time zones
---

# Home and the current zone always show in the week

The zone of the device anchors the week view and is never stored, so a trip changes nothing; home is set once from the first device and replaced only by making another zone home. Neither can be removed.
