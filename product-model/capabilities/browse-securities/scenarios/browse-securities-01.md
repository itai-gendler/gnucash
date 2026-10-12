---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Open Securities and inspect the selected namespace and identities.",
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
      "text": "The Product presents Security identity and retained quote settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "security",
          "effect": "reads",
          "facts": [
            "Name",
            "Namespace",
            "Symbol",
            "Identifier",
            "Fraction",
            "User symbol",
            "Quote enabled",
            "Quote source",
            "Quote timezone"
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

# Security identities

## Trigger

Open Securities and inspect the selected namespace and identities.

## Outcome

The Product presents Security identity and retained quote settings.
