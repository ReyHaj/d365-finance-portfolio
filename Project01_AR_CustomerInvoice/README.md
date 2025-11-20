# Project 01 – AR Customer Invoice (End-to-End)  
## Microsoft Dynamics 365 Finance – Functional Consultant Portfolio

This project demonstrates a complete **Accounts Receivable (AR)** invoicing lifecycle in **Microsoft Dynamics 365 Finance**.  
It includes both service-based and product-based invoicing scenarios:

- **Free Text Invoice (FTI)** – Service invoice  
- **Sales Order Invoice (SO)** – Product invoice  

This project forms part of my journey to master **MB-310 (D365 Finance)** and build a real consulting portfolio.

---

# 📌 1. Project Overview

This project covers the full AR invoicing flow:

- Customer master data setup  
- Free Text Invoice creation and posting  
- Sales Order → Confirmation → Pick → Pack → Invoice  
- Tax calculation  
- Accounting distributions  
- Ledger voucher analysis  
- Subledger vs. general ledger flow  
- AR reporting (Aging, Customer balance, Trial balance impact)

The goal is to simulate a **real-world AR process** as performed by functional consultants.

---

# 🎯 2. Objectives

- Demonstrate the complete AR invoicing flow in D365 Finance  
- Configure and validate AR master data  
- Process both Free Text Invoice and Sales Order Invoice  
- Validate accounting distributions and posting profiles  
- Analyse financial impact through voucher postings  
- Review customer transaction history and AR reports  
- Build a reusable, professional portfolio project  

---

# 🧩 3. Scope of Work

This project includes:

### **A. Customer Master Data Setup**
- Customer account creation  
- Payment terms  
- Method of payment  
- Sales tax group  
- Address setup  

### **B. Option A: Free Text Invoice (Service Invoice)**
- FTI header & line setup  
- Tax calculation  
- Accounting distribution validation  
- Voucher posting  
- AR impact analysis  

### **C. Option B: Sales Order Invoice (Product Invoice)**
- Create Sales Order  
- Confirm order  
- Generate picking list  
- Picking list registration  
- Post packing slip (delivery)  
- Post invoice  
- Voucher analysis: AR + Revenue + COGS + Inventory  

### **D. Reporting and Validation**
- Customer transactions  
- AR Aging  
- Trial balance impact  
- Voucher inquiry  

---

# 🏗 4. System Environment

| Component | Detail |
|----------|--------|
| System | Microsoft Dynamics 365 Finance (Trial) |
| Role | System Administrator |
| Legal Entity | USMF (Contoso Demo) |
| Customer | P01-0001 – Project01 Test Customer |
| Item (SO Scenario) | D0001 – MidRangeSpeaker |

---

# 📂 5. Repository Structure
Project01_AR_CustomerInvoice/
│── README.md
│── Documentation/
│ ├── FTI_Documentation.md
│ ├── SalesOrder_Documentation.md
│ └── Voucher_Analysis.md
│
└── Screenshots/
├── FreeTextInvoice/
│ ├── 01_Customer_P01-0001.png
│ ├── 02_FTI_Header.png
│ ├── 03_FTI_Line.png
│ ├── 04_SalesTax.png
│ ├── 05_AccountingDistribution.png
│ ├── 06_FTI_Posted.png
│ └── 07_FTI_Voucher.png
│
└── SalesOrder/
├── 01_SO_Header.png
├── 02_SO_Line.png
├── 03_SO_Confirmation.png
├── 04_PickingList.png
├── 05_PickingRegistration.png
├── 06_PackingSlip.png
├── 07_Invoice.png
└── 08_SO_Voucher.png


---

# 📜 6. End-to-End Process Steps

## **1️⃣ Customer Master Data Setup**

**Navigation**:  
Accounts receivable > Customers > All customers > New

**Customer Details**
- Customer account: **P01-0001**  
- Name: **Project01 Test Customer**  
- Customer group: **10**  
- Payment terms: **Net30**  
- Currency: **USD**  
- Method of payment: **CHECK**  
- Sales tax group: **5Pct**

📸 Screenshot: `/Screenshots/FreeTextInvoice/01_Customer_P01-0001.png`

---

# 7️⃣ OPTION A — FREE TEXT INVOICE (Service Invoice)

## **A.1 Create the Invoice**

**Navigation:**  
Accounts receivable > Invoices > All free text invoices > New

### Header
- Customer account: **P01-0001**
- Description: Consulting Service Fee
- Invoice date: 2025-11-18
- Due date: 30 days (Net30)
- Currency: USD

### Line
| Field | Value |
|-------|--------|
| Description | Consulting Services |
| Main Account | **401200 – Service Revenue** |
| Unit Price | 250.00 |
| Quantity | 1 |
| Sales tax group | 5Pct |
| Item tax group | ALL |

📸 Line Screenshot: `/Screenshots/FreeTextInvoice/03_FTI_Line.png`

---

## **A.2 Sales Tax Calculation**

- Tax Base: **250.00**
- Tax Rate: **5%**
- Tax Amount: **12.50**
- Total Invoice Amount: **262.50**

📸 Screenshot: `/Screenshots/FreeTextInvoice/04_SalesTax.png`

---

## **A.3 Validate Accounting Distributions**

| Ledger Account | Description | Amount |
|----------------|-------------|--------|
| 130100 | Accounts Receivable | 262.50 |
| 401200 | Service Revenue | -250.00 |
| 202250 | Sales Tax Payable | -12.50 |

📸 Screenshot: `/Screenshots/FreeTextInvoice/05_AccountingDistribution.png`

---

## **A.4 Post Free Text Invoice**

After posting:

- Status: **Completed**
- Invoice Number: **FTI-00000021**
- Customer balance updated

📸 `/Screenshots/FreeTextInvoice/06_FTI_Posted.png`

---

## **A.5 Voucher (Accounting Entry)**

| Ledger Account | Debit | Credit |
|----------------|--------|---------|
| 130100 (AR) | 262.50 | – |
| 401200 (Revenue) | – | 250.00 |
| 202250 (Tax Payable) | – | 12.50 |

📸 `/Screenshots/FreeTextInvoice/07_FTI_Voucher.png`

---

# 8️⃣ OPTION B — SALES ORDER INVOICE (Product Invoice)

## **B.1 Create Sales Order**

**Navigation:**  
Accounts receivable > Orders > All sales orders > New

**Header Information**
- Customer: P01-0001  
- Site: 1  
- Warehouse: 13  

**Line**
- Item: **D0001 – MidRangeSpeaker**  
- Quantity: **1**  
- Unit Price: **480 USD**

📸 `/Screenshots/SalesOrder/01_SO_Header.png`

---

## **B.2 Confirm Sales Order**

Sell > Generate > Confirm Sales Order

📸 `/Screenshots/SalesOrder/03_SO_Confirmation.png`

---

## **B.3 Picking List + Registration**

- Generate picking list  
- Register picking → **Completed**

📸 `/Screenshots/SalesOrder/04_PickingList.png`

---

## **B.4 Post Packing Slip**

Pick and pack > Post packing slip

- Quantity delivered: 1  
- Status: Delivered

📸 `/Screenshots/SalesOrder/06_PackingSlip.png`

---

## **B.5 Post Sales Invoice**

Invoice > Generate > Invoice

- Invoice number: **CIV-00000716**
- Amount: **480 USD**

📸 `/Screenshots/SalesOrder/07_Invoice.png`

---

## **B.6 Voucher Analysis**

### Revenue + AR Posting
| Account | Debit | Credit |
|---------|--------|--------|
| 130100 | 480.00 | – |
| 401100 | – | 480.00 |

### COGS + Inventory
| Account | Debit | Credit |
|---------|--------|--------|
| COGS | 302.71 | – |
| Finished Goods Inventory | – | 302.71 |

📸 `/Screenshots/SalesOrder/08_SO_Voucher.png`

---

# 📊 9. AR Reporting

### Reports Used:
- **AR Aging Report**  
- **Customer balance report**  
- **Trial balance (ledger impact)**  
- **Customer transactions inquiry**

These validate the financial impact of the posted invoices.

---

# 🎓 10. Skills Demonstrated

- AR master data configuration  
- Free Text Invoice processing  
- Sales Order processing  
- Inventory → COGS recognition  
- Tax configuration & validation  
- Ledger voucher interpretation  
- Subledger vs Ledger flow  
- End-to-end O2C process  
- Professional documentation & GitHub project structuring  

---

# ⭐ 11. Conclusion

Project 01 successfully demonstrates two complete AR invoicing flows:

### ✔ Free Text Invoice (service)  
### ✔ Sales Order Invoice (products, full O2C process)

Both scenarios include:

- Tax  
- Distributions  
- Ledger postings  
- Subledger entries  
- Delivery updates  
- AR financial impact  

This project is ready for:
- GitHub portfolio  
- LinkedIn showcase  
- MB-310 preparation  
- Junior consultant interviews  

---

# 📞 Contact  
**Reyhaneh – D365 Finance Functional Consultant (Junior)**  
Email: reyhaneh.hajili2728@gmail.com  
Phone: +39 392 305 6496  
