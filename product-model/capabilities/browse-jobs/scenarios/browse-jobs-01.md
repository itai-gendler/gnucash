---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Search jobs using owner, identity, reference or active criteria.",
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
          "place": "gnucash-desktop::jobs"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product presents Job number, name, owner, reference and rate for the selected results.",
      "kind": "product",
      "entities": [
        {
          "entity": "job",
          "effect": "reads",
          "facts": [
            "Number",
            "Name",
            "Reference",
            "Rate",
            "Active",
            "Owner"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::jobs"
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

# Owner-associated search/results

## Trigger

Search jobs using owner, identity, reference or active criteria.

## Outcome

The Product presents Job number, name, owner, reference and rate for the selected results.
