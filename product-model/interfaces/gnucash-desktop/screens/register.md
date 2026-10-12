---
{
  "entities": [
    {
      "entity": "transaction",
      "shows": [
        "Posted date",
        "Entered date",
        "Number",
        "Description",
        "Notes",
        "Currency",
        "Read-only reason",
        "Void reason",
        "Void time",
        "Reversing transaction",
        "Document link"
      ],
      "collects": [
        "Posted date",
        "Number",
        "Description",
        "Notes",
        "Currency",
        "Void reason"
      ]
    },
    {
      "entity": "split",
      "shows": [
        "Account",
        "Memo",
        "Action",
        "Amount",
        "Value",
        "Reconciliation status",
        "Reconciliation date"
      ],
      "collects": [
        "Account",
        "Memo",
        "Action",
        "Amount",
        "Value",
        "Reconciliation status"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Name",
        "Commodity",
        "Balance",
        "Cleared balance",
        "Reconciled balance"
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

# Register

Work with selected transaction and split accounting, filtered register results and account balances; supply duplicate and void inputs here.
