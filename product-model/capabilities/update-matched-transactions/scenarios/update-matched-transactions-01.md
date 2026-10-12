---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose CSV Update and Clear for a selected match with replacement enabled.",
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
      "text": "The Product updates the matched Transaction’s posted date and selected description/notes, updates source Split amount/value/memo and related balancing values as applicable, then clears the match, dates it and retains supplied online identity. Already reconciled status is not downgraded.",
      "kind": "product",
      "entities": [
        {
          "entity": "transaction",
          "effect": "changes",
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
            "Amount",
            "Value",
            "Memo",
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

# CSV update then clear

## Trigger

Choose CSV Update and Clear for a selected match with replacement enabled.

## Outcome

The Product updates the matched Transaction’s posted date and selected description/notes, updates source Split amount/value/memo and related balancing values as applicable, then clears the match, dates it and retains supplied online identity. Already reconciled status is not downgraded.
