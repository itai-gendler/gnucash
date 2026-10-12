---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit a missing required address name or invalid workday/rate expression while editing.",
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
      "text": "The Product requests corrected Employee inputs and leaves the invalid form changes unaccepted.",
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

# Invalid facts

## Trigger

Submit a missing Payment-Address Name or invalid workday/rate expression while editing.

## Outcome

The Product requests corrected Employee inputs and leaves the invalid form changes unaccepted.
