---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "split",
      "effect": "changes",
      "facts": [
        "Account",
        "Memo",
        "Action"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
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
          "fact": "Read-only reason",
          "absent": true,
          "entity": "transaction"
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
          "fact": "Read-only reason",
          "absent": true,
          "entity": "transaction"
        },
        {
          "fact": "Posted date",
          "at-least": {
            "entity": "book",
            "fact": "Transaction read-only cutoff"
          },
          "entity": "transaction"
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

# Only the User edits eligible unprotected split fields in a writable register

Account, Memo and Action edits require the related transaction to be unprotected and date eligible in a writable book.
