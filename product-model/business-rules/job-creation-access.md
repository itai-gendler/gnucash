---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "job",
      "effect": "creates",
      "contexts": [
        {
          "place": "gnucash-desktop::job"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Session access",
          "is": "Writable",
          "entity": "book"
        }
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

# Only the User creates job records through writable business entry

Only the User creates job records through writable business entry.
