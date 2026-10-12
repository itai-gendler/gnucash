---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "transfer-funds",
      "contexts": [
        {
          "place": "gnucash-desktop::transfer-funds"
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

# Transfers require suitable accounts and valid conversion inputs

Require suitable distinct Accounts, valid amount/rate, and applicable conversion precision.
