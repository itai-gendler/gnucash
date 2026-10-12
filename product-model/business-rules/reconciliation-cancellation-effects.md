---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "cancel-reconciliation",
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

# Cancellation discards local selections without undoing accepted accounting

Discard local marking selections without undoing accepted setup or independently committed work.
