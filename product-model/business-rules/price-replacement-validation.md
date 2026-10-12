---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "add-price",
      "contexts": [
        {
          "place": "gnucash-desktop::price-database"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-price",
      "contexts": [
        {
          "place": "gnucash-desktop::price-database"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-price-edit-db.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-price-editor.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gnc-pricedb.cpp"
    }
  ]
}
---

# Prices validate fields and ask before same-day replacement

Validate commodity/currency/value; same-day replacement can be declined.
