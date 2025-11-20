# Voucher Analysis – Project 01 (Accounts Receivable)

This document explains the full accounting impact of both invoice types used in **Project 01**:

- **Free Text Invoice (Service-based invoice)**
- **Sales Order Invoice (Product-based invoice – full O2C cycle)**

The purpose of this analysis is to demonstrate:
- How D365 Finance posts AR transactions into the General Ledger
- The difference between service revenue vs. product revenue postings
- The link between subledger (AR) and general ledger (GL)
- COGS and inventory impact in product-based invoicing

---

# 1. Free Text Invoice – Voucher Analysis  
**Invoice Number:** FTI-00000021  
**Invoice Amount:** 262.50 USD  
**Scenario Type:** Service invoice (no inventory)  

## 1.1 Ledger Impact Summary

| Account     | Type   | Amount  | Explanation |
|-------------|--------|---------|-------------|
| **130100**  | Debit  | 262.50  | Customer becomes debtor (Accounts Receivable) |
| **401200**  | Credit | 250.00  | Service revenue recognized |
| **202250**  | Credit | 12.50   | Sales tax payable to tax authority |

## 1.2 Explanation of Posting Logic

1. The **Accounts Receivable** account is debited because the customer now owes 262.50 USD.
2. The **Service Revenue** account is credited for the base amount of the consulting service.
3. The **Sales Tax Payable** account is credited to reflect the tax obligation Contoso must remit.

## 1.3 Key Concepts (MB-310)

- Free Text Invoices **do not affect inventory**.
- Only revenue, AR, and tax liability accounts are impacted.
- Posting profiles control which GL accounts are used.
- Subledger = Customer transaction  
- Ledger = Financial voucher  

📸 Related screenshots:  
`/Screenshots/FreeTextInvoice/07_FTI_Voucher.png`

---

# 2. Sales Order Invoice – Voucher Analysis  
**Sales Order:** 000860  
**Invoice Number:** CIV-00000716  
**Invoice Amount:** 480.00 USD  
**Scenario Type:** Product invoice (with inventory movement)  

This scenario includes **two types of postings**:

- Revenue + AR (on invoice)
- COGS + Inventory (cost recognition)
- Accrued sales (packing slip) if enabled in demo data (Contoso)

---

## 2.1 Ledger Impact Summary

### A. Revenue & Accounts Receivable

| Account      | Type   | Amount | Explanation |
|--------------|--------|--------|-------------|
| **130100**   | Debit  | 480.00 | Customer becomes debtor for the product |
| **401100**   | Credit | 480.00 | Product sales revenue recognized |

---

### B. Cost of Goods Sold (COGS) & Inventory

| Account                    | Type   | Amount   | Explanation |
|----------------------------|--------|----------|-------------|
| **500100 / 500150**        | Debit  | 302.71   | Cost of goods sold recognized |
| **140200 – Finished Goods Inventory** | Credit | 302.71 | Inventory reduced at standard cost |

---

### C. Additional Contoso Demo Postings (may appear)

| Account                   | Type   | Explanation |
|---------------------------|--------|-------------|
| **Accrued Sales (401400)** | Credit / Debit | Temporary revenue at packing slip |
| **Inventory Revaluation**  | Minor Debit/Credit | Rounding adjustments |
| **Cost of Goods Sold – Adjustments** | Debit/Credit | Variance postings |

These entries appear due to the Contoso demo configuration and may vary slightly.

---

## 2.2 Posting Flow Explanation

### Step 1 – Picking List
No financial posting occurs.  
Warehouse operation only.

### Step 2 – Packing Slip
Contoso demo typically posts:
- Accrued sales
- Deferred COGS

### Step 3 – Invoice
Finalizes:

- **Revenue recognition**  
- **AR creation**  
- **COGS recognition**  
- **Inventory reduction**

---

## 2.3 Key Concepts (MB-310)

- Sales Order Invoices impact **both operational** (inventory) and **financial** (GL) accounts.
- Packing Slip may generate **physical** and **financial** postings depending on setup.
- Invoice generates the final AR + Revenue postings.
- COGS is posted when goods are delivered (packing slip) or invoiced (depends on policy).
- Standard cost vs. moving average determines COGS valuation.

📸 Related screenshots:  
`/Screenshots/SalesOrder/08_SO_Voucher.png`

---

# 3. Subledger vs General Ledger (Integration)

| Layer | Meaning |
|-------|---------|
| **Subledger (AR)** | Stores detailed customer transactions |
| **General Ledger** | Stores summarized financial impact |

Dynamics 365 Finance automatically links them using:

- Voucher numbers  
- Posting types  
- Accounting distributions  

You can access linked journals from:
Accounts receivable > Customers > Customer transactions > Voucher

---

# 4. Financial Insight Summary

### Free Text Invoice
- Service-only scenario  
- No inventory impact  
- Simple AR + Revenue + Tax  

### Sales Order Invoice
- Full O2C process  
- Physical + financial inventory movement  
- COGS recognition  
- Revenue recognition  
- AR creation  

---

# 5. Conclusion

This voucher analysis demonstrates how Dynamics 365 Finance processes:

- Accounts Receivable  
- Revenue recognition  
- Sales tax liability  
- Cost of goods sold  
- Inventory reductions  
- Accrued postings (packing slip)  
- GL and subledger integration  

It is an essential component of Project 01 and showcases complete financial understanding of AR posting logic required for **MB-310** and real-world functional consulting.

---

