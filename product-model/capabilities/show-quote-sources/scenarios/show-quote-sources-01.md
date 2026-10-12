---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash CLI"
  },
  "steps": [
    {
      "text": "Request quote-source information.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-cli"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product outputs Finance::Quote version and supported source names.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-cli"
        }
      },
      "actor": "user"
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

# Version/source information

## Trigger

Request quote-source information.

## Outcome

The Product outputs Finance::Quote version and supported source names.
