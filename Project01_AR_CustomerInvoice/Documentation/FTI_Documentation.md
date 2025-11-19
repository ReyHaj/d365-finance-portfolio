# Free Text Invoice – Documentation  
**Project 01 – Accounts Receivable**  
**Customer:** P01-0001 – Project01 Test Customer

---

## 1️⃣ Scenario Overview
This scenario demonstrates how to create, calculate tax for, and post a Free Text Invoice (FTI) for a service in Dynamics 365 Finance.

Free Text Invoice is used for **service-based** billing where no inventory or item is involved.

---

## 2️⃣ Navigation Path
**Accounts receivable > Invoices > All free text invoices > New**

---

## 3️⃣ Header Details
| Field | Value |
|-------|--------|
| Customer account | P01-0001 |
| Invoice date | 18-Nov-2025 |
| Currency | USD |
| Method of payment | Check |
| Terms of payment | Net30 |

---

## 4️⃣ Invoice Line Details
| Field | Value |
|-------|--------|
| Description | Consulting Service Fee |
| Main account | 401200 – Service Revenue |
| Sales tax group | 5Pct |
| Item sales tax group | ALL |
| Unit price | 250.00 |
| Quantity | 1 |
| Tax | 12.50 |

---

## 5️⃣ Sales Tax Calculation
Navigation:  
**Invoice > Sales tax**

Tax details:  
- Base: 250 USD  
- Rate: 5%  
- Tax Amount: **12.50 USD**

---

## 6️⃣ Posting the Invoice
**Invoice > Post**

Posting status changes to: **Completed**  
Invoice number created: **FTI-00000021**

---

## 7️⃣ Voucher Result
| Type | Account | Debit | Credit |
|------|----------|--------|---------|
| Customer AR | 130100 | 262.50 | - |
| Service Revenue | 401200 | - | 250.00 |
| Sales Tax Payable | 202250 | - | 12.50 |

📸 See: `/Screenshots/FreeTextInvoice/04_Voucher.png`

---

## ✔ Conclusion
The Free Text Invoice has been successfully created, taxed, posted, and verified with correct voucher entries.
