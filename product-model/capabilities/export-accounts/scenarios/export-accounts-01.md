---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Export Accounts and a writable destination.",
      "kind": "actor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product writes the Account hierarchy and associated account/commodity information without Transaction contents; current Book accounting is not replaced.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Name",
            "Code",
            "Description",
            "Notes",
            "Type",
            "Commodity",
            "Precision",
            "Parent",
            "Placeholder",
            "Hidden",
            "Opening balance account",
            "Tax related",
            "Lower balance limit",
            "Upper balance limit",
            "Include subaccounts in balance limits",
            "Balance",
            "Cleared balance",
            "Reconciled balance",
            "Last reconciliation date",
            "Reconciliation interval",
            "Include subaccounts",
            "Postponed statement date",
            "Postponed ending balance"
          ]
        },
        {
          "entity": "book",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/gnc-file.c"
    }
  ]
}
---

# Export hierarchy without Transactions

## Trigger

Choose Export Accounts and a writable destination.

## Outcome

The Product writes the Account hierarchy and associated account/commodity information without Transaction contents; current Book accounting is not replaced.
