---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Attempt an indicator edit on protected or restricted accounting.",
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
      "text": "The indicator change is refused or disabled; the Split remains unchanged.",
      "kind": "product",
      "entities": [
        {
          "entity": "split",
          "effect": "reads",
          "facts": [
            "Reconciliation status"
          ]
        },
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": [
            "Read-only reason",
            "Posted date"
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

# Restricted Split

## Trigger

Attempt an indicator edit on protected or restricted accounting.

## Outcome

The indicator change is refused or disabled; the Split remains unchanged.
