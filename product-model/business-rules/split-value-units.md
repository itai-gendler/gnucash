---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "split",
      "facts": [
        "Amount",
        "Value"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Split.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/split-register-model-save.c"
    }
  ]
}
---

# Split amount and value use their accounting units

Amount uses Account commodity; Value uses Transaction currency, with applicable precision.
