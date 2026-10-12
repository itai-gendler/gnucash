---
{
  "kind": "primary",
  "routes": {
    "reports": "Report choices",
    "saved": "Saved report choices"
  },
  "steps": [
    {
      "text": "Inspect the offered definitions or saved configurations.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "reports": {
          "place": "gnucash-desktop::report"
        },
        "saved": {
          "place": "gnucash-desktop::saved-report-configurations"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product presents available Report choices and Saved Report Configuration names/types for selection.",
      "kind": "product",
      "entities": [
        {
          "entity": "report",
          "effect": "reads",
          "facts": [
            "Name",
            "Report type"
          ]
        },
        {
          "entity": "saved-report-configuration",
          "effect": "reads",
          "facts": [
            "Name",
            "Report type"
          ]
        }
      ],
      "contexts": {
        "reports": {
          "place": "gnucash-desktop::report"
        },
        "saved": {
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

# Report/saved choices in GnuCash

## Trigger

Open report choices or Saved Report Configurations.

## Outcome

The Product presents available Report choices and Saved Report Configuration names/types for selection.
