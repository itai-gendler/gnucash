---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Supply a new Price for an existing commodity/currency/day and accept Replace.",
      "kind": "actor",
      "entities": [
        {
          "entity": "price",
          "effect": "reads",
          "facts": [
            "Commodity",
            "Currency",
            "Date",
            "Value"
          ],
          "as": "previous-price"
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
      "text": "The Product removes the previous Price and retains the new Price when its source has equal or better precedence.",
      "kind": "product",
      "entities": [
        {
          "entity": "price",
          "effect": "removes",
          "as": "previous-price"
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
          ],
          "as": "new-price"
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

# Same-day replacement choice

## Trigger

Submit a price for a commodity/currency/day that already has a price and respond to replacement confirmation.

## Outcome

The accepted same-day replacement is retained under the selected inputs and applicable source precedence.

## Edge cases

- Cancel leaves the existing price unchanged.
- A better-precedence existing source can prevent the proposed price from being added.
