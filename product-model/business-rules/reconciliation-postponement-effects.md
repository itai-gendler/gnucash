---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
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
        "Reconciliation status"
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

# Postponement retains statement figures and eligible clearing choices

Retain statement parameters; selected eligible Splits become cleared, applicable unselected Splits unreconciled; future unselected candidates remain unchanged.
