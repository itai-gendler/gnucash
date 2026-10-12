---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash CLI"
  },
  "steps": [
    {
      "text": "Request quotes and receive a mixture of valid and failed results.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-cli"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product loads the Book and establishes its normal writable source session.",
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
          "place": "gnucash-cli"
        }
      },
      "actor": "user"
    },
    {
      "text": "The loaded Book source remains writable and saving succeeds.",
      "kind": "condition",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Session access"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-cli"
        }
      }
    },
    {
      "text": "The Product retains valid Prices, displays diagnostics for partial quote errors, and attempts Book saving. When source saving succeeds, the current accounting contents are persisted and unsaved changes are cleared; the partial-failure path returns status 2.",
      "kind": "product",
      "entities": [
        {
          "entity": "price",
          "effect": "creates",
          "facts": [
            "Commodity",
            "Currency",
            "Date",
            "Source",
            "Type",
            "Value"
          ]
        },
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

# Partial results in GnuCash CLI

## Trigger

Request quotes and receive a mixture of valid and failed results. The loaded source remains writable and its save succeeds.

## Outcome

The Product retains valid Prices, reports partial quote errors, and still attempts Book saving; the partial-failure path can return status 2.
