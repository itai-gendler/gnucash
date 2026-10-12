---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-job.c#gnc_job_verify_ok"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gncJob.c"
    }
  ],
  "relations": [
    {
      "entity": "invoice",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "bill",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Job

An independently searched job associated with a customer or vendor.

## Information kept

- **Number** — The job number.
- **Name** — The job’s displayed name.
- **Reference** — The job’s billing reference.
- **Rate** — The retained job rate.
- **Active** — Whether the job is active.
- **Owner** — The associated customer or vendor.
