---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash CLI"
  },
  "steps": [
    {
      "text": "Request a known report’s description and options, optionally supplying a book.",
      "kind": "actor",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "report",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-cli"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product describes the Report and its options; a supplied Book is opened read-only.",
      "kind": "product",
      "entities": [
        {
          "entity": "report",
          "effect": "reads",
          "facts": [
            "Name",
            "Report type",
            "Options"
          ]
        },
        {
          "entity": "book",
          "effect": "reads",
          "facts": []
        }
      ],
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
      "target": "gnucash/gnome/gnc-plugin-page-report.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-custom-report.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/report/report-core.scm"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/report/gnc-report.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnucash-commands.cpp"
    }
  ]
}
---

# Report description/options in GnuCash CLI

## Trigger

Request a known report’s description and options, optionally supplying a book.

## Outcome

The Product describes the Report and its options; a supplied Book is opened read-only.
