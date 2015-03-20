An overview of the migration of banking functionality from 7.0 and
previous to 8.0 and future.

bank-statement-import
=====================

General:

* Migrate 9.0 Odoo framework to 8.0 - Being tested
* Provide improvements on framework to enable import - Being tested
* Create decorator function to easily migrate old parsers - Being tested
* Check and lookup IBAN account numbers - Being tested
* Migration of pre 8.0 banking import files, statements and transactions
* Make it possible to import statement files that contain info for multiple
  bank accounts - Being tested
* Support zip files containing multiple import files - Being tested
* Autonumber imported transactions - Being tested

Parsers to be migrated:

* camt.053 - Done
* mt940 - Done
* mt940 abnamro
* mt940 - Done
* fi_patu
* girotel
* ing
* multibank
* triodos
* hsbc

It has been agreed to do the other parsers if customers request them (and
provide funding, possibly by grouping customers to share costst).

Everything is on one branch of one repo:
Repo: https://github.com:nl66278/bank-statement-import.git
Branch: 8.0_import_parsers

bank-statement-reconcile
========================

* Use transaction date instead of statement date to determine
  period in generated move - Being developed
  Repo: https://github.com:nl66278/bank-statement-reconcile.git
  Branch: 8.0_transaction_period_fix_therp
* Wizard to link transaction to new or existing partner - Being tested
  Repo: https://github.com:nl66278/bank-statement-reconcile.git
  Branch: 8.0_link_partner_therp
* Confirm separate transactions - instead of only the whole statement
  in one go. Including cancelling of single transactions - Ready for testing
  Repo: https://github.com/bas-solutions/bank-statement-reconcile.git
  Branch: bank_statement_line_confirm
* Improve standard reconcile with open invoices.
* Improve standard reconcile with existing move lines
* Automatically reconcile banking cost transactions

A note on terminology
---------------------
The reconcile process actually encompasses two things:
- Something that really should be called "matching" - and will be called that
  in Odoo 9.0: that is linking bank statement lines (transactions) to journal
  entries (account moves). These moves can be pre-existing, or can be created
  on the fly when needed.
- "Reconciliation" proper is the act of linking debit to credit transactions,
  mostly for marking incoming or outgoing invoice payments due als wholly or
  partially paid.
Of course reconciliation and matching are usually closely linked, but
outstanding payments can also be reconciled with debt writeoffs or credit
invoice moves.

A bank statement line will lead to 2 account move lines, one for the bank
account, one to debit or credit account (usually). Only the account move line
for the debit or credit account will be involved in the reconciliation.

bank-payment
============
* Module to maintain direct debit mandates - Done
* Module to maintain SEPA direct debit mandates - Done
* Module to create SEPA payment file - Done
* Module to create transfer moves when exporting direct debit files - ??
  This is the old account_banking_payment ??

More information
================
https://lists.launchpad.net/banking-addons-driver
https://docs.google.com/spreadsheets/d/1R77W6xFFexM247mUen3N9uFacX-OZYtGcyP6HGgRjjU/edit?pli=1#gid=0

