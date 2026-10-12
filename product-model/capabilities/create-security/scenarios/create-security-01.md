---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Supply a custom namespace, name, unique symbol, fraction and supported quote settings.",
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
      "text": "The Product creates the custom Security with the supplied identity and quote facts.",
      "kind": "product",
      "entities": [
        {
          "entity": "security",
          "effect": "creates",
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

# Custom Security

## Trigger

Supply a custom namespace, name, unique symbol, fraction and supported quote settings.

## Outcome

The Product creates the custom Security with the supplied identity and quote facts.
