---
{
  "availability": [
    {
      "place": "gnucash-desktop"
    },
    {
      "place": "gnucash-cli"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/app-utils/gnc-quotes.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-price-edit-db.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnucash-commands.cpp"
    }
  ]
}
---

# Get quotes

Fetch Finance::Quote results and retain valid prices, reporting partial and external failures. CLI retrieval loads and separately saves the book.
