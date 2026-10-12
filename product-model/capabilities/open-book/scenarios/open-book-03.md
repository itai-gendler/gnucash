---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Open for a source whose lock is already present.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user"
    },
    {
      "text": "The selected source displays diagnostics for a lock. The choices do not promise exclusive isolation from another writer.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      }
    },
    {
      "text": "The Product offers the implemented lock choices: read-only access, break the lock, another source or cancellation; the chosen branch determines whether the Book opens.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Location",
            "Session access"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/gnc-file.c"
    }
  ]
}
---

# Locked-source choice

## Trigger

Choose Open for a source whose lock is already present.

## Outcome

The Product offers the implemented lock choices: read-only access, break the lock, another source or cancellation; the chosen branch determines whether the Book opens.
