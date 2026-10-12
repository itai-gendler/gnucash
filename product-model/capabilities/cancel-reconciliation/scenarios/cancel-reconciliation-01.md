---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Cancel and accept confirmation when current marking selections changed.",
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
      "text": "The Product discards current local selections and closes reconciliation; accepted Account setup and independently committed accounting remain.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Reconciliation interval",
            "Include subaccounts"
          ]
        },
        {
          "entity": "split",
          "effect": "reads",
          "facts": [
            "Reconciliation status"
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

# Discard current selections

## Trigger

Choose Cancel and accept confirmation when current marking selections changed.

## Outcome

The Product discards current local selections and closes reconciliation; accepted Account setup and independently committed accounting remain.
