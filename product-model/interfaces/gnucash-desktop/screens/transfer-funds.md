---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Name",
        "Type",
        "Commodity"
      ]
    },
    {
      "entity": "transaction",
      "shows": [
        "Posted date",
        "Number",
        "Description",
        "Notes"
      ],
      "collects": [
        "Posted date",
        "Number",
        "Description",
        "Notes"
      ]
    },
    {
      "entity": "split",
      "shows": [
        "Account",
        "Memo",
        "Amount",
        "Value"
      ],
      "collects": [
        "Account",
        "Memo",
        "Amount",
        "Value"
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

# Transfer Funds

Supply the movement’s accounting and conversion inputs between selected accounts.
