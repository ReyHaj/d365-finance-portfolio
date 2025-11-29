# Project 01 – AR Customer Payments & Settlement  
**Microsoft Dynamics 365 Finance – Accounts Receivable**

This project demonstrates the **Customer Payment** and **Settlement** process in Microsoft Dynamics 365 Finance, continuing from **Project 01 – AR Customer Invoice**.

It shows how open customer invoices are paid, settled, posted to the general ledger, and reported in customer aging reports.

---

## 🎯 Objectives

By the end of this project I demonstrate that I can:

- Record **customer payments** against open invoices  
- Use **Customer payment journals** correctly (journal name, offset account, method of payment)
- Perform **settlement** between invoices and payments (FTI + Sales Order)
- Analyse **customer transactions** before and after settlement  
- Read **voucher postings** for AR payments (Bank vs. Accounts Receivable)  
- Run and interpret the **Customer aging report**  
- Explain the full flow: **Invoice → Open AR → Payment → Settlement → Closed AR**

This project is designed for:

- **MB-310 exam preparation (Accounts Receivable section)**
- **Junior D365 Finance Functional Consultant** portfolio
- Interview discussions about **Order-to-Cash (O2C)** and **cash application**

---

## 🏗 System Environment

| Component   | Details                                              |
|------------|------------------------------------------------------|
| System     | Microsoft Dynamics 365 Finance & Operations (Trial)  |
| Role       | System Administrator                                 |
| Legal Entity | USMF (Contoso demo company)                        |
| Company Scenario | Project01 Test Customer – Service + Product    |

Prerequisite: **Project 01 – AR Customer Invoice** is completed and has created two open invoices:

- **FTI-00000020** – Free text invoice (262.50 USD)  
- **CIV-00000715** – Sales order invoice (480.00 USD)

Customer: **P01-0001 – Project01 Test Customer**

---

## 📂 Project Structure

Project01_AR_CustomerPayments/
├─ README.md
└─ Documentation/
   └─ CustomerPayments_Documentation.md
Screenshots can be stored under:
  
  Phase 1.1.Foundation Setup (Customer Payments Basics).png
  Phase 1.2.Foundation Setup (Customer Payments Basics).png
  Phase 2.1 Start the Customer Payment Journal (In-System Work).png
  Phase 2.2 Start the Customer Payment Journal (In-System Work).png
  Phase 3.1.Validate Payment Posting + GL Voucher Analysis.png
  Phase 3.2.Validate Payment Posting + GL Voucher Analysis.png
  phase 4.1.Voucher Analysis (Final Validation).png
  phase 4.2.Voucher Analysis (Final Validation).png
  phase 5.2.Customer aging report.png
  phase 5.1.Customer aging report.png


Project01_AR_CustomerPayments/
└─ Screenshots/
   ├─ Phase01_JournalHeader/
   ├─ Phase02_JournalLine_Posting/
   ├─ Phase03_SettlementView/
   ├─ Phase04_Voucher/
   └─ Phase05_AgingReport/
🔄 End-to-End Process Overview
This project is split into five phases:

Phase 1 – Create Customer Payment Journal
  Open Customer payment journal
  Create a new journal header (name: CustPay, description: Project 02 – Customer Payments)
  Add payment lines:
  Payment 1: for the Sales Order invoice (480.00 USD)
  Payment 2: for the Free Text invoice (262.50 USD)

Phase 2 – Post the Payment and Verify Customer Transactions
  Validate and Post the customer payment journal
  Navigate to Customer transactions and confirm:
  Invoices still visible
  New Payment transactions created
  Balances on invoices become 0.00 after settlement

Phase 3 – Settlement (Apply Payment to Invoices)
For each payment:
  
  Open the Settlement window
  Mark the correct invoice line (FTI vs Sales Order)
  Post the settlement
  Confirm that:
  Invoices are closed
  Payments show as settled
  No remaining balance for customer P01-0001

Phase 4 – Voucher & Ledger Analysis
Open payment voucher from customer transactions
  Review ledger postings:
  Debit Bank account
  Credit Accounts Receivable
  Explain how this reverses the original AR entry from Project 01.

Phase 5 – AR Reporting (Customer Aging)
  Run Customer aging report
  Explain how: 
  Before payment: customer appears with open balances in aging buckets
  After payment & settlement: no open balance for P01-0001

📊 Accounting Logic (High Level)
From Project 01 (invoices):

Invoice posting (simplified)

DR Accounts Receivable

CR Revenue

CR Tax payable (if applicable)

For Sales Order invoices: DR COGS / CR Inventory

From Project 02 (payments):

Customer payment posting

DR Bank account

CR Accounts Receivable

After settlement:

Customer’s AR balance = 0

Invoices change status from Open to Closed

Aging report shows no overdue balance for this customer.

🎓 Skills Demonstrated
AR Customer payment journal configuration and posting

Settlement concepts (open transactions, closed transactions, partial vs full)

Reading Customer transactions and understanding status / balance

Analysing vouchers and GL impact of AR payments

Running and interpreting Customer aging reports

Connecting Project 01 (Invoice) and Project 02 (Payment) as one continuous O2C flow

🔗 Related Projects
Project 01 – AR Customer Invoice
Path: /Project01_AR_CustomerInvoice/README.md

Future AR projects may include:

Project 03 – Customer Credit Notes & Adjustments

Project 04 – Collections & Interest Notes


#  Phase 2.1 Start the Customer Payment Journal (In-System Work).png
#	Phase 2.2 Start the Customer Payment Journal (In-System Work).png
#	Phase 3.1.Validate Payment Posting + GL Voucher Analysis.png
#	Phase 3.2.Validate Payment Posting + GL Voucher Analysis.png.png
#	Phase1.2.Foundation Setup (Customer Payments Basics).png
#	ScreenShots/Phase 1.1.Foundation Setup (Customer Payments Basics).png
#	phase 4.1.Voucher Analysis (Final Validation).png
#	phase 4.2.Voucher Analysis (Final Validation).png
#	phase 5.1.Customer aging report.png
#	phase 5.2.Customer aging report.png



📞 Contact
Reyhaneh – D365 Finance Functional Consultant (Junior Level)
📧 Email: reyhaneh.hajili2728@gmail.com
📱 Phone: +39 392 305 6496

