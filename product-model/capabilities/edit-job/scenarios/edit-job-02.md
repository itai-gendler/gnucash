---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit a missing name/owner or invalid rate while editing.",
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
      "text": "The Product requests corrected Job inputs and leaves the invalid changes unaccepted.",
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

# Invalid facts

## Trigger

Submit a missing name/owner or invalid rate while editing.

## Outcome

The Product requests corrected Job inputs and leaves the invalid changes unaccepted.
