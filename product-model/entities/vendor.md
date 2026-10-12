---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-vendor.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gncVendor.c"
    }
  ],
  "relations": [
    {
      "entity": "bill",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "job",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ],
  "domain": "vendor"
}
---

# Vendor

A vendor addressed independently through business forms and searches.

## Information kept

- **Number** — The vendor number; a blank number is generated on save.
- **Name** — The vendor’s company name.
- **Contact** — Contact name, address, phone, fax and email details.
- **Active** — Whether the vendor is active.
- **Currency** — The currency used for the vendor’s business accounting.
- **Terms** — The selected billing terms.
- **Tax settings** — The tax inclusion and tax-table settings.
- **Notes** — Notes about the vendor.
- **Open balance** — The derived unsettled vendor accounting balance.
