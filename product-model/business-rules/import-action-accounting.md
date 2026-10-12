---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "import-transactions",
      "contexts": [
        {
          "place": "gnucash-desktop::import-transactions"
        }
      ]
    },
    {
      "type": "capability",
      "id": "update-matched-transactions",
      "contexts": [
        {
          "place": "gnucash-desktop::import-transactions"
        }
      ]
    },
    {
      "type": "capability",
      "id": "clear-matched-transactions",
      "contexts": [
        {
          "place": "gnucash-desktop::import-transactions"
        }
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

# Import decisions distinguish addition, replacement and clearing

ADD creates and clears; UPDATE replaces selected details and clears; CLEAR retains details; skipped/unmatched rows add nothing.
