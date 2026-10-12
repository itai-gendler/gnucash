---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Record nonzero entry value without a suitable posting account, or supply invalid numeric input.",
      "kind": "actor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::invoice"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product requests corrected Invoice Entry Income account/value inputs and does not record the invalid row.",
      "kind": "product",
      "entities": [
        {
          "entity": "invoice",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "invoice-entry",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::invoice"
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

# Invalid Invoice account/value

## Trigger

Record nonzero entry value without a suitable posting account, or supply invalid numeric input.

## Outcome

The Product requests corrected Invoice Entry Income account/value inputs and does not record the invalid row.
