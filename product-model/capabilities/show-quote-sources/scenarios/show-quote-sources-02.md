---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash CLI"
  },
  "steps": [
    {
      "text": "Request quote-source information with Finance::Quote unavailable.",
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
      "text": "The Product displays diagnostics for the unavailable Finance::Quote dependency and returns failure.",
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

# Finance::Quote unavailable

## Trigger

Request quote-source information with Finance::Quote unavailable.

## Outcome

The Product reports the unavailable Finance::Quote dependency and returns failure.
