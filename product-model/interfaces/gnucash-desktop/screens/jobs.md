---
{
  "entities": [
    {
      "entity": "job",
      "shows": [
        "Number",
        "Name",
        "Reference",
        "Rate",
        "Active",
        "Owner"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-job.c#gnc_job_verify_ok"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-business.c"
    }
  ]
}
---

# Jobs

Search and read jobs with their associated owner, billing reference and rate.
