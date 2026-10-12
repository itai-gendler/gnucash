---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Select accounts, recurrence/history inputs and precision, then request period-history estimates.",
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
      "text": "The Product records Budget Account-period amounts from selected Account historical activity for the corresponding periods.",
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

# Period-history estimates

## Trigger

Select accounts, recurrence/history inputs and precision, then request period-history estimates.

## Outcome

The Product records Budget Account-period amounts from selected Account historical activity for the corresponding periods.
