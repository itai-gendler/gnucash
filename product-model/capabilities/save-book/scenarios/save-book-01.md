---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Save for the current named writable source.",
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
      "text": "The Product writes the Book’s current accounting, updates Saved contents and clears Unsaved changes on successful persistence.",
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

# Persist existing source

## Trigger

Choose Save for the current named writable source.

## Outcome

The Product writes the Book’s current accounting, updates Saved contents and clears Unsaved changes on successful persistence.
