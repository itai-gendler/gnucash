---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Attempt to edit while another register holds the transaction’s edit.",
      "kind": "actor",
      "entities": [
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::register"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product warns about the concurrent Transaction edit and does not treat the second register as an isolated successful commit.",
      "kind": "product",
      "entities": [
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": []
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

# Concurrent-register conflict

## Trigger

Attempt to edit while another register holds the transaction’s edit.

## Outcome

The Product warns about the concurrent Transaction edit and does not treat the second register as an isolated successful commit.
