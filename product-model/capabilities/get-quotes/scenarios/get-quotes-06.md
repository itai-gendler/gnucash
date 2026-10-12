---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash CLI"
  },
  "steps": [
    {
      "text": "Request quotes with unavailable or failing Finance::Quote.",
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
      "text": "The Product loads the Book and establishes its normal writable source session.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Location",
            "Session access"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-cli"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product displays diagnostics for the quote exception and still saves the loaded Book when its source write succeeds; that caught exception does not itself change the zero return value.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Saved contents",
            "Unsaved changes"
          ]
        }
      ],
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

# Unavailable/failed retrieval in GnuCash CLI

## Trigger

Request quotes with unavailable or failing Finance::Quote.

## Outcome

A caught Finance::Quote exception is reported; successful subsequent book saving can still leave exit status zero.

## Edge cases

- Book save failure instead follows the separately specified backend-failure outcome.
