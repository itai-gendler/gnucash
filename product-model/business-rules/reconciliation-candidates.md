---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "split",
      "effect": "reads",
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

# Reconciliation candidates are unreconciled or cleared splits in scope

Candidates are unreconciled/cleared Splits in the selected Account scope; no universal statement-date exclusion.
