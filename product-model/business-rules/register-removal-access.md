---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction",
      "effect": "removes",
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
          "absent": true
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
          "absent": true
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

# Only the User removes eligible unprotected transactions in a writable register

Removal requires a writable book, no explicit protection and the inactive-period or eligible-date alternative.
