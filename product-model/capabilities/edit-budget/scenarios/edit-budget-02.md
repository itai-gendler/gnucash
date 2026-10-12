---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Supply an invalid amount expression for a period cell.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::budget"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product rejects the invalid Budget value; a blank input instead unsets the amount.",
      "kind": "product",
      "entities": [
        {
          "entity": "budget",
          "effect": "reads",
          "facts": [
            "Account-period amounts"
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

# Invalid amount

## Trigger

Supply an invalid amount expression for a period cell.

## Outcome

The Product rejects the invalid Budget value; a blank input instead unsets the amount.
