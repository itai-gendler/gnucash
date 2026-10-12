---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Change eligible reconciled accounting, accept the unreconcile warning and record the changes.",
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
      "text": "The Product records the Transaction changes and makes affected Split indicators unreconciled.",
      "kind": "product",
      "entities": [
        {
          "entity": "transaction",
          "effect": "changes",
          "facts": [
            "Posted date",
            "Number",
            "Description",
            "Notes",
            "Currency"
          ]
        },
        {
          "entity": "split",
          "effect": "changes",
          "facts": [
            "Account",
            "Memo",
            "Action",
            "Amount",
            "Value",
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

# Reconciled-edit warning choice

## Trigger

Edit reconciled accounting and respond to the unreconcile warning.

## Outcome

The accepted edit is committed with affected reconciliation indicators unreconciled.

## Edge cases

- Declining the warning leaves the proposed change unrecorded and preserves the previous indicator.
