---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "GnuCash continuation"
  },
  "steps": [
    {
      "text": "Application Preferences enables the credit-card transfer prompt and the selected Account is a credit-card account; the statement ending balance is negative.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Type"
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
          "place": "gnucash-desktop"
        }
      }
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
      "text": "The Product marks selected Splits reconciled with the statement date, records the Account’s last reconciliation date, clears postponed figures and updates derived balances; file persistence remains a later save. The Product opens a prefilled Transfer Funds process using the negative ending balance and a funding Account when one is found.",
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
    },
    {
      "text": "Select distinct same-currency accounts and supply date, amount and accounting description.",
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
          "place": "gnucash-desktop::transfer-funds"
        }
      },
      "actor": "user",
      "capability": "transfer-funds"
    },
    {
      "text": "The Product creates a Transaction and dependent Splits carrying the equal same-currency transfer.",
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
          "place": "gnucash-desktop::transfer-funds"
        }
      },
      "actor": "user",
      "capability": "transfer-funds"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/dialog-transfer.cpp"
    }
  ]
}
---

# Prompt enabled, credit Account, negative ending balance

## Trigger

Balanced reconciliation completes for a credit-card account with a negative statement ending balance and the payment-prompt preference enabled.

## Outcome

The offered prefilled payment transfer is recorded as accounting.
