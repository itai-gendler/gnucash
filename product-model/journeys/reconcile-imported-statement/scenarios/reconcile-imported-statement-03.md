---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "GnuCash continuation"
  },
  "steps": [
    {
      "text": "Choose OFX Clear for a selected match without replacement.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::import-transactions"
        }
      },
      "actor": "user",
      "capability": "clear-matched-transactions"
    },
    {
      "text": "The Product preserves Transaction details and Split amounts/values/memo, changes unreconciled source status to cleared, leaves already reconciled status intact, records clearing date and supplied online identity, and discards the provisional download accounting. With requested reconciliation and valid statement balance data, the Product opens Reconcile using those statement figures.",
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
      "actor": "user",
      "capability": "clear-matched-transactions"
    },
    {
      "text": "Accept valid statement date/balance and the Include subaccounts choice.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::reconcile"
        }
      },
      "actor": "user",
      "capability": "reconcile-account"
    },
    {
      "text": "The Product retains Account Include subaccounts during accepted statement setup and updates Reconciliation interval only when a previous Last reconciliation date permits a nonnegative inferred interval; these setup changes precede Finish.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Include subaccounts",
            "Reconciliation interval"
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
          "place": "gnucash-desktop::reconcile"
        }
      },
      "actor": "user",
      "capability": "reconcile-account"
    },
    {
      "text": "Select matching debit/credit items and choose Finish when the displayed difference is zero.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::reconcile"
        }
      },
      "actor": "user",
      "capability": "reconcile-account"
    },
    {
      "text": "The displayed difference is zero for the sign-adjusted starting balance, selected net and ending balance.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::reconcile"
        }
      },
      "capability": "reconcile-account"
    },
    {
      "text": "The Product marks selected Splits reconciled with the statement date, records the Account’s last reconciliation date, clears postponed figures and updates derived balances; file persistence remains a later save.",
      "kind": "product",
      "entities": [
        {
          "entity": "split",
          "effect": "changes",
          "facts": [
            "Reconciliation status",
            "Reconciliation date"
          ]
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Last reconciliation date",
            "Postponed statement date",
            "Postponed ending balance",
            "Cleared balance",
            "Reconciled balance"
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
          "place": "gnucash-desktop::reconcile"
        }
      },
      "actor": "user",
      "capability": "reconcile-account"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/window-reconcile.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/reconcile-view.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Account.cpp"
    }
  ]
}
---

# Cleared matches

## Trigger

Successful OFX matching runs with Run Reconcile selected and valid statement balance/date data.

## Outcome

Accepted selected statement Splits are reconciled and Account history retains the statement date.
