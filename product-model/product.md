---
{
  "id": "gnucash",
  "summary": "Personal and small-business double-entry accounting with desktop books, reconciliation, business documents and independently offered CLI reports and quotes.",
  "category": "accounting",
  "license": "GPL-2.0-or-later",
  "languages": [
    "en",
    "ar",
    "as",
    "az",
    "bg",
    "brx",
    "ca",
    "cs",
    "da",
    "de",
    "doi",
    "el",
    "en-AU",
    "en-GB",
    "en-NZ",
    "es",
    "es-NI",
    "et",
    "eu",
    "fa",
    "fi",
    "fr",
    "gu",
    "he",
    "hi",
    "hr",
    "hu",
    "id",
    "it",
    "ja",
    "kn",
    "ko",
    "kok",
    "kok-Latn",
    "ks",
    "lt",
    "lv",
    "mai",
    "mk",
    "mni",
    "mni-Beng",
    "mr",
    "nb",
    "ne",
    "nl",
    "pl",
    "pt",
    "pt-BR",
    "ro",
    "rw",
    "sk",
    "sr",
    "sv",
    "ru",
    "ta",
    "te",
    "tr",
    "uk",
    "ur",
    "vi",
    "zh-CN",
    "zh-TW"
  ],
  "limitations": [
    "A book is used by one session at a time; when its lock is held elsewhere, GnuCash warns and offers to open it read-only.",
    "Every committed Transaction balances; any remainder goes to an Imbalance Split instead of leaving the Transaction unbalanced.",
    "Online quotes come from Finance::Quote, an optional Perl module installed separately.",
    "Due scheduled transactions are created only when Since Last Run runs in the desktop, on opening a book or on request."
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnucash.cpp#scm_run_gnucash"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnucash-cli.cpp#GnucashCli::start"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "po/CMakeLists.txt#ALL_LINGUAS"
    }
  ]
}
---

# GnuCash

GnuCash keeps personal and small-business double-entry accounting books. People organize accounts, record transactions, reconcile statements, schedule accounting, prepare budgets and business documents, apply payments, retain securities and prices, import accounting and read reports. The desktop and CLI expose their independently specified workflows. Online quotes use Finance::Quote when available.

## Intent

GnuCash lets individuals and small businesses keep their own double-entry accounting: everyday transactions, reconciliation, budgets, investments, and customer and vendor business, in books they hold themselves.
