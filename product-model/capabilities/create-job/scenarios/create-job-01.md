---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Supply a name, customer/vendor owner and valid or blank rate, then save.",
      "kind": "actor",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "vendor",
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
      "text": "The Product creates the Job with Number, Name, Reference, Rate, Active and Owner, generating a Number when its input is blank.",
      "kind": "product",
      "entities": [
        {
          "entity": "job",
          "effect": "creates",
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

# Valid owner-associated Job

## Trigger

Supply a name, customer/vendor owner and valid or blank rate, then save.

## Outcome

The Product creates the Job with Number, Name, Reference, Rate, Active and Owner, generating a Number when its input is blank.
