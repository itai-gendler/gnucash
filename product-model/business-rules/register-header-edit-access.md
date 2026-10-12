---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction",
      "effect": "changes",
      "facts": [
        "Posted date",
        "Number",
        "Description",
        "Currency"
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

# Only the User edits eligible unprotected transaction headers in a writable register

Header changes selected by this Rule require a writable book and no explicit transaction protection. A disabled read-only period admits the operation; otherwise the transaction’s posted date must meet the related book’s cutoff.
