---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "add-reversing-transaction",
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
    }
  ]
}
---

# A reversal negates accounting and retains its original association

Negate Amount/Value, clear reconciliation indicators, retain association; offer existing reversal instead of creating another.
