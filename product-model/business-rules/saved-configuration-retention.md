---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "saved-report-configuration",
      "effect": "creates"
    },
    {
      "type": "entity",
      "id": "saved-report-configuration",
      "effect": "changes"
    },
    {
      "type": "entity",
      "id": "saved-report-configuration",
      "effect": "removes"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/report/report-core.scm#gnc:report-to-template"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/report/report-core.scm#gnc:save-all-reports"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/report/gnc-report.cpp#gnc_saved_reports_write_to_file"
    }
  ]
}
---

# Saved report configurations persist independently from book accounting

New/replaced identity is retained separately from Book data; failed file writes need not roll back memory changes.
