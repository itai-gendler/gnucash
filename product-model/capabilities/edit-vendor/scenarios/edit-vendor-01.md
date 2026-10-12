---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Change supported contact/accounting facts and save.",
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
      "text": "The Product records changed Vendor facts: Name, contact, currency, terms, tax settings and notes.",
      "kind": "product",
      "entities": [
        {
          "entity": "vendor",
          "effect": "changes",
          "facts": [
            "Number",
            "Name",
            "Contact",
            "Active",
            "Currency",
            "Terms",
            "Tax settings",
            "Notes"
          ]
        },
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Unsaved changes"
          ]
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

# Changed facts

## Trigger

Change supported contact/accounting facts and save.

## Outcome

The Product records changed Vendor facts: Name, contact, currency, terms, tax settings and notes.
