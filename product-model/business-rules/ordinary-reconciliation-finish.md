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
      "target": "gnucash/gnome/window-reconcile.cpp#recnRecalculateBalance"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/window-reconcile.cpp#recnFinishCB"
    }
  ]
}
---

# Ordinary reconciliation Finish requires zero difference

Ordinary Finish is enabled only at zero difference.
