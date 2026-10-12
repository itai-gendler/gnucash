---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "GnuCash continuation"
  },
  "steps": [
    {
      "text": "Choose Save before selecting a source destination.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user",
      "capability": "save-book"
    },
    {
      "text": "The Product invokes Save As for the unnamed Book; no source is persisted before that continuation.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Location"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user",
      "capability": "save-book"
    },
    {
      "text": "Choose Save As and a valid new destination.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user",
      "capability": "save-book-as"
    },
    {
      "text": "The Product establishes the selected destination as the Book’s writable source.",
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
      "actor": "user",
      "capability": "save-book-as"
    },
    {
      "text": "The Product persists the Book’s current accounting at that writable destination and clears unsaved changes.",
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
      "actor": "user",
      "capability": "save-book-as"
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

# Unnamed Book

## Trigger

Save invokes or offers Save As, and the user accepts the continuation and selects a valid writable destination.

## Outcome

The Book is persisted at the selected new destination.
