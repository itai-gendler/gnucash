---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit a blank company name.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::vendor"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product requests corrected Vendor inputs and does not accept the invalid record.",
      "kind": "product",
      "entities": [
        {
          "entity": "vendor",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::vendor"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-vendor.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-owner-tree.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-business.c"
    }
  ]
}
---

# Invalid required facts

## Trigger

Submit a blank company name.

## Outcome

The Product requests corrected Vendor inputs and does not accept the invalid record.
