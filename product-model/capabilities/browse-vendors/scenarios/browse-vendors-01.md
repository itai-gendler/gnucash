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
          "place": "gnucash-desktop::vendors"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product presents Vendor identity/contact information and derived open balances.",
      "kind": "product",
      "entities": [
        {
          "entity": "vendor",
          "effect": "reads",
          "facts": [
            "Number",
            "Name",
            "Contact",
            "Active",
            "Open balance"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::vendors"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-vendor.c"
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

The Product presents Vendor identity/contact information and derived open balances.
