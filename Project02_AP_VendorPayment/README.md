Project 03 – Accounts Payable (AP) | Dynamics 365 Finance

Status: In Progress
Module: Accounts Payable
Cycle: Procure-to-Pay (P2P)

📌 Overview

This project focuses on building the complete Accounts Payable (AP) workflow inside Microsoft Dynamics 365 Finance.
The goal is to configure vendor-related master data and execute the full Procure-to-Pay cycle, including purchasing, receiving goods, invoicing, and vendor payments.

This project connects with my previous AR projects (Project 01 & 02) to form a full financial cycle for my D365 Finance Functional Consultant portfolio.

🎯 Objectives

Configure vendor master data: groups, posting profiles, payment terms/methods, bank accounts

Execute a real P2P scenario:

Create Purchase Order

Product Receipt (Inventory update)

Vendor Invoice (Financial update)

Invoice Matching

Vendor Payment & Settlement

Validate subledger + general ledger postings

Prepare reusable documentation for GitHub & LinkedIn

🔄 Scope (High-Level)

Vendor setup (ABC Supplier)

PO for raw materials

Product receipt posting

AP invoice posting

Payment journal execution

Voucher review & accounting flow
/////////////////////
**PROJECT 02 — ACCOUNTS PAYABLE (AP) END-TO-END

DYNAMICS 365 FINANCE – P2P CYCLE**

📌 Introduction

This project demonstrates a complete Accounts Payable (AP) cycle in Microsoft Dynamics 365 Finance, covering the full Procure-to-Pay (P2P) process.

This is Project #02 of my D365 Finance Portfolio, following:

Project 01 – AR Free Text & Sales Order Invoice

Project 01.1 – Customer Payments & Settlement (AR)

Together, they form a full-cycle Finance workflow across AR + AP.

🎯 Project Goal

The objective of this project is to:

Understand the complete AP lifecycle in D365 Finance

Configure vendors, payment terms, methods, posting profiles

Execute the full Procure-to-Pay (P2P) scenario

Analyze the accounting entries (subledger + general ledger)

🔄 Business Scenario – Procure-to-Pay (P2P)

The company needs to purchase raw materials from a supplier (ABC Supplier) and go through:

Vendor setup
Purchase order creation
Receiving the goods
Vendor invoice
Vendor payment

This project simulates a realistic procurement workflow used by Finance teams worldwide.

🧩 Phase 1 — AP Fundamentals (Concepts)
✔ What is Accounts Payable (AP)?
    AP represents liabilities the company owes to suppliers for goods or services received.

✔ Procure-to-Pay (P2P) Stages
    Purchase order
    Product receipt
    Vendor invoice
    Payment
    GL posting

✔ 3-Way Matching
    Quantity match (PO vs Receipt)
    Price match (PO vs Invoice)
    Receipt match (Receipt vs Invoice)

✔ AP vs AR
    Accounts Payable	Accounts Receivable
    Money going out	Money coming in
    Vendor invoices	Customer invoices
    Liability account	Asset account


 Phase 2 — Vendor Master Setup
2.1 Vendor Group

Navigation: Accounts payable → Setup → Vendors → Vendor groups
Vendor group: DOMESTIC
Posting profile: AP-Domestic
Terms of payment (default): Net 30

📷 Phase 2.1 – Selecting Vendor Group (10 – Parts Vendors)
📷 Phase 2.1 – Vendor Group Setup.png

2.2 Posting Profiles

Navigation: Accounts payable → Setup → Posting → Posting profiles
Configured:
Summary account (AP): 3001xx
Accrued purchases: 200190
Prepayments: Optional

📷 Phase 2.2 – Posting Profiles  set up

2.3 Payment Terms

Navigation: Accounts receivable → Setup → Payment → Terms of payment
Net 30

📷 Phase 2.3 – Payment Terms set.png

2.4 Payment Method

Navigation: Accounts payable → Setup → Payment → Methods of payment
Method: BANK
Format: Electronic
Bank account required

📷 Phase 2.4 – Vendor Payment Method Setup.png

2.5 Vendor Bank Account

Navigation: Accounts payable → Vendors → All vendors → Bank accounts
IBAN (Test)
Bank group
Currency: USD

📷 Phase 2.5 – create Vendor Bank Account.png

2.6 Create Vendor

Vendor account: V-0001 – ABC Supplier
Details completed: Address, Payment, Invoice, Bank, Tax.

📷 Phase 2.6 – create Vendor  (ABC Supplier).png

  Phase 3 — Procure-to-Pay Execution
3.1 Purchase Order (PO)

Navigation: Procurement and sourcing → Purchase orders → All purchase orders → New
Vendor: V-0001
Item: M0001
Quantity: 10
Unit price: 50

📷 Phase 3.1 – Purchase Order Creation for Vendor ABC Supplier.png

3.2 Product Receipt

Navigation: Purchase order → Receive → Product receipt
Receipt number: PR-0001
Quantity: 10
        ➤ Accounting (Voucher)
        DR 140100 – Inventory
        CR 200190 – Accrued Purchases

📷 Phase 3.2 - PO Line add.png

3.3 Invoice Matching

Match status: PASSED
No price/quantity discrepancies
Invoice number: ABC-126

📷 Phase 3.3 – PO confirmation.png

3.4 Vendor Invoice Posting

Navigation: Purchase order → Invoice → Invoice → Post

    ➤ Accounting (Voucher)
    DR 200190 – Accrued Purchases (Reversal)
    CR 3001xx – Vendor AP

📷 Phase 3.4.1 - Product receipt prior to posting.png
📷 Phase 3.4.2 - Product receipt after posting.png
📷 Phase 3.4.3 -Voucher of Product Receipt.png

3.5 Vendor Payment

Navigation: Accounts payable → Payments → Payment journal
Account: V-0001
Credit: 536.25 USD
Offset: Bank
Settled with invoice ABC-126

    ➤ Accounting (Voucher)
    DR 3001xx – Vendor (AP)
    CR 110110 – Bank Account

📷 Phase 3.5 – Invoice Matching Completed.png

🧾 Phase 4 — Summary of Accounting Flow
✔ Product Receipt
    Inventory ↑
    Accrued Purchases ↑

✔ Vendor Invoice
    Accrued Purchases ↓
    Vendor Liability ↑

✔ Vendor Payment
    Vendor Liability ↓
    Bank ↓

 This is exactly how the subledger integrates with the General Ledger in D365 Finance.

📚 MB-310 Insights
Posting profiles determine AP accounting behavior
Matching policies prevent incorrect posting
Product receipt creates physical updates
Vendor invoice creates financial updates
Settlement removes open transactions

📘 Lessons Learned
How to configure vendor master data
Importance of payment terms & posting profiles
Understanding 3-way matching
How accruals work in P2P
Full accounting visibility from PO → Receipt → Invoice → Payment
How to analyze vouchers and settlements

📂 Repository Structure
Project03-AccountsPayable/
│
├── README.md
├── Phase1-APBasics/
├── Phase2-VendorSetup/
├── Phase3-ProcureToPay/
├── Phase4-VoucherAnalysis/
├── Screenshots/
│   ├── VendorGroup.png
│   ├── PostingProfile.png
│   ├── PO.png
│   ├── ProductReceipt.png
│   ├── InvoiceVoucher.png
│   ├── PaymentVoucher.png
│   └── MatchStatus.png
└── CheatSheet-AP.pdf

🏁 Conclusion

This project completes the full Accounts Payable cycle in Dynamics 365 Finance and connects seamlessly with Projects 01 & 02 (AR Cycle), forming a complete end-to-end Finance workflow.
