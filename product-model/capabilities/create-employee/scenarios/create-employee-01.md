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
          "place": "gnucash-desktop::employee"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product creates the Employee, generating its Number and retaining Username, contact name/address details, language, workday, rate, currency and credit-card account.",
      "kind": "product",
      "entities": [
        {
          "entity": "employee",
          "effect": "creates",
          "facts": [
            "Number",
            "Username",
            "Payment contact",
            "Active",
            "Language",
            "Workday",
            "Rate",
            "Currency",
            "Credit-card account",
            "Open balance"
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

# Valid record/generated blank number

## Trigger

Supply the supported record facts and save with a blank number.

## Outcome

The Product creates the Employee, generating its Number and retaining Username, contact name/address details, language, workday, rate, currency and credit-card account.
