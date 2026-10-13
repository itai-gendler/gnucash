---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction",
      "effect": "creates",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
    },
    {
      "type": "entity",
      "id": "transaction",
      "effect": "changes",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Scrub.cpp#gnc_transaction_balance_no_trading"
    }
  ]
}
---

# Ordinary register commit applies imbalance handling

Ordinary commit can add an imbalance-adjusting Split; excludes loading/shutdown paths. A Transaction is balanced when its Split values sum to zero, and any remainder goes to one Imbalance Split in the Transaction currency.
