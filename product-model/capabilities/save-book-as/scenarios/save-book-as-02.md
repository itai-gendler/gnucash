---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Save As for an existing destination and accept replacement confirmation.",
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
      "text": "The destination already exists; selection does not imply overwrite acceptance.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      }
    },
    {
      "text": "The Product establishes the confirmed destination as the Book’s writable source.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "changes",
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
    },
    {
      "text": "The Product writes the Book’s current accounting over the accepted destination contents.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Saved contents",
            "Unsaved changes"
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

# Existing-destination choice

## Trigger

Choose Save As and a destination that already contains accounting.

## Outcome

The accepted destination contains the current accounting after successful saving.

## Edge cases

- Declining replacement confirmation leaves the destination untouched and does not complete saving.
