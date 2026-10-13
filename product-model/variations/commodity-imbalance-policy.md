---
{
  "kind": "configuration",
  "of": "business-rule",
  "settings": [
    {
      "entity": "book",
      "fact": "Trading accounts"
    }
  ],
  "takesEffect": "Read from the Book each time a Transaction is committed; a change to the Book option applies to later commits.",
  "stability": "Existing Transactions keep the Imbalance or Trading Splits they already have until they are next edited and committed or scrubbed again.",
  "alternatives": [
    {
      "id": "ordinary-commit-balancing",
      "selectedWhen": "Trading accounts is off. A new Book starts with it off."
    },
    {
      "id": "ordinary-commit-trading-balancing",
      "selectedWhen": "Trading accounts is on."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/qofbook.cpp#qof_book_use_trading_accounts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gnc-optiondb.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Scrub.cpp#xaccTransScrubImbalance"
    }
  ]
}
---

# Commodity imbalance policy

A Book chooses how committed Transactions are balanced: with a plain Imbalance Split, or with Trading accounts that keep each commodity balanced. Both policies are supported.
