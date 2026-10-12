---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Open Price Database and inspect commodity/currency/date records.",
      "kind": "actor",
      "entities": [
        {
          "entity": "price",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::price-database"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product presents retained Price Commodity, Currency, Date, Source, Type and Value.",
      "kind": "product",
      "entities": [
        {
          "entity": "price",
          "effect": "reads",
          "facts": [
            "Commodity",
            "Currency",
            "Date",
            "Source",
            "Type",
            "Value"
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
      "target": "gnucash/gnome/dialog-price-edit-db.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-price-editor.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gnc-pricedb.cpp"
    }
  ]
}
---

# Price records

## Trigger

Open Price Database and inspect commodity/currency/date records.

## Outcome

The Product presents retained Price Commodity, Currency, Date, Source, Type and Value.
