---
{
  "appliesTo": [
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
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Session access",
          "is": "Writable",
          "entity": "book"
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

# Only the User records reconciliation marks through writable accounting entry

Only the User records reconciliation marks through writable accounting entry.
