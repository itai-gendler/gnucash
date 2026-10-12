---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "run-report",
      "contexts": [
        {
          "place": "gnucash-cli"
        }
      ]
    },
    {
      "type": "capability",
      "id": "export-report",
      "contexts": [
        {
          "place": "gnucash-cli"
        }
      ]
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

# CLI report execution resolves a supported unique report

Require one supported report; reject unknown/ambiguous selection and unsupported export types.
