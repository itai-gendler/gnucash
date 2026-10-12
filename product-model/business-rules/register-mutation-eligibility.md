---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "enter-transaction",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-transaction",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
    },
    {
      "type": "capability",
      "id": "duplicate-transaction",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
    },
    {
      "type": "capability",
      "id": "delete-transaction",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
    },
    {
      "type": "capability",
      "id": "void-transaction",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
    },
    {
      "type": "capability",
      "id": "unvoid-transaction",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
    },
    {
      "type": "capability",
      "id": "add-reversing-transaction",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
    },
    {
      "type": "capability",
      "id": "change-split-reconciliation-status",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-register.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-split-reg.c#gnc_split_reg_determine_read_only"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/split-register.c#gnc_split_register_save"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Transaction.cpp"
    }
  ]
}
---

# Register mutation actions retain their inspected eligibility checks

Book and register read-only checks, selected account/aggregate placeholder eligibility, explicit transaction protection, operation-specific date checks and unreconcile warnings govern the inspected actions.
