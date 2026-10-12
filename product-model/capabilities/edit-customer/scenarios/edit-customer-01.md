---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Change supported contact/accounting facts and save.",
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
      "text": "The Product records changed Customer facts: Name, billing/shipping contacts, currency, terms, tax settings, discount, credit limit and notes.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Number",
            "Name",
            "Billing contact",
            "Shipping contact",
            "Active",
            "Currency",
            "Terms",
            "Tax settings",
            "Discount",
            "Credit limit",
            "Notes"
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

# Changed facts

## Trigger

Change supported contact/accounting facts and save.

## Outcome

The Product records changed Customer facts: Name, billing/shipping contacts, currency, terms, tax settings, discount, credit limit and notes.
