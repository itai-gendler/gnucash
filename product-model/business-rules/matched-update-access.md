---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction",
      "effect": "changes",
      "facts": [
        "Posted date",
        "Description",
        "Notes"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop::import-transactions"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Import updates enabled",
          "is": true,
          "entity": "application-preferences"
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

# Only the User replaces matched transaction details when import updates are enabled

Replacement of matched header details requires the User and the singleton application preference Import updates enabled. Clearing without replacement remains its separate behavior.
