---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose CSV Clear for a selected match without replacement.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::import-transactions"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product preserves Transaction details and Split amounts/values/memo, changes unreconciled source status to cleared, leaves already reconciled status intact, records clearing date and supplied online identity, and discards the provisional download accounting.",
      "kind": "product",
      "entities": [
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": [
            "Posted date",
            "Description",
            "Notes"
          ]
        },
        {
          "entity": "split",
          "effect": "changes",
          "facts": [
            "Reconciliation status",
            "Reconciliation date",
            "Online identifier"
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

# CSV clear without replacing details

## Trigger

Choose CSV Clear for a selected match without replacement.

## Outcome

The Product preserves Transaction details and Split amounts/values/memo, changes unreconciled source status to cleared, leaves already reconciled status intact, records clearing date and supplied online identity, and discards the provisional download accounting.
