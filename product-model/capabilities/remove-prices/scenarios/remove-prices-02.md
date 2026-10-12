---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose old-price pruning and supply date, source and retention choices.",
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
      "text": "The Product removes Prices selected by date/source and the selected weekly, monthly, scaled or fiscal retention policy; unselected retained records remain.",
      "kind": "product",
      "entities": [
        {
          "entity": "price",
          "effect": "removes"
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

# Date/source/retention pruning

## Trigger

Choose old-price pruning and supply date, source and retention choices.

## Outcome

The Product removes Prices selected by date/source and the selected weekly, monthly, scaled or fiscal retention policy; unselected retained records remain.
