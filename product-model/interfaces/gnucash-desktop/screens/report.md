---
{
  "entities": [
    {
      "entity": "report",
      "shows": [
        "Name",
        "Report type",
        "Options",
        "Saved configuration",
        "Rendered content"
      ],
      "collects": [
        "Name",
        "Options"
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

# Report

Read and adjust an opened working report, then supply save or export inputs.
