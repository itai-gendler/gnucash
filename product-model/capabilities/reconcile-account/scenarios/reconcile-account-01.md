---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Accept valid statement date/balance and the Include subaccounts choice.",
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
      "text": "The displayed difference is zero for the sign-adjusted starting balance, selected net and ending balance.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::reconcile"
        }
      }
    },
    {
      "text": "The Product marks selected Splits reconciled with the statement date, records the Account’s last reconciliation date, clears postponed figures and updates derived balances; file persistence remains a later save. If Application Preferences enables the credit-card transfer prompt, the selected Account is credit-card type and the ending statement balance is negative, the Product opens a prefilled transfer.",
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
        },
        {
          "entity": "application-preferences",
          "effect": "reads",
          "facts": [
            "Prompt for credit-card payment"
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

# Balanced completion

## Trigger

Supply valid statement figures, select matching debit/credit items and choose Finish when the difference is zero.

## Outcome

The Product marks selected Splits reconciled with the statement date, records the Account’s last reconciliation date, clears postponed figures and updates derived balances; file persistence remains a later save.

## Edge cases

- On initial reconciliation with no Last reconciliation date, accepted setup retains Include subaccounts without updating Reconciliation interval. Finish still records the statement date and selected reconciliation marks.
- An accepted statement date yielding a negative inferred interval leaves Reconciliation interval unchanged.
