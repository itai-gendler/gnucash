---
{
  "scope": "Selected desktop accounting and independent CLI report/quote code at b183b507f2db984875d83d31992b2a805f74caea.",
  "method": "Static inventory and entry-point, handler, engine, persistence, configuration and supporting-document inspection.",
  "covered": [
    {
      "description": "Desktop and independent CLI entry, report and quote handlers.",
      "paths": [
        "gnucash/gnucash.cpp",
        "gnucash/gnucash-cli.cpp",
        "gnucash/gnucash-commands.cpp"
      ]
    },
    {
      "description": "Selected book, account, transfer, register, reconciliation, schedule, budget and business controllers.",
      "paths": [
        "gnucash/gnome/",
        "gnucash/gnome-utils/"
      ]
    },
    {
      "description": "Ordinary transaction and document-entry ledger save/control code.",
      "paths": [
        "gnucash/register/ledger-core/"
      ]
    },
    {
      "description": "Selected accounting subject mutations, balances, posting, payment, budget and price engine code.",
      "paths": [
        "libgnucash/engine/"
      ]
    },
    {
      "description": "Schedule instance generation and Finance::Quote result handling.",
      "paths": [
        "libgnucash/app-utils/gnc-sx-instance-model.c",
        "libgnucash/app-utils/gnc-quotes.cpp"
      ]
    },
    {
      "description": "CSV transaction construction, QIF conversion/merge, OFX callbacks and shared matching.",
      "paths": [
        "gnucash/import-export/csv-imp/",
        "gnucash/import-export/qif-imp/",
        "gnucash/import-export/ofx/",
        "gnucash/import-export/import-main-matcher.cpp",
        "gnucash/import-export/import-backend.cpp"
      ]
    },
    {
      "description": "Working-report framework, saved configuration persistence and selected balance-sheet/P&L inputs.",
      "paths": [
        "gnucash/report/report-core.scm",
        "gnucash/report/gnc-report.cpp",
        "gnucash/report/reports/standard/balance-sheet.scm",
        "gnucash/report/reports/standard/balsheet-pnl.scm"
      ]
    },
    {
      "description": "Selected XML/SQL serializers and source save, read-only, locking and DBI provider handling.",
      "paths": [
        "libgnucash/backend/xml/",
        "libgnucash/backend/sql/",
        "libgnucash/backend/dbi/"
      ]
    },
    {
      "description": "Relevant action/form definitions, consumed preferences and declared locales.",
      "paths": [
        "gnucash/ui/",
        "gnucash/gtkbuilder/",
        "gnucash/gschemas/",
        "po/CMakeLists.txt"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Build, package and CI scaffolding without an independent product contract.",
      "paths": [
        "cmake/",
        ".github/",
        "util/ci/",
        "CMakeLists.txt"
      ]
    },
    {
      "description": "Borrowed implementation libraries and purely visual art resources.",
      "paths": [
        "borrowed/",
        "contrib/art/"
      ]
    },
    {
      "description": "Generic test harness templates.",
      "paths": [
        "test-templates/"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "AqBanking setup, protocol downloads and payment submissions.",
      "paths": [
        "gnucash/import-export/aqb/"
      ]
    },
    {
      "description": "Other account/price/business imports, CSV export, log replay and remaining format-specific variants.",
      "paths": [
        "gnucash/import-export/csv-imp/assistant-csv-account-import.c",
        "gnucash/import-export/csv-imp/assistant-csv-price-import.cpp",
        "gnucash/import-export/bi-import/",
        "gnucash/import-export/customer-import/",
        "gnucash/import-export/csv-exp/",
        "gnucash/import-export/log-replay/",
        "gnucash/import-export/qif-imp/",
        "gnucash/import-export/ofx/"
      ]
    },
    {
      "description": "Investment lots, stock operations, capital gains, loans, calculator and book-closing callers.",
      "paths": [
        "gnucash/gnome/assistant-stock-transaction.cpp",
        "gnucash/gnome/assistant-stock-split.c",
        "gnucash/gnome/assistant-loan.cpp",
        "gnucash/gnome/dialog-fincalc.c",
        "gnucash/gnome/dialog-date-close.c",
        "libgnucash/engine/gnc-lot.cpp"
      ]
    },
    {
      "description": "Orders, terms, tax-table lifecycles and jurisdiction-specific tax code.",
      "paths": [
        "gnucash/gnome/dialog-order.c",
        "gnucash/gnome/dialog-billterms.c",
        "gnucash/gnome-utils/dialog-tax-table.c",
        "libgnucash/engine/gncOrder.c",
        "libgnucash/engine/gncBillTerm.c",
        "libgnucash/engine/gncTaxTable.c",
        "gnucash/report/reports/locale-specific/"
      ]
    },
    {
      "description": "Shared/rebilled entry identity, document duplication/reminders and specialized existing-payment editing/removal.",
      "paths": [
        "gnucash/gnome/dialog-invoice.c",
        "gnucash/gnome/dialog-payment.c",
        "gnucash/register/ledger-core/gncEntryLedgerControl.c",
        "libgnucash/engine/gncInvoice.c",
        "libgnucash/engine/gncOwner.c"
      ]
    },
    {
      "description": "Register clipboard, standalone split CRUD, repair, combined-register mutation and broader destruction combinations.",
      "paths": [
        "gnucash/gnome/gnc-plugin-page-register.cpp",
        "gnucash/register/ledger-core/split-register.c",
        "gnucash/register/ledger-core/split-register-control.cpp",
        "libgnucash/engine/Scrub.cpp"
      ]
    },
    {
      "description": "Linked-document and import-map lifecycle editors.",
      "paths": [
        "gnucash/gnome/dialog-doclink.c",
        "gnucash/gnome/dialog-imap-editor.c"
      ]
    },
    {
      "description": "Full book-option/preference editing, autosave, recovery and legacy conversion.",
      "paths": [
        "gnucash/gnome-utils/dialog-options.cpp",
        "gnucash/gnome-utils/dialog-preferences.c",
        "gnucash/gnome-utils/gnc-autosave.c",
        "libgnucash/backend/xml/io-gncxml-v1.cpp"
      ]
    },
    {
      "description": "Remaining report formulas, composite dashboards, stylesheets and printing specializations.",
      "paths": [
        "gnucash/report/reports/",
        "gnucash/report/stylesheets/",
        "gnucash/gnome/dialog-report-column-view.cpp",
        "gnucash/gnome/dialog-print-check.c"
      ]
    },
    {
      "description": "Python/Guile bindings and example-service behavioral contracts.",
      "paths": [
        "bindings/",
        "contrib/"
      ]
    },
    {
      "description": "Exhaustive backend connection, concurrent-write, locking, upgrade and recovery branches.",
      "paths": [
        "libgnucash/backend/dbi/",
        "libgnucash/backend/sql/",
        "libgnucash/backend/xml/"
      ]
    }
  ],
  "limitations": [
    {
      "description": "Reconciliation Finish callback has a nonzero confirmation branch without an established supported normal desktop entry route.",
      "paths": [
        "gnucash/gnome/window-reconcile.cpp"
      ]
    }
  ]
}
---

# Coverage
