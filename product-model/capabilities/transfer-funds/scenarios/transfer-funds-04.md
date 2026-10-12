---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Inspect Transfer Funds from a read-only accounting entry route.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::transfer-funds"
        }
      },
      "actor": "user"
    },
    {
      "text": "The entry action is disabled; no transfer Transaction is created.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Session access"
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

# Read-only entry action

## Trigger

Inspect Transfer Funds from a read-only accounting entry route.

## Outcome

The entry action is disabled; no transfer Transaction is created.
