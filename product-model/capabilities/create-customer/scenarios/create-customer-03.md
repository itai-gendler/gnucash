---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Inspect the business creation action in a read-only session.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::customer"
        }
      },
      "actor": "user"
    },
    {
      "text": "The creation action is disabled and no Customer is created.",
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
          "place": "gnucash-desktop::customer"
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

# Read-only creation action

## Trigger

Inspect the business creation action in a read-only session.

## Outcome

The creation action is disabled and no Customer is created.
