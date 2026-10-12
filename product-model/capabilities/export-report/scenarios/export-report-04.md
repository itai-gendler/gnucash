---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Export when the exporter fails or the destination cannot be written.",
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
      "text": "The Product presents Report exporter/destination diagnostics and does not claim a successfully written export.",
      "kind": "product",
      "entities": [
        {
          "entity": "report",
          "effect": "reads",
          "facts": [
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

# Exporter/destination failure in GnuCash

## Trigger

Export when the exporter fails or the destination cannot be written.

## Outcome

The Product presents Report exporter/destination diagnostics and does not claim a successfully written export.
