In SAP, **GL Account Types** (stored in field `SKB1-KTOKS`) categorize general ledger (G/L) accounts based on their purpose and usage. Here’s what each code typically represents:

---

### **Standard SAP GL Account Types**
| **Code** | **Account Type**         | **Description**                                                                 | **Examples**                          |
|----------|--------------------------|-------------------------------------------------------------------------------|---------------------------------------|
| **(blank)** | *Not Assigned*          | Unclassified or rarely used accounts                                          | Temporary clearing accounts           |
| **A**    | **Asset Accounts**       | Used for balance sheet assets (current/non-current)                           | Machinery (AS), Inventory (IN)        |
| **D**    | **Customer Accounts**    | Accounts for customer receivables (AR)                                        | Customer invoices, down payments      |
| **K**    | **Vendor Accounts**      | Accounts for vendor payables (AP)                                             | Vendor invoices, credit memos         |
| **M**    | **Material Accounts**    | Linked to inventory valuation (raw materials, finished goods)                | Stock accounts, GR/IR clearing        |
| **S**    | **G/L Revenue/Expense** | Profit & loss (P&L) accounts for income/expenses                              | Sales revenue, production costs       |

---

### **Key Details**
1. **Balance Sheet vs. P&L**:
   - **A, D, K, M**: Balance sheet accounts (asset/liability).
   - **S**: P&L accounts (revenue/expense).

2. **Link to Transactions**:
   - **A (Assets)**: Posted via asset transactions (e.g., `AS01`, `AB01`).
   - **D/K (AR/AP)**: Tied to customer/vendor documents (`FD01`, `FK01`).
   - **M (Materials)**: Auto-posted via goods movements (`MIGO`, `MIRO`).

3. **Configuration**:
   - Defined in **`OBD4`** (G/L Account Groups).
   - Master data tables: `SKA1` (Chart of Accounts), `SKB1` (Company Code Assignments).

---

### **How to Verify in Your System**
1. **Transaction `FS00`**:
   - Enter a G/L account and check the **Account Type** field.
2. **Table `SKB1`**:
   ```SQL
   SELECT SAKNR, KTOKS FROM SKB1 WHERE BUKRS = '1000' AND KTOKS IN ('A', 'D', 'K', 'M', 'S');
   ```

---

### **Why This Matters for Production Analysis**
- **Material Accounts (M)**: Track inventory movements (e.g., goods issued to production).  
- **Expense Accounts (S)**: Capture production variances (e.g., price differences).  
- **Asset Accounts (A)**: Capitalize production equipment costs.  

**Example Query for Production Costs**:  
```SQL
SELECT SAKNR, TXT50 FROM SKA1 
WHERE KTOPL = 'COA' AND KTOKS = 'S' 
AND TXT50 LIKE '%Production%';
```

---

Need help mapping these to your production variance process? Let me know!
