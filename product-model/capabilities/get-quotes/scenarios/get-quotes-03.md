---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Get Quotes and receive both usable and failed commodity results.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::price-database"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product retains valid Prices and displays diagnostics for failed quote results; failure of some commodities does not discard every successful quote.",
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
            "Unsaved changes"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::price-database"
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

# Partial results in GnuCash

## Trigger

Choose Get Quotes and receive both usable and failed commodity results.

## Outcome

The Product retains valid Prices and reports failed quote results; failure of some commodities does not discard every successful quote.
