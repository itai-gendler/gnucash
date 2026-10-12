---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Start reconciliation using the Account postponed statement date/balance and accept the restored figures and Include subaccounts choice.",
      "kind": "actor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Postponed statement date",
            "Postponed ending balance"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::reconcile"
        }
      },
      "actor": "user"
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
      "actor": "user"
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
      "actor": "user"
    },
    {
      "text": "The Product restores the Account’s postponed date and ending balance, presents eligible Splits and completes selected reconciled marks when the resulting difference is zero.",
      "kind": "product",
      "entities": [
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
          "entity": "split",
          "effect": "changes",
          "facts": [
            "Reconciliation status",
            "Reconciliation date"
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
      "actor": "user"
    }
  ],
  "references": [
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

# Resume postponed figures

## Trigger

Start reconciliation for accounting with postponed figures and continue the restored statement.

## Outcome

The Product restores the Account’s postponed date and ending balance, presents eligible Splits and completes selected reconciled marks when the resulting difference is zero.

## Edge cases

- On initial reconciliation with no Last reconciliation date, accepted setup retains Include subaccounts without updating Reconciliation interval. Finish still records the statement date and selected reconciliation marks.
- An accepted statement date yielding a negative inferred interval leaves Reconciliation interval unchanged.
