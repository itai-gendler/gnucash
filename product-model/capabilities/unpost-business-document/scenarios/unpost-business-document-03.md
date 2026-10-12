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
          "place": "gnucash-desktop::expense-voucher"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product returns the Expense Voucher to Unposted, removes its posting Transaction and dependent Splits, resets posting associations, detaches/rebalances settlement links and optionally resets entry tax tables; existing payments are not promised to disappear.",
      "kind": "product",
      "entities": [
        {
          "entity": "expense-voucher",
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
          "place": "gnucash-desktop::expense-voucher"
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

# Voucher/credit case

## Trigger

Choose Unpost for the posted document or its credit-note case and accept the tax-reset choice.

## Outcome

The Product returns the Expense Voucher to Unposted, removes its posting Transaction and dependent Splits, resets posting associations, detaches/rebalances settlement links and optionally resets entry tax tables; existing payments are not promised to disappear.
