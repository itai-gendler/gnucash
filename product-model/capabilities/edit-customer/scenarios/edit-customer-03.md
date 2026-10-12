---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Inspect editing reached from the read-only owner overview.",
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
      "text": "The overview edit action is disabled and the selected Customer is not changed.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Session access"
          ]
        },
        {
          "entity": "customer",
          "effect": "reads",
          "facts": []
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

# Read-only overview action

## Trigger

Inspect editing reached from the read-only owner overview.

## Outcome

The overview edit action is disabled and the selected Customer is not changed.
