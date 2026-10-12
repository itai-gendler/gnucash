---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Supply the supported record facts and save with a blank number.",
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
      "text": "The Product creates the Vendor, generating its Number and retaining Name, contact, currency, terms, tax settings and notes.",
      "kind": "product",
      "entities": [
        {
          "entity": "vendor",
          "effect": "creates",
          "facts": [
            "Number",
            "Name",
            "Contact",
            "Active",
            "Currency",
            "Terms",
            "Tax settings",
            "Notes",
            "Open balance"
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

# Valid record/generated blank number

## Trigger

Supply the supported record facts and save with a blank number.

## Outcome

The Product creates the Vendor, generating its Number and retaining Name, contact, currency, terms, tax settings and notes.
