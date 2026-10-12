---
{
  "entities": [
    {
      "entity": "transaction",
      "shows": [
        "Posted date",
        "Number",
        "Description",
        "Notes",
        "Currency"
      ]
    },
    {
      "entity": "split",
      "shows": [
        "Account",
        "Memo",
        "Action",
        "Amount",
        "Value",
        "Reconciliation status",
        "Online identifier"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Name",
        "Type",
        "Commodity"
      ]
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

# Import Transactions

Review proposed accounting, parse errors and candidate matches; supply parsing, mapping, matching and action decisions.
