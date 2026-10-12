---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit a missing name/owner or invalid rate.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::job"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product requests corrected Job inputs without accepting the invalid record.",
      "kind": "product",
      "entities": [
        {
          "entity": "job",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::job"
        }
      },
      "actor": "user"
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

# Invalid name/owner/rate

## Trigger

Submit a missing name/owner or invalid rate.

## Outcome

The Product requests corrected Job inputs without accepting the invalid record.
