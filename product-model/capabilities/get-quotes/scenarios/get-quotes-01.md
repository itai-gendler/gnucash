---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Get Quotes with Finance::Quote available and configured quoted commodities.",
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
      "text": "The Product retains valid dated Prices with currency/value/source from successful quote results.",
      "kind": "product",
      "entities": [
        {
          "entity": "security",
          "effect": "reads",
          "facts": [
            "Quote enabled",
            "Quote source",
            "Quote timezone"
          ]
        },
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

# Retrieve Prices in GnuCash

## Trigger

Choose Get Quotes with Finance::Quote available and configured quoted commodities.

## Outcome

The Product retains valid dated Prices with currency/value/source from successful quote results.
