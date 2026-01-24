# Business Development Kit (BusDK)

**Bus** is a modular, Git-native, CLI-first toolkit for running a business — built on open, long-lived formats and transparent, auditable workflows, designed for humans and AI agents.

A BusDK workspace is designed to live in a **Git repository**, where business data is stored as **UTF-8 CSV datasets** and validated using **Frictionless Data Table Schema (JSON)** as the authoritative source of typing and constraints. The focus is on **simple primitives**, **deterministic behavior**, and workflows that work equally well for humans and automated agents.

BusDK is currently **pre-release** and under active development: interfaces, schemas, and file conventions may still change, and not all modules are feature-complete. The long-term goal is a suite of focused subcommand binaries invoked through the core `bus` dispatcher (see also: https://github.com/busdk/bus). Specifications and documentation live in https://github.com/busdk/docs.

## Modules (subcommands)

- [bus-accounts](https://github.com/busdk/bus-accounts) — Chart of Accounts / account master data for BusDK workspaces.
- [bus-assets](https://github.com/busdk/bus-assets) — Fixed asset register in schema-validated CSV, including depreciation schedules, depreciation postings for `bus-journal`/`bus-period`, and audit-friendly acquisition/disposal reporting.
- [bus-attachments](https://github.com/busdk/bus-attachments) — Document archive for receipts and supporting files, with Frictionless-schema CSV metadata so other modules can link records to verifiable, Git-friendly attachments.
- [bus-bank](https://github.com/busdk/bus-bank) — Bank statement import and reconciliation: parse bank CSVs, match transactions to invoices/accounts, and emit balanced journal entries into the append-only ledger.
- [bus-budget](https://github.com/busdk/bus-budget) — Budgeting: manage schema-validated CSV budgets and generate budget-vs-actual variance reporting from the ledger.
- [bus-entities](https://github.com/busdk/bus-entities) — Durable IDs for customers, vendors, banks, and authorities (CSV + Frictionless schemas), with validation and matching hints (e.g., names, IDs, IBAN) for reliable cross-module linking.
- [bus-inventory](https://github.com/busdk/bus-inventory) — Inventory and stock records as schema-validated CSV: items, stock movements, stocktakes, and inventory valuation support that can produce deterministic postings for `bus-journal`/`bus-period`.
- [bus-invoices](https://github.com/busdk/bus-invoices) — Sales and purchase invoices as Frictionless CSV datasets, with deterministic validation, CLI tooling, and optional auto-posting to `bus-journal`.
- [bus-journal](https://github.com/busdk/bus-journal) — Double-entry journal for recording and validating ledger transactions (CSV + Frictionless Table Schema).
- [bus-payroll](https://github.com/busdk/bus-payroll) — Payroll runs as schema-validated datasets: earnings/deductions and employer liabilities, with deterministic journal postings and audit-friendly payroll summaries.
- [bus-period](https://github.com/busdk/bus-period) — Open, close, and lock accounting periods; generate closing entries and next-period opening balances to keep closed periods immutable.
- [bus-reconcile](https://github.com/busdk/bus-reconcile) — Bank reconciliation: match imported bank transactions to invoices or journal entries, allocate payments (partials/splits/fees), and record reconciled state as append-only CSV with Frictionless schemas.
- [bus-reports](https://github.com/busdk/bus-reports) — Reporting: generate trial balance, general ledger, profit & loss, and balance sheet, with integrity checks and text/CSV/JSON outputs.
- [bus-validate](https://github.com/busdk/bus-validate) — Workspace validation: check each CSV against its Frictionless schema, verify cross-table integrity, and enforce core double-entry invariants.
- [bus-vat](https://github.com/busdk/bus-vat) — Finnish VAT (ALV): compute VAT from Bus workspaces, validate VAT code/rate mappings, reconcile invoice VAT vs ledger postings, and produce period summaries and export files for reporting and archiving.
- [bus-filing](https://github.com/busdk/bus-filing) — Filing target dispatcher invoked as `bus filing …`, discovering and executing `bus-filing-<target>` binaries.
- [bus-filing-prh](https://github.com/busdk/bus-filing-prh) — PRH filing target for `bus filing prh …`, generating PRH-ready financial statement export bundles from a closed, validated workspace.
- [bus-filing-vero](https://github.com/busdk/bus-filing-vero) — Vero filing target for `bus filing vero …`, generating Vero-ready tax filing export bundles from a closed, validated workspace.
