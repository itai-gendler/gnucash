---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Save a new reusable configuration and encounter configuration-file write failure.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::report"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product displays diagnostics for configuration-file failure after creating the Saved Report Configuration in memory; the working Report’s saved association is not advanced by this failed write.",
      "kind": "product",
      "entities": [
        {
          "entity": "saved-report-configuration",
          "effect": "creates",
          "facts": [
            "Name",
            "Report type",
            "Options",
            "Embedded configurations"
          ]
        },
        {
          "entity": "report",
          "effect": "reads",
          "facts": [
            "Saved configuration",
            "Needs save"
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

# Write failure

## Trigger

Save a new reusable configuration when writing the user saved-report file fails.

## Outcome

The new configuration can remain in memory despite file-write failure. The working report association is assigned only after successful configuration saving.
