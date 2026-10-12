---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Accept valid statement date/balance and Include subaccounts, then select items whose displayed difference is nonzero.",
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
      "text": "Ordinary Finish is disabled; the Product retains the current local selections for correction or other reconciliation actions. Accepted Account setup remains retained while no Split reconciliation marks are committed.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Reconciled balance"
          ]
        },
        {
          "entity": "split",
          "effect": "reads",
          "facts": [
            "Amount",
            "Value",
            "Reconciliation status"
          ]
        },
        {
          "entity": "book",
          "effect": "reads",
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

# Nonzero difference disables ordinary Finish

## Trigger

Supply statement figures and selections whose displayed difference is nonzero.

## Outcome

Ordinary Finish is disabled; the Product retains the current local selections for correction or other reconciliation actions. Accepted Account setup remains retained while no Split reconciliation marks are committed.
