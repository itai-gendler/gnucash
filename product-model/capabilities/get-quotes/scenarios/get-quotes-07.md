---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash CLI"
  },
  "steps": [
    {
      "text": "Request quote retrieval when book loading or saving fails.",
      "kind": "actor",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-cli"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product displays diagnostics for the Book backend/load/save error and returns failure for that book operation; a failed save does not prove successful Price persistence.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Location",
            "Saved contents"
          ]
        },
        {
          "entity": "price",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-cli"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/app-utils/gnc-quotes.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-price-edit-db.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnucash-commands.cpp"
    }
  ]
}
---

# Book load/save failure in GnuCash CLI

## Trigger

Request quote retrieval when book loading or saving fails.

## Outcome

The Product reports the Book backend/load/save error and returns failure for that book operation; a failed save does not prove successful Price persistence.
