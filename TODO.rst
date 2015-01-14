An overview of the migration of banking functionality from 7.0 and
previous to 8.0 and future.

bank-statement-import
=====================

General:

* Migrate 9.0 Odoo framework to 8.0 - Being tested
* Provide improvements on framework to enable import - Being tested
* Create decorator function to easily migrate old parsers - Being tested
* Wizard to link transaction to new or existing partner
* Check and lookup IBAN account numbers
* Migration of pre 8.0 banking import files, statements and transactions
* Make it possible to import statement files that contain info for multiple
  bank accounts
* Support zip files containing multiple import files
* Autonumber imported transactions

Parsers to be migrated:

* camt.053 - Done
* mt940 base
* mt940 abnamro
* mt940 ing
* fi_patu
* girotel
* ing
* multibank
* triodos
* hsbc

It has been agreed to do the other parsers if customers request them (and
provide funding, possibly by grouping customers to share costst).

bank-statement-reconcile
========================

* Use transaction date instead of statement date to determine
  period in generated move
* Confirm separate transactions - instead of only the whole statement
  in one go - Ready for testing
* Select vat percentage for transaction - actually this is already part
  of the banking framework out of the box. Nothing todo?
* Reconcile with open invoices
* Reconcile with existing move lines (withouth invoice)
* Partial reconciliation
* Allow cancellation of single transactions, withouth installing
  account_cancel
* Automatically reconcile banking cost transactions
* Actually reconcile moves created from transactions (you might think the
  standard button 'Reconcile' would do this, but apparently not).

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

