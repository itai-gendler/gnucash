---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "get-quotes",
      "contexts": [
        {
          "place": "gnucash-desktop"
        },
        {
          "place": "gnucash-cli"
        }
      ]
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

# Quote retrieval retains valid results and reports failures

Retain valid dated Prices and report partial/external failures; CLI persistence is separate.
