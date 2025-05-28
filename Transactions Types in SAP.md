In SAP, the codes you listed (`MKPF`, `RMRP`, `VBRK`) are not transaction codes (T-codes) but rather **table names**. Here's what each represents:

---

### **1. `MKPF` (Header of Material Document)**
- **Purpose**: Stores header data for material movements (goods receipts, goods issues, transfers).
- **Key Fields**:
  - `MBLNR` (Material Document Number)
  - `MJAHR` (Fiscal Year)
  - `BUDAT` (Posting Date)
  - `USNAM` (User who posted)
- **Related Transactions**:
  - **`MB03`** (Display Material Document)
  - **`MIGO`** (Goods Movement)

---

### **2. `RMRP` (Reminder/Dispute Management: Payment Reminders)**
- **Purpose**: Stores data related to payment reminders or dunning notices in Accounts Receivable.
- **Key Fields**:
  - `MABNR` (Reminder Number)
  - `KUNNR` (Customer Number)
  - `BELNR` (Accounting Document)
- **Related Transactions**:
  - **`F26`** (Create Payment Reminders)
  - **`F28`** (Process Dunning)

---

### **3. `VBRK` (Billing Document Header)**
- **Purpose**: Contains header data for billing documents (invoices, credit memos).
- **Key Fields**:
  - `VBELN` (Billing Document Number)
  - `FKART` (Billing Type, e.g., "F2" for invoice)
  - `NETWR` (Net Value)
  - `KUNNR` (Sold-to Customer)
- **Related Transactions**:
  - **`VF03`** (Display Billing Document)
  - **`VFX3`** (Billing Document List)

---

### **Summary Table**
| **Table** | **Description** | **Key Field** | **Related T-Code** |
|-----------|----------------|--------------|--------------------|
| `MKPF` | Material Document Header | `MBLNR` (Doc Number) | `MB03`, `MIGO` |
| `RMRP` | Payment Reminders | `MABNR` (Reminder No.) | `F26`, `F28` |
| `VBRK` | Billing Document Header | `VBELN` (Billing Doc) | `VF03`, `VFX3` |

---
