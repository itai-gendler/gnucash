---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose New and resolve current unsaved changes.",
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
      "text": "The Product creates an empty current Book with a writable session and no source location.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "creates",
          "facts": [
            "Location",
            "Session access",
            "Unsaved changes",
            "Saved contents",
            "Transaction read-only period",
            "Transaction read-only cutoff",
            "Trading accounts",
            "Number source",
            "Default invoice report"
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
      "text": "With Show hierarchy on new book enabled in Application Preferences, the Product opens hierarchy setup for the new Book.",
      "kind": "product",
      "entities": [
        {
          "entity": "application-preferences",
          "effect": "reads",
          "facts": [
            "Show hierarchy on new book"
          ]
        },
        {
          "entity": "book",
          "effect": "reads",
          "facts": []
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

# Create empty current Book

## Trigger

Choose New and resolve current unsaved changes.

## Outcome

The Product creates an empty current Book with a writable session and no source location.
