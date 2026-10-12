---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Supply an invalid statement ending-balance expression.",
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
      "text": "The Product requests a valid statement amount before continuing reconciliation; no Split marks are committed.",
      "kind": "product",
      "entities": [
        {
          "entity": "split",
          "effect": "reads",
          "facts": []
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

# Invalid statement amount

## Trigger

Supply an invalid statement ending-balance expression.

## Outcome

The Product requests a valid statement amount before continuing reconciliation; no Split marks are committed.
