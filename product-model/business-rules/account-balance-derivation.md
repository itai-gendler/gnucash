---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "facts": [
        "Balance",
        "Cleared balance",
        "Reconciled balance"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Account.cpp"
    }
  ]
}
---

# Account balances derive from split reconciliation indicators

Ordinary/cleared/reconciled balances use their inspected Split-status sums; void values are zero.
