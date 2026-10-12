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
          "place": "gnucash-desktop::employee"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product records changed Employee facts: Username, contact name/address details, language, workday, rate, currency and credit-card account.",
      "kind": "product",
      "entities": [
        {
          "entity": "employee",
          "effect": "changes",
          "facts": [
            "Number",
            "Username",
            "Payment contact",
            "Active",
            "Language",
            "Workday",
            "Rate",
            "Currency",
            "Credit-card account"
          ]
        },
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Unsaved changes"
          ]
        },
        {
          "entity": "account",
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

# Changed facts

## Trigger

Change supported contact/accounting facts and save.

## Outcome

The Product records changed Employee facts: Username, contact name/address details, language, workday, rate, currency and credit-card account.
