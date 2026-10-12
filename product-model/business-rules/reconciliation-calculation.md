---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "reconcile-account",
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

# Reconciliation difference compares statement and selected accounting

Displayed difference compares statement ending balance with the sign-adjusted starting reconciled balance and selected debit/credit net. Current selections and difference are process information.
