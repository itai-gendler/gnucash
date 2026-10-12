---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Delete, then decline the deletion or reconciled-accounting warning.",
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
      "text": "The Transaction and its Splits remain unchanged.",
      "kind": "product",
      "entities": [
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "split",
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

# Decline warning

## Trigger

Choose Delete, then decline the deletion or reconciled-accounting warning.

## Outcome

The Transaction and its Splits remain unchanged.
