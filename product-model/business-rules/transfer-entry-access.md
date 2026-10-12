---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction",
      "effect": "creates",
      "contexts": [
        {
          "place": "gnucash-desktop::transfer-funds"
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
        }
      ]
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

# Only the User records transfers through writable accounting entry

Only the User records transfers through writable accounting entry.
