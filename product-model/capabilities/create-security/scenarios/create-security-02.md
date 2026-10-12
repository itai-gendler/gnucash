---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit missing identity, a duplicate namespace/symbol pair or a reserved namespace/type.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::securities"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product requests corrected Security identity and does not accept the invalid custom record.",
      "kind": "product",
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

# Missing/duplicate/reserved identity

## Trigger

Submit missing identity, a duplicate namespace/symbol pair or a reserved namespace/type.

## Outcome

The Product requests corrected Security identity and does not accept the invalid custom record.
