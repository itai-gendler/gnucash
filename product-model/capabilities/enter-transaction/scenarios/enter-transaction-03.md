---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Attempt to leave an entry with incompatible precision or a remaining imbalance.",
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
      "text": "The Product requests correction or an explicit balancing choice and can keep the current Transaction row selected; ordinary commit may create an imbalance-adjusting Split.",
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
          "facts": [
            "Amount",
            "Value"
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

# Precision/balance correction

## Trigger

Attempt to leave an entry with incompatible precision or a remaining imbalance.

## Outcome

The Product requests correction or an explicit balancing choice and can keep the current Transaction row selected; ordinary commit may create an imbalance-adjusting Split.
