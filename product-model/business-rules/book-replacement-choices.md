---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "new-book",
      "contexts": [
        {
          "place": "gnucash-desktop"
        }
      ]
    },
    {
      "type": "capability",
      "id": "open-book",
      "contexts": [
        {
          "place": "gnucash-desktop"
        }
      ]
    },
    {
      "type": "capability",
      "id": "revert-book",
      "contexts": [
        {
          "place": "gnucash-desktop"
        }
      ]
    },
    {
      "type": "capability",
      "id": "save-book",
      "contexts": [
        {
          "place": "gnucash-desktop"
        }
      ]
    },
    {
      "type": "capability",
      "id": "save-book-as",
      "contexts": [
        {
          "place": "gnucash-desktop"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/gnc-file.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnucash-commands.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/backend/xml/gnc-backend-xml.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/backend/sql/gnc-sql-backend.cpp"
    }
  ]
}
---

# Book replacement honors current choices and failure restoration

Honor unsaved/discard/overwrite choices and implemented failure restoration; no universal atomicity.
