---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Change a custom security’s supported identity or quote settings and save.",
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
      "text": "The Product retains the Security Name, Namespace, Symbol, Identifier, Fraction, User symbol, Quote enabled, Quote source and Quote timezone changes.",
      "kind": "product",
      "entities": [
        {
          "entity": "security",
          "effect": "changes",
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

# Security/quote facts

## Trigger

Change a custom security’s supported identity or quote settings and save.

## Outcome

The Product retains the Security Name, Namespace, Symbol, Identifier, Fraction, User symbol, Quote enabled, Quote source and Quote timezone changes.
