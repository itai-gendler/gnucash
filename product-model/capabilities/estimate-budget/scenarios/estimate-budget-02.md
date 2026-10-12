---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Select accounts, choose averaged estimation and supply history and precision inputs.",
      "kind": "actor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::budget"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product records averaged historical Budget Account-period amounts for the selected Accounts using the requested precision.",
      "kind": "product",
      "entities": [
        {
          "entity": "budget",
          "effect": "changes",
          "facts": [
            "Account-period amounts"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Commodity"
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
          "place": "gnucash-desktop::budget"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-budget.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-budget.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-budget-view.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gnc-budget.cpp"
    }
  ]
}
---

# Averaged estimates

## Trigger

Select accounts, choose averaged estimation and supply history and precision inputs.

## Outcome

The Product records averaged historical Budget Account-period amounts for the selected Accounts using the requested precision.
