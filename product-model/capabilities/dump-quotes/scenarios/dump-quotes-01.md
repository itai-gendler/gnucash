---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash CLI"
  },
  "steps": [
    {
      "text": "Request quote dumping for a supported source and supplied symbols.",
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
      "text": "The Product outputs the returned symbol quote information without loading or changing any accounting source.",
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

# Requested source/symbol results

## Trigger

Request quote dumping for a supported source and supplied symbols.

## Outcome

The Product outputs the returned symbol quote information without loading or changing any accounting source.
