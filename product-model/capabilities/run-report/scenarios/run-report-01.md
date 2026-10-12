---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Select a report and options for the current accounting.",
      "kind": "actor",
      "entities": [
        {
          "entity": "report",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::report"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product creates a working Report and renders accounting according to the chosen Options without posting Transactions.",
      "kind": "product",
      "entities": [
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
          "place": "gnucash-desktop::report"
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

# Render with Options in GnuCash

## Trigger

Select a report and options for the current accounting.

## Outcome

The Product creates a working Report and renders accounting according to the chosen Options without posting Transactions.
