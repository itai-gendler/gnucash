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
      ],
      "collects": [
        "Number",
        "Name",
        "Reference",
        "Rate",
        "Active",
        "Owner"
      ]
    },
    {
      "entity": "customer",
      "shows": [
        "Number",
        "Name"
      ]
    },
    {
      "entity": "vendor",
      "shows": [
        "Number",
        "Name"
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

# Job

Work with one owner-associated job.
