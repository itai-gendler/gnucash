---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Change the opened report’s supported options and apply them.",
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
      "text": "The Product records Report Options, marks working changes for configuration saving and rerenders its content from accounting.",
      "kind": "product",
      "entities": [
        {
          "entity": "report",
          "effect": "changes",
          "facts": [
            "Options",
            "Needs save",
            "Rendered content"
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

# Change Options and rerender

## Trigger

Change the opened report’s supported options and apply them.

## Outcome

The Product records Report Options, marks working changes for configuration saving and rerenders its content from accounting.
