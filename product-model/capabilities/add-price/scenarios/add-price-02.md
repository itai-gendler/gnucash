---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit no commodity/currency or an invalid value expression.",
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
      "text": "The Product requests corrected Price inputs and does not accept the invalid record.",
      "kind": "product",
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

# Missing commodity/currency or invalid value

## Trigger

Submit no commodity/currency or an invalid value expression.

## Outcome

The Product requests corrected Price inputs and does not accept the invalid record.
