---
actors:
- user
references:
- kind: code
  role: implementation
  target: src/features/sources/client/DialogSourceDeletion.ts#DialogSourceDeletion
---

# Empty a calendar before deleting it

## Goal

Keep a Mitra calendar's entries when the calendar itself is no longer wanted.

## Success criterion

The entries live in another calendar, and the old one is empty.
