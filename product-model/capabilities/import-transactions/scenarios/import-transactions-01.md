---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose CSV, map valid rows to accounts, accept proposed additions and finish matching.",
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
      "text": "The Product creates Active Transactions with dependent Splits for accepted CSV additions; balancing uses selected destination accounting and the source Split becomes cleared with a reconciliation date.",
      "kind": "product",
      "entities": [
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

# CSV additions

## Trigger

Choose CSV, map valid rows to accounts, accept proposed additions and finish matching.

## Outcome

The Product creates Active Transactions with dependent Splits for accepted CSV additions; balancing uses selected destination accounting and the source Split becomes cleared with a reconciliation date.
