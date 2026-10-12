---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Unpost for the posted document or its credit-note case and accept the tax-reset choice.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bill"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product returns the Bill to Unposted, removes its posting Transaction and dependent Splits, resets posting associations, detaches/rebalances settlement links and resets the ordinary entry tax tables to their parent tables when that choice is accepted; existing payments are not promised to disappear.",
      "kind": "product",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Posted",
            "Posting date",
            "Due date",
            "Posting account",
            "Posting transaction",
            "Totals",
            "Outstanding amount",
            "Paid"
          ],
          "from": "Posted",
          "to": "Unposted"
        },
        {
          "entity": "transaction",
          "effect": "removes",
          "from": "Active"
        },
        {
          "entity": "split",
          "effect": "removes",
          "with": "transaction"
        },
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Unsaved changes"
          ]
        },
        {
          "entity": "payment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bill"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product resets the Bill Entry Tax table after clearing the document’s posting association.",
      "kind": "product",
      "entities": [
        {
          "entity": "bill-entry",
          "effect": "changes",
          "facts": [
            "Tax table"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bill"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-invoice.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-invoice.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gncInvoice.c"
    }
  ]
}
---

# Bill/credit case

## Trigger

Choose Unpost for the posted document or its credit-note case and accept the tax-reset choice.

## Outcome

The Product returns the Bill to Unposted, removes its posting Transaction and dependent Splits, resets posting associations, detaches/rebalances settlement links and optionally resets entry tax tables; existing payments are not promised to disappear.

## Edge cases

- Declining tax-table reset preserves the entries’ retained tax-table associations.
