---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Last reconciliation date",
        "Postponed statement date",
        "Postponed ending balance"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop::reconcile"
        }
      ]
    },
    {
      "type": "entity",
      "id": "split",
      "effect": "changes",
      "facts": [
        "Reconciliation status",
        "Reconciliation date"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop::reconcile"
        }
      ]
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

# Completed reconciliation retains selected marks and history

Selected Splits become reconciled with date; last date is retained; postponement is cleared.
