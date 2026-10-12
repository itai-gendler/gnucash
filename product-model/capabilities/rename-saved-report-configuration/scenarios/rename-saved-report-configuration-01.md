---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Supply a nonduplicate name for the selected saved configuration.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::saved-report-configurations"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product retains the Saved Report Configuration Name and writes user saved-report configuration data.",
      "kind": "product",
      "entities": [
        {
          "entity": "saved-report-configuration",
          "effect": "changes",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "report",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::saved-report-configurations"
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

# Changed Name

## Trigger

Supply a nonduplicate name for the selected saved configuration.

## Outcome

The Product retains the Saved Report Configuration Name and writes user saved-report configuration data.
