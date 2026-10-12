---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Inspect editing of accounting whose session, view, explicit protection or posted-date check restricts the action.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::register"
        }
      },
      "actor": "user"
    },
    {
      "text": "The edit action is disabled or the protected Transaction change is refused; current accounting remains.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Session access",
            "Transaction read-only period",
            "Transaction read-only cutoff"
          ]
        },
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": [
            "Posted date",
            "Read-only reason"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::register"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-register.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-split-reg.c#gnc_split_reg_determine_read_only"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/split-register.c#gnc_split_register_save"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Transaction.cpp"
    }
  ]
}
---

# Book/Transaction restriction

## Trigger

Inspect editing of accounting whose session, view, explicit protection or posted-date check restricts the action.

## Outcome

The edit action is disabled or the protected Transaction change is refused; current accounting remains.
