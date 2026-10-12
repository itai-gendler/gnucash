---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Open the overview and supply optional search or active-record filters.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::employees"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product presents Employee identity/contact information and derived open balances.",
      "kind": "product",
      "entities": [
        {
          "entity": "employee",
          "effect": "reads",
          "facts": [
            "Number",
            "Username",
            "Payment contact",
            "Active",
            "Open balance"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::employees"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-employee.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-owner-tree.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-business.c"
    }
  ]
}
---

# Overview/search

## Trigger

Open the overview and supply optional search or active-record filters.

## Outcome

The Product presents Employee identity/contact information and derived open balances.
