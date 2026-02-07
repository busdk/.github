# Business Development Kit (BusDK)

**BusDK** is a modular, Git-native, CLI-first toolkit for running a business — built on open, long-lived formats and transparent, auditable workflows, designed to work equally well for humans and AI agents.

A Bus workspace lives in a **Git repository**. Business data is stored as **UTF-8 CSV datasets** and validated with **Frictionless Table Schema (JSON)** as the authoritative source of typing, constraints, and cross-table integrity. The system focuses on **small primitives**, **deterministic behavior**, and workflows that remain inspectable and reproducible over time.

BusDK is currently **pre-release** and under active development: interfaces, schemas, and file conventions may still change, and not all modules are feature-complete. The long-term goal is a coherent suite of modules invoked through the `bus` command (see https://github.com/busdk/busdk). Specifications and documentation live at https://docs.busdk.com. For deeper architectural background, see the BuSDK design document.

## Business Model

BusDK will be distributed as free, ready-to-run CLI binaries, so anyone can download and use the tools immediately. The full source code and documentation are available to subscribers: during an active subscription you get access to the latest repositories, updates, and release history. All subscriber-accessible code and documentation are provided under the MIT License, so once you have access you may use, modify, and redistribute them under MIT terms. Subscriptions fund ongoing development, maintenance, and timely updates, and provide the simplest official way to stay current with BusDK releases.

## Modules (subcommands)

- [bus-init](https://docs.busdk.com/modules/bus-init) — Workspace scaffolding: initialize a new BusDK workspace layout (e.g. `fi`) by creating the required directories, baseline schema-validated CSV datasets, and a root `datapackage.json`, deterministically and without running any git or network operations.
- [bus-accounts](https://docs.busdk.com/modules/bus-accounts) — Chart of Accounts / account master data for BusDK workspaces.
- [bus-assets](https://docs.busdk.com/modules/bus-assets) — Fixed asset register in schema-validated CSV, including depreciation schedules, depreciation postings for `bus-journal`/`bus-period`, and audit-friendly acquisition/disposal reporting.
- [bus-attachments](https://docs.busdk.com/modules/bus-attachments) — Document archive for receipts and supporting files, with Frictionless-schema CSV metadata so other modules can link records to verifiable, Git-friendly attachments.
- [bus-bank](https://docs.busdk.com/modules/bus-bank) — Bank statement import and reconciliation: parse bank CSVs, match transactions to invoices/accounts, and emit balanced journal entries into the append-only ledger.
- [bus-budget](https://docs.busdk.com/modules/bus-budget) — Budgeting: manage schema-validated CSV budgets and generate budget-vs-actual variance reporting from the ledger.
- [bus-entities](https://docs.busdk.com/modules/bus-entities) — Durable IDs for customers, vendors, banks, and authorities (CSV + Frictionless schemas), with validation and matching hints (e.g., names, IDs, IBAN) for reliable cross-module linking.
- [bus-inventory](https://docs.busdk.com/modules/bus-inventory) — Inventory and stock records as schema-validated CSV: items, stock movements, stocktakes, and inventory valuation support that can produce deterministic postings for `bus-journal`/`bus-period`.
- [bus-invoices](https://docs.busdk.com/modules/bus-invoices) — Sales and purchase invoices as Frictionless CSV datasets, with deterministic validation, CLI tooling, and optional auto-posting to `bus-journal`.
- [bus-journal](https://docs.busdk.com/modules/bus-journal) — Double-entry journal for recording and validating ledger transactions (CSV + Frictionless Table Schema).
- [bus-loans](https://docs.busdk.com/modules/bus-loans) — Loan register, drawdowns, and amortization schedules.
- [bus-payroll](https://docs.busdk.com/modules/bus-payroll) — Payroll runs as schema-validated datasets: earnings/deductions and employer liabilities, with deterministic journal postings and audit-friendly payroll summaries.
- [bus-period](https://docs.busdk.com/modules/bus-period) — Open, close, and lock accounting periods; generate closing entries and next-period opening balances to keep closed periods immutable.
- [bus-reconcile](https://docs.busdk.com/modules/bus-reconcile) — Bank reconciliation: match imported bank transactions to invoices or journal entries, allocate payments (partials/splits/fees), and record reconciled state as append-only CSV with Frictionless schemas.
- [bus-reports](https://docs.busdk.com/modules/bus-reports) — Reporting: generate trial balance, general ledger, profit & loss, and balance sheet, with integrity checks and text/CSV/JSON outputs.
- [bus-validate](https://docs.busdk.com/modules/bus-validate) — Workspace validation: check each CSV against its Frictionless schema, verify cross-table integrity, and enforce core double-entry invariants.
- [bus-vat](https://docs.busdk.com/modules/bus-vat) — Finnish VAT (ALV): compute VAT from Bus workspaces, validate VAT code/rate mappings, reconcile invoice VAT vs ledger postings, and produce period summaries and export files for reporting and archiving.
- [bus-filing](https://docs.busdk.com/modules/bus-filing) — Filing target dispatcher invoked as `bus filing …`, discovering and executing `bus-filing-<target>` binaries.
- [bus-filing-prh](https://docs.busdk.com/modules/bus-filing-prh) — PRH filing target for `bus filing prh …`, generating PRH-ready financial statement export bundles from a closed, validated workspace.
- [bus-filing-vero](https://docs.busdk.com/modules/bus-filing-vero) — Vero filing target for `bus filing vero …`, generating Vero-ready tax filing export bundles from a closed, validated workspace.
- [bus-pdf](https://docs.busdk.com/modules/bus-pdf) — Generic PDF rendering target for `bus pdf …`, generating deterministic PDF documents from templates and structured data, designed to be used by other modules (for example `bus invoices pdf …`) to produce auditable, reproducible document artifacts such as Finnish A4 invoices.
