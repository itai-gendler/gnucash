---
{
  "kind": "validation",
  "routes": {
    "invoice": "Invoice",
    "bill": "Bill",
    "expense-voucher": "Expense Voucher"
  },
  "steps": [
    {
      "text": "Inspect recording a ledger row on a posted document or in a read-only session.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "invoice": {
          "place": "gnucash-desktop::invoice"
        },
        "bill": {
          "place": "gnucash-desktop::bill"
        },
        "expense-voucher": {
          "place": "gnucash-desktop::expense-voucher"
        }
      },
      "actor": "user"
    },
    {
      "text": "The ledger recording action is disabled or read-only; no entry is recorded.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Session access"
          ]
        }
      ],
      "contexts": {
        "invoice": {
          "place": "gnucash-desktop::invoice"
        },
        "bill": {
          "place": "gnucash-desktop::bill"
        },
        "expense-voucher": {
          "place": "gnucash-desktop::expense-voucher"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/gncEntryLedgerControl.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/gncEntryLedgerModel.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/gncEntryLedgerLayout.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-invoice.cpp"
    }
  ]
}
---

# Posted/read-only ledger

## Trigger

Inspect recording a ledger row on a posted document or in a read-only session.

## Outcome

The ledger recording action is disabled or read-only; no entry is recorded.
