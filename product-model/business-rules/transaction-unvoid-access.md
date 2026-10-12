---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction",
      "effect": "changes",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ],
      "to": "Active"
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Session access",
          "is": "Writable",
          "entity": "book"
        },
        {
          "state": "Voided"
        },
        {
          "fact": "Transaction read-only period",
          "entity": "book",
          "is": 0
        }
      ]
    },
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Session access",
          "is": "Writable",
          "entity": "book"
        },
        {
          "state": "Voided"
        },
        {
          "fact": "Posted date",
          "at-least": {
            "entity": "book",
            "fact": "Transaction read-only cutoff"
          }
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

# Only the User restores eligible voided transactions in a writable register

Restoration requires a currently Voided transaction in a writable book, with the inactive-period or eligible-date alternative; the void protection reason is expected here.
