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
          "place": "gnucash-desktop::customers"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product presents Customer identity/contact information and derived open balances.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Number",
            "Name",
            "Billing contact",
            "Active",
            "Open balance"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::customers"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-customer.c#gnc_ui_to_customer"
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

The Product presents Customer identity/contact information and derived open balances.
