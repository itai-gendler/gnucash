---
{
  "entities": [
    {
      "entity": "vendor",
      "shows": [
        "Number",
        "Name",
        "Contact",
        "Active",
        "Currency",
        "Terms",
        "Tax settings",
        "Notes",
        "Open balance"
      ],
      "collects": [
        "Number",
        "Name",
        "Contact",
        "Active",
        "Currency",
        "Terms",
        "Tax settings",
        "Notes"
      ]
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

# Vendor

Work with one vendor’s retained contact and accounting settings.
