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
      "target": "libgnucash/engine/Transaction.cpp#xaccTransIsBalanced"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Scrub.cpp#xaccTransScrubImbalance"
    }
  ]
}
---

# Ordinary register commit balances each commodity through Trading accounts

Ordinary commit keeps value and every commodity balanced; excludes loading/shutdown paths. Non-trading and Trading Splits must each sum to zero in value, and no commodity may stay imbalanced. On commit the Product removes the Transaction's Trading Splits, adds an Imbalance Split for any remaining value, then adds Trading Splits per commodity and reversing Trading Splits for zero-amount gain or loss lines.
