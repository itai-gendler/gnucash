---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "book",
      "effect": "changes",
      "facts": [
        "Saved contents"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop"
        },
        {
          "place": "gnucash-cli"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Session access",
          "is": "Writable"
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

# Only the User writes saved book contents in a writable session

Writing Saved contents requires the User and a Writable current Book session. Save As first establishes access for the chosen destination; it does not grant writing the previous read-only source.
