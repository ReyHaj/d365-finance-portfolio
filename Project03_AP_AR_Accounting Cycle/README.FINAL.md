*** Microsoft Dynamics 365 Finance End-to-End Financial Cycles Project (Phase 1–9)
** Project Overview

    This project demonstrates a complete end-to-end financial lifecycle implemented in Microsoft Dynamics 365 Finance & Operations, covering transactional processing, accounting validation, reconciliation, reporting, and cash flow analysis.
    The project is designed to simulate real-world finance operations and reflect the responsibilities of a Dynamics 365 Finance Functional Consultant, aligned with MB-310 exam objectives.

** Project Objectives

    Implement full Accounts Payable (AP) and Accounts Receivable (AR) cycles
    Validate financial data accuracy through reporting and reconciliation
    Ensure General Ledger integrity
    Reconcile Inventory value with accounting
    Analyze cash flow and liquidity at CFO level

** Project Structure
    
    d365-finance-portfolio/
    │
    ├── Phase01-03_Transactional_Cycles/
    ├── Phase04-05_Payments_and_Bank/
    ├── Phase06_Financial_Reporting/
    ├── Phase07_Trial_Balance/
    ├── Phase08_Inventory_Reconciliation/
    ├── Phase09_Cash_Flow_Analysis/
    └── README.md

🟦 Phase 1–3 – Transactional Cycles (AP & AR Foundations)
Scope

    Vendor and Customer master data setup
    Vendor invoices (PO-based & non-PO)
    Customer invoices (Free Text & Sales Order)
    Subledger postings generation
    Outcome
    Operational AP & AR transactions correctly created
    Subledger postings ready for validation

* Key Screenshots

      Vendor_Master_Setup.png
      Customer_Master_Setup.png
      Vendor_Invoice_Posted.png
      Customer_Invoice_Posted.png

🟦 Phase 4–5 – Payments & Bank Operations
Scope

    Vendor Payment Journals
    Customer Payment Journals
    Check payments
    Bank posting integration
    Outcome
    End-to-end cash movements recorded
    AP & AR balances updated
    📸 Key Screenshots
    VendorPayment_Journal_Posted.png
    CustomerPayment_Journal_Posted.png
    Bank_Transaction_Posting.png

🟦 Phase 6 – Financial Reporting (AP + AR + GL)
Purpose
    
    Ensure that all operational transactions are accurately reflected in financial reports and the General Ledger.
    Activities
    Reviewed Vendor balances and AP transactions
    Reviewed Customer balances and AR transactions
    Analyzed AP & AR Aging reports
    Traced subledger transactions to GL vouchers
    Outcome
    Subledger-to-ledger consistency validated
    Financial data confirmed accurate
    📸 Key Screenshots
    AP_Vendor_Transactions.png
    AR_Customer_Transactions.png
    AP_Aging_Report.png
    AR_Aging_Report.png
    GL_Voucher_Details.png

🟦 Phase 7 – Trial Balance Validation
Purpose
    
    Validate accounting integrity at General Ledger level.
    Activities
    Generated Trial Balance for selected fiscal period
    Verified Debit = Credit
    Reviewed key account balances (Bank, AP, AR, Inventory)
    Drilled down to voucher transactions
    Outcome
    Balanced General Ledger
    Audit-ready financial data
    📸 Key Screenshots
    TrialBalance_Overview.png
    TrialBalance_ByAccount.png
    TrialBalance_Voucher_Drilldown.png

🟦 Phase 8 – Inventory Value Reconciliation
Purpose

    Ensure inventory valuation accuracy between Inventory subledger and General Ledger.
    Activities
    Generated Inventory Value Report
    Reviewed inventory quantities and values
    Reconciled inventory balances with GL accounts
    Verified clearing of accrued purchases
    Outcome
    Inventory subledger reconciled with GL
    Accurate inventory asset valuation
    📸 Key Screenshots
    InventoryValue_Report.png
    InventoryValue_Summary.png
    Inventory_GL_Reconciliation.png
    AccruedPurchases_Clearing.png

🟦 Phase 9 – Cash Flow & Financial Analysis (CFO-Level)
Purpose

    Translate accounting data into liquidity and cash intelligence.

🔹 Phase 9.1 – Vendor Payment & Bank Validation

    Activities
    Verified Vendor Payment voucher posting
    Confirmed Bank Statement
    Completed Bank Reconciliation Worksheet
    Outcome
    Cash outflows validated
    Bank and ledger aligned
    📸 Screenshots
    VendorPayment_VoucherPosting.png
    BankStatement_Confirmed.png
    BankReconciliation_Worksheet_Matched.png

🔹 Phase 9.2 – Trial Balance Post-Payment
Activities

    Re-generated Trial Balance after payments
    Verified no imbalance introduced
    📸 Screenshot
    TrialBalance_PostPayment.png

🔹 Phase 9.3 – Cash Flow Forecast
Activities

    Generated Cash Flow Forecast
    Reviewed Daily Cash Position
    Analyzed expected inflows (AR) and outflows (AP)
    📸 Screenshots
    CashFlowForecast_DailyCashPosition.png
    CashFlowForecast_CustomerSummary.png
    CashFlowForecast_VendorSummary.png

🔹 Phase 9.4 – AP & AR Exposure Analysis
Activities
    
    Reviewed open and overdue AP transactions
    Reviewed open and overdue AR transactions
    📸 Screenshots
    AP_Transactions_Overview.png
    AR_Transactions_Overview.png
    Executive Outcome (Phase 9)
    Liquidity risks identified
    Working capital inefficiencies highlighted
    CFO-level insights produced

** Skills Demonstrated

    Dynamics 365 Finance (F&O)
    Accounts Payable & Receivable
    General Ledger & Trial Balance
    Inventory valuation & reconciliation
    Bank reconciliation
    Cash Flow Forecasting & Analysis
    Functional consulting mindset

** Project Status

    - End-to-End Finance Cycles Completed
    - Reporting & Reconciliation Validated
    - Cash Flow Analysis Delivered
