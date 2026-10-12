---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose QIF, complete conversion/mapping and accept selected duplicate pruning and account-tree merge.",
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
          "place": "gnucash-desktop::import-transactions"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product prunes selected duplicate Transactions and merges the imported Account hierarchy with accepted Active Transactions and dependent Splits; it opens Accounts when no account page exists.",
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
          "place": "gnucash-desktop::import-transactions"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/import-export/csv-imp/assistant-csv-trans-import.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/import-export/import-main-matcher.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/import-export/import-backend.cpp#gnc_import_process_trans_item"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/import-export/ofx/gnc-ofx-import.cpp#gnc_ofx_match_done"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/import-export/qif-imp/assistant-qif-import.c#gnc_ui_qif_import_finish_cb"
    }
  ]
}
---

# QIF conversion/merge

## Trigger

Choose QIF, complete conversion/mapping and accept selected duplicate pruning and account-tree merge.

## Outcome

The Product prunes selected duplicate Transactions and merges the imported Account hierarchy with accepted Active Transactions and dependent Splits; it opens Accounts when no account page exists.
