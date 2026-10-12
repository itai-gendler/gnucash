---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash CLI"
  },
  "steps": [
    {
      "text": "Request a uniquely resolved report from an available book.",
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
      "text": "The Product loads the Book read-only and creates and renders a working Report using supported Options; accounting is not posted.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Location",
            "Session access"
          ]
        },
        {
          "entity": "report",
          "effect": "creates",
          "facts": [
            "Name",
            "Report type",
            "Options",
            "Needs save",
            "Saved configuration",
            "Rendered content"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Balance",
            "Commodity"
          ]
        },
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": [
            "Posted date",
            "Currency"
          ]
        },
        {
          "entity": "split",
          "effect": "reads",
          "facts": [
            "Amount",
            "Value"
          ]
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

# Render from read-only Book in GnuCash CLI

## Trigger

Request a uniquely resolved report from an available book.

## Outcome

The Product loads the Book read-only and creates and renders a working Report using supported Options; accounting is not posted.
