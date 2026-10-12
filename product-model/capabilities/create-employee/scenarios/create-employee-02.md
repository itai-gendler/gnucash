---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit a missing required address name or invalid workday/rate expression.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::employee"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product requests corrected Employee inputs and does not accept the invalid record.",
      "kind": "product",
      "entities": [
        {
          "entity": "employee",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::employee"
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

# Invalid required facts/amounts

## Trigger

Submit a missing Payment-Address Name or invalid workday/rate expression.

## Outcome

The Product requests corrected Employee inputs and does not accept the invalid record.
