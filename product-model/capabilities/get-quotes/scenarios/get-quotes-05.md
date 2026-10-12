---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Inspect Get Quotes with Finance::Quote unavailable, or encounter retrieval failure.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::price-database"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product disables unavailable retrieval or displays diagnostics for the external failure; a successful complete Price set is not claimed.",
      "kind": "product",
      "entities": [
        {
          "entity": "price",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::price-database"
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

# Unavailable/failed retrieval in GnuCash

## Trigger

Inspect Get Quotes with Finance::Quote unavailable, or encounter retrieval failure.

## Outcome

The Product disables unavailable retrieval or reports the external failure; a successful complete Price set is not claimed.
