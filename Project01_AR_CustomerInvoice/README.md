# Project 01 – AR Customer Invoice
# Project 01 – End-to-End Customer Invoice Process (Accounts Receivable)
### Microsoft Dynamics 365 Finance – Portfolio Project  

---

## 📌 Project Overview
This project demonstrates the full **Accounts Receivable (AR)** invoicing lifecycle in Microsoft Dynamics 365 Finance.  
It simulates a real business scenario where a customer is created, an invoice is issued, posted, and analyzed through financial and AR reporting tools.

This project is part of my journey to master **Microsoft Dynamics 365 Finance (MB-310)** and build a professional consulting portfolio.

---

## 🎯 Objectives
- Demonstrate the full AR invoicing process in D365 Finance.
- Configure and validate AR master data (Customer, Posting Profiles, Payment Terms).
- Create and post a Free Text Invoice or Sales Order Invoice.
- Analyze subledger and general ledger accounting entries.
- Review customer balance and AR reports.
- Build a structured, reusable project template for future D365 portfolio items.

---

## 🧩 Scope of Work
This end-to-end scenario includes:

1. **Customer Master Data Setup**
2. **Invoice Creation**
   - Free Text Invoice *(services)*  
   - OR Sales Order Invoice *(products)*  
3. **Posting the Invoice**
4. **Accounting Distributions Review**
5. **Voucher (GL) Analysis**
6. **Customer Transactions Inquiry**
7. **AR Reporting**
   - Aging Report  
   - Customer Balance  
   - Trial Balance impact  

---

## 🏗 System Environment
- **Dynamics 365 Finance & Operations (Trial Environment)**
- **Role:** System Administrator  
- **Company Used:** USMF (Default Contoso Demo Company)

---

## 📂 Repository Structure
Project01/
│── Documentation/
│ └── Project01_AR_Invoice_Process.pdf
│── Screenshots/
│ ├── Customer/
│ ├── Invoice/
│ ├── Posting/
│ └── Reporting/
│── ConfigFiles/
│── README.md



---

## 📸 Deliverables
This project includes:

- Full step-by-step documentation (Markdown + PDF)
- Screenshots of every process step
- Voucher and subledger journal analysis
- Customer transaction history
- AR Aging and financial reporting snapshots
- Final conclusions & learning outcomes

---

## 📜 End-to-End Process Steps

### **1️⃣ Customer Creation**
- Navigate: *Accounts receivable > Customers > All customers > New*
- Define:
  - Customer group  
  - Payment terms  
  - Method of payment  
  - Address & contact details  
- Validate posting profile assignment.

---

### **2️⃣ Invoice Creation**
You may complete one or both scenarios:

#### **Option A – Free Text Invoice**
- Navigate: *Accounts receivable > Invoices > All free text invoices*
- Add line description, revenue account, sales tax group, amount.

#### **Option B – Sales Order Invoice**
- Create sales order  
- Add item lines  
- Confirm → Pick → Pack → Invoice  

---

### **3️⃣ Posting the Invoice**
- Validate accounting distributions
- Confirm tax calculation
- Post the invoice
- Capture voucher (Ledger) details

---

### **4️⃣ Accounting Analysis**
- View subledger journal  
- Review voucher posting:  
  - **Debit:** Accounts Receivable  
  - **Credit:** Revenue  
  - **Credit:** Tax Payable (if applicable)

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

---

## 📌 Status
**In Progress** – Moving to *Step 1: Customer Creation* in the USMF environment.

---

## 📞 Contact
For collaborations or consulting opportunities:  
**Reyhaneh – D365 Finance Functional Consultant (Junior Level)**  
+393923056496
reyhaneh.hajili2728@gmail.com
