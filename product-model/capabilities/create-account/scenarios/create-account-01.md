---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose New Account and supply identity, parent, type, commodity and a nonzero opening balance.",
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
          "place": "gnucash-desktop::account"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product creates the Account with its chosen facts and creates the opening-balance Transaction and dependent Splits when a nonzero balance is supplied.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
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
          "entity": "transaction",
          "effect": "creates",
          "facts": [
            "Posted date",
            "Entered date",
            "Number",
            "Description",
            "Notes",
            "Currency",
            "Read-only reason",
            "Void reason",
            "Void time",
            "Former notes",
            "Reversing transaction",
            "Scheduled source",
            "Document link"
          ],
          "to": "Active"
        },
        {
          "entity": "split",
          "effect": "creates",
          "facts": [
            "Account",
            "Memo",
            "Action",
            "Amount",
            "Value",
            "Reconciliation status",
            "Reconciliation date",
            "Former amount",
            "Former value",
            "Online identifier"
          ],
          "with": "transaction"
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
          "place": "gnucash-desktop::account"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-account-tree.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/dialog-account.c#gnc_ui_to_account"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/assistant-hierarchy.cpp#on_finish"
    }
  ]
}
---

# Individual Account with opening balance

## Trigger

Choose New Account and supply identity, parent, type, commodity and a nonzero opening balance.

## Outcome

The Product creates the Account with its chosen facts and creates the opening-balance Transaction and dependent Splits when a nonzero balance is supplied.
