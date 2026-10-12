---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Postpone and confirm retaining the unfinished statement.",
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
      "text": "The Product stores the Account’s postponed statement date/balance; selected eligible Splits become cleared and applicable unselected Splits become unreconciled. Future unselected candidates remain unchanged.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Postponed statement date",
            "Postponed ending balance",
            "Cleared balance"
          ]
        },
        {
          "entity": "split",
          "effect": "changes",
          "facts": [
            "Reconciliation status"
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

# Retain statement figures and clearing choices

## Trigger

Choose Postpone and confirm retaining the unfinished statement.

## Outcome

The Product stores the Account’s postponed statement date/balance; selected eligible Splits become cleared and applicable unselected Splits become unreconciled. Future unselected candidates remain unchanged.
