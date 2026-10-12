---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit unsuitable or identical accounts, an invalid amount or an invalid conversion.",
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
          "place": "gnucash-desktop::transfer-funds"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product requests corrected Account, amount or rate inputs and does not record the transfer Transaction.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Commodity",
            "Type"
          ]
        },
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::transfer-funds"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/dialog-transfer.cpp"
    }
  ]
}
---

# Invalid Accounts/amount/rate

## Trigger

Submit unsuitable or identical accounts, an invalid amount or an invalid conversion.

## Outcome

The Product requests corrected Account, amount or rate inputs and does not record the transfer Transaction.
