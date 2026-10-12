---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Remove and decline the associated-record confirmation.",
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
      "text": "The Security and its retained Prices remain unchanged.",
      "kind": "product",
      "entities": [
        {
          "entity": "price",
          "effect": "reads",
          "facts": []
        },
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

# Decline removal

## Trigger

Choose Remove and decline the security or associated-price confirmation.

## Outcome

The Security and its retained Prices remain unchanged.
