---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Name",
        "Commodity",
        "Reconciled balance",
        "Last reconciliation date",
        "Reconciliation interval",
        "Include subaccounts",
        "Postponed statement date",
        "Postponed ending balance"
      ],
      "collects": [
        "Include subaccounts"
      ]
    },
    {
      "entity": "transaction",
      "shows": [
        "Posted date",
        "Number",
        "Description"
      ]
    },
    {
      "entity": "split",
      "shows": [
        "Account",
        "Amount",
        "Value",
        "Memo",
        "Reconciliation status",
        "Reconciliation date"
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

# Reconcile

Compare statement inputs with candidate accounting and calculated figures; select, finish, postpone or cancel the process.
