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
      "type": "entity",
      "id": "split",
      "facts": [
        "Online identifier"
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

# Imported identity handling follows the source format

OFX duplicate identifiers and QIF prune/merge are format-specific; CSV receives no inferred identifier parity.
