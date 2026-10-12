---
{
  "entities": [
    {
      "entity": "price",
      "shows": [
        "Commodity",
        "Currency",
        "Date",
        "Source",
        "Type",
        "Value"
      ],
      "collects": [
        "Commodity",
        "Currency",
        "Date",
        "Source",
        "Type",
        "Value"
      ]
    },
    {
      "entity": "security",
      "shows": [
        "Name",
        "Namespace",
        "Symbol"
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

# Price Database

Read and edit dated price records, select pruning inputs and retrieve online quotes.
