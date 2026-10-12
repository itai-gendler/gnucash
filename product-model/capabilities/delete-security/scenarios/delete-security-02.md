---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Remove for a custom security whose identity remains in use.",
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
      "text": "The Product displays diagnostics for Account references and leaves the Security in place.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Commodity"
          ]
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

# Referenced by Accounts

## Trigger

Choose Remove for a security still used by accounts.

## Outcome

The Product reports Account references and leaves the Security in place; this does not establish a universal Transaction-reference check.
