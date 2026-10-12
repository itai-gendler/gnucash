---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose a template hierarchy, commodity and nonzero opening-balance inputs, then finish.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::account-hierarchy"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product creates or merges selected Accounts and any nonzero opening-balance Transactions with dependent Splits; the Book becomes unsaved. When entered through new-book setup, the Product invokes Save As for the completed hierarchy.",
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
          "place": "gnucash-desktop::account-hierarchy"
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

# Template hierarchy

## Trigger

Choose a template hierarchy, commodity and optional opening balances, then finish.

## Outcome

The Product creates or merges selected Accounts and any nonzero opening-balance Transactions with dependent Splits; the Book becomes unsaved.


## Edge cases

- With no nonzero opening balances, hierarchy creation records no opening-balance transaction.
- The automatic Save As continuation belongs to new-book setup; an ordinary hierarchy addition does not promise it.
