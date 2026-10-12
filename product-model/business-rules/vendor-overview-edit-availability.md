---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-vendor",
      "contexts": [
        {
          "place": "gnucash-desktop::vendors"
        }
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

# Vendor overview editing has a read-only action gate

The Vendor overview enables its edit action only with a selected record in a writable Book. This entry-route check does not establish a universal restriction on independently reached editing dialogs.
