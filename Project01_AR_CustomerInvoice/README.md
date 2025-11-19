# Project 01 – AR Customer Invoice
# Project 01 – End-to-End Customer Invoice Process (Accounts Receivable)
### Microsoft Dynamics 365 Finance – Portfolio Project  

---
# Project 01 – AR Customer Invoice
# Project 01 – End-to-End Customer Invoice Process (Accounts Receivable)
### Microsoft Dynamics 365 Finance – Portfolio Project  

## 📌 Project Overview
This project demonstrates the full **Accounts Receivable (AR)** invoicing lifecycle in Microsoft Dynamics 365 Finance.  
It simulates a real business scenario where a customer is created, an invoice is issued, posted, and analysed through financial and AR reporting tools.
This project is part of my journey to master **Microsoft Dynamics 365 Finance (MB-310)** and build a professional consulting portfolio.

## 🎯 Objectives
- Demonstrate the full AR invoicing process in D365 Finance.
- Configure and validate AR master data (Customer, Posting Profiles, Payment Terms).
- Create and post a Free Text Invoice or Sales Order Invoice.
- Analyse subledger and general ledger accounting entries.
- Review customer balance and AR reports.
- Build a structured, reusable project template for future D365 portfolio items.

## 🧩 Scope of Work
This end-to-end scenario includes:
1. **Customer Master Data Setup**
2. **Invoice Creation**
   - Free Text Invoice *(services-based invoice)*  
   - Sales Order Invoice *(products-based invoice)*  
3. **Posting the Invoice**
4. **Accounting Distributions Review**
5. **Voucher (GL) Analysis**
6. **Customer Transactions Inquiry**
7. **AR Reporting**
   - Aging Report  
   - Customer Balance  
   - Trial Balance impact  

## 🏗 System Environment
- **Dynamics 365 Finance & Operations (Trial Environment)**
- **Role:** System Administrator  
- **Company Used:** USMF (Default Contoso Demo Company)

## 📂 Repository Structure
Project01/
Project01/
├── README.md
├── Documentation/
│ ├── FTI_Documentation.md
│ ├── SalesOrder_Documentation.md
│ └── Voucher_Analysis.md
└── Screenshots/
  ├── FreeTextInvoice/
   └── SalesOrder/
│── ConfigFiles/
│── README.md

## 📸 Deliverables
This project includes:

- Full step-by-step documentation (Markdown + PDF)
- Screenshots of every process step
- Voucher and subledger journal analysis
- Customer transaction history
- AR Aging and financial reporting snapshots
- Final conclusions & learning outcomes

## 📜 End-to-End Process Steps

### **1️⃣ Setup (Master Data)
- Navigate: *Accounts receivable > Customers > All customers > New*
- Define:
  - Customer account: **P01-0001 **
  - Customer Name:** Project01 Test Customer**
  - Customer group: **10**
  - Payment terms: **Net30 **
  - Currency:** USD **  
  - Method of payment: **CHECK**
  - Address & contact details: **123 Main Street, New York, NY**
See:  ,
📸 Screenshots → `/Screenshots/FreeTextInvoice/`: `01_Customer_P01-0001.png`

### **2️⃣ Invoice Creation**
#### **Option A – — Free Text Invoice (Service Invoice)**
A Free Text Invoice (FTI) is used for service-based billing where no inventory is involved.  
This invoice demonstrates core AR functionality and financial posting behavior.
- Navigate: *Accounts receivable > Invoices > All free text invoices*
✔ Invoice Header
- Customer Account: **P01-0001**
- Revenue Account: **401200 – Service Revenue**
- Sales Tax Group: **5Pct**
- Description:**Consulting Service Fee **
- Total Amount: **262.50 USD**
- Status: **Completed**
✔ Invoice Line
- Description: **Consulting Services **
- Main Account: **401200 – Service Revenue**
- Unit Price: **250.00**
- Quantity: **1**
- Sales Tax Group: **5Pct**
- Item Sales Tax Group: **ALL**
- Tax Amount: **12.50**

See:  
📄 Documentation → **FTI_Documentation.md**  
📸 Screenshots → `/Screenshots/FreeTextInvoice/`

#### **Option B — Sales Order Invoice (Product Invoice)**
- Navigate: *Accounts receivable > Invoices > All free text invoices*
- Created  
- Confirmed  
- Picking List  
- Packing Slip  
- Invoice  
- Voucher
- Confirm → Pick → Pack → Invoice  
See:  
📄 Documentation → **SalesOrder_Documentation.md**  
📸 Screenshots → `/Screenshots/SalesOrder/`
Sales Order Invoice (Product Invoice)
*(Documentation will be completed after performing the Sales Order cycle.)*

Sales Order steps to be executed:

1. Create Sales Order  
2. Add items  
3. Confirm  
4. Generate Picking List  
5. Generate Packing Slip  
6. Invoice  
7. Analyze Voucher  

📄 See: `Documentation/SalesOrder_Documentation.md`  
📸 Screenshots inside `/SalesOrder/`

## 📊 Voucher Analysis
Full accounting entry breakdown for both FTI & Sales Order invoices.  
Accounts receivable > Customers > All customers >P01-0001 > Tab: Transactions > FTI-00000021 > Voucher
See:  
📄 Documentation → **Voucher_Analysis.md**

### **3️⃣ Posting the Invoice**
- Validate accounting distributions:
- Purpose:** Verify which ledger accounts will be used before posting**
**Result:**
- AR (Customer):** 130100 ** 
- Revenue account (from line): **401200 – Service Revenue** 
- Sales Tax Payable:** 202250 ** 
📄 Documentation → **Accounting_Distribution.md**  
📸 Screenshot: `03_Accounting_Distribution.png` (optional)

- Confirm Sales tax calculation
- Purpose:** To verify that the sales tax is calculated correctly based on**
Navigation:** *Invoice > Sales tax*
	Tax Base:250.00 
Rate: 5%  
Amount: 12.50 
How it was accessed: Invoice > Sales tax
📸 Screenshot: `03_Sales_Tax_Calculation.png`

- Post the invoice:
-Purpose:** To commit the transaction to the system and generate the subledger + general ledger entries.**
Posting Status:** Completed  
Invoice Number:** `FTI-00000021`**  
Total Invoice Amount:** 262.50 USD ** 
📸 Screenshot: `05_Posted_FTI_Header.png`

- Capture voucher (Ledger Posting)
 Purpose:** To inspect the general ledger accounts impacted by the invoice.** 
Navigation:** *Invoice > Voucher**
Ledger Account	Debit	Credit	Description
130100	262.50	–	Accounts receivable (customer balance)
401200	–	250.00	Service revenue
202250	–	12.50	Sales tax payable

📸 /Screenshots/FreeTextInvoice/04_Voucher.png

### **4️⃣ Accounting Analysis**
- View subledger journal:
 Purpose: ** To inspect the AR subledger transaction generated by the invoice posting.** 
Navigation: Invoice > Subledger journal
What was reviewed:
Customer transaction entry created
Ledger posting type: Free text invoice
Correct relationship between AR and GL 

📸/Screenshots/FreeTextInvoice/06_Subledger_Journal.png

- Review voucher posting:  The system generated the following entries based on the invoice:
Debit: Accounts Receivable → 130100
Customer now owes 262.50 US
Credit: Revenue → 401200
Service revenue recognized
Credit: Sales Tax Payable → 20225
12.50 USD owed to tax authority
This reflects a standard AR Service Invoice posting flow.
---

# 📊 Voucher Analysis Summary
See: `Documentation/Voucher_Analysis.md`
### Free Text Invoice  
- DR Accounts Receivable  
- CR Service Revenue  
- CR Sales Tax Payable  
---

### **5️⃣ Customer Transaction Inquiry**
Navigate:  
*Accounts receivable > Customers > All customers > Customer transactions*

Review:
- Open transactions  
- Settlements  
- Balances  

---

### **6️⃣ AR Reporting**
Generate and analyze:

#### **• AR Aging Report**  
Shows outstanding balances by age bucket.

#### **• Customer Balance**  
Real-time receivables balance.

#### **• Trial Balance Impact**  
Validates GL postings created by AR transactions.

## 🎯 Key Skills Demonstrated
- Customer master setup  
- AR parameters  
- Tax calculation  
- Invoice posting flow  
- Settlement basics  
- Sales order full cycle  
- Financial voucher interpretation  

---

## 📊 Expected Outcomes
Upon completion, the project produces:

- A fully posted invoice with valid accounting entries  
- Customer transaction history visible in AR  
- Reporting visibility into AR balances  
- Demonstrated understanding of subledger → ledger flow  
- A complete professional portfolio item ready for GitHub and LinkedIn  

---

## 🎓 Skills Demonstrated
- D365 Finance functional navigation  
- AR master data configuration  
- Invoice processing (service & product-based)  
- Accounting distribution validation  
- Understanding of subledger & GL integration  
- Financial visibility using AR reports  
- Technical documentation for consulting projects  
- Professional GitHub project structuring  


## 📞 Contact
For collaborations or consulting opportunities:  
**Reyhaneh – D365 Finance Functional Consultant (Junior Level)**  
+393923056496
reyhaneh.hajili2728@gmail.com
