---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Supply the supported record facts and save with a blank number.",
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
      "text": "The Product creates the Customer, generating its Number and retaining Name, billing/shipping contacts, currency, terms, tax settings, discount, credit limit and notes.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "creates",
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
            "Notes",
            "Open balance"
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

# Valid record/generated blank number

## Trigger

Supply the supported record facts and save with a blank number.

## Outcome

The Product creates the Customer, generating its Number and retaining Name, billing/shipping contacts, currency, terms, tax settings, discount, credit limit and notes.
