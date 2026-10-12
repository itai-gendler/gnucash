---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Change the selected job’s supported facts and save.",
      "kind": "actor",
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
    },
    {
      "text": "The Product retains the changed Job name, reference, rate, active flag and owner.",
      "kind": "product",
      "entities": [
        {
          "entity": "job",
          "effect": "changes",
          "facts": [
            "Number",
            "Name",
            "Reference",
            "Rate",
            "Active",
            "Owner"
          ]
        },
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Unsaved changes"
          ]
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

# Changed facts

## Trigger

Change the selected job’s supported facts and save.

## Outcome

The Product retains the changed Job name, reference, rate, active flag and owner.
