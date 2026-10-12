---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Remove for an unused custom security and accept the associated-record confirmation.",
      "kind": "actor",
      "entities": [
        {
          "entity": "security",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::securities"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product removes the Security and dependent Prices selected by its associated-price removal path.",
      "kind": "product",
      "entities": [
        {
          "entity": "security",
          "effect": "removes"
        },
        {
          "entity": "price",
          "effect": "removes",
          "with": "security"
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
          "place": "gnucash-desktop::securities"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-commodities.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/dialog-commodity.cpp"
    }
  ]
}
---

# Remove Security and associated Prices

## Trigger

Choose Remove for an unreferenced custom security and confirm removal of any associated prices.

## Outcome

The Product removes the Security and dependent Prices selected by its associated-price removal path.
