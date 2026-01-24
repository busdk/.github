# Business Software Development Kit

**BuSDK** is a modular, CLI-first toolkit for **small-business accounting and bookkeeping**, built around **open, long-lived formats** and **transparent, auditable operations**.

All business data lives in **UTF-8 CSV files** with **Frictionless Data Table Schema (JSON)** as the authoritative source of typing and constraints, intended to be maintained inside a **Git repository** for a tamper-evident history of every change. The system favors **simple primitives**, **deterministic behavior**, and workflows that work equally well for humans and automated agents.

BuSDK aims to ship as a suite of focused subcommand binaries invoked through the core `bus` dispatcher: **bus-accounts**, **bus-attachments**, **bus-bank**, **bus-budget**, **bus-entities**, **bus-invoices**, **bus-journal**, **bus-period**, **bus-reconcile**, **bus-reports**, **bus-validate**, and **bus-vat**.
