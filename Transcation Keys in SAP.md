These codes represent **SAP Transaction Keys (BSCHL/BUZEI)** used primarily in financial accounting to classify posting line items. They appear in documents like FB50 (G/L Posting) and FB60 (Vendor Invoice) to determine account determination logic. Here's a structured breakdown:

---

### **1. Common Transaction Keys (Grouped by Function)**
#### **A. Standard Postings**
| Key | Description | Typical Use |
|-----|------------|-------------|
| **BSX** | GL Account Posting | General ledger entries |
| **GBB** | Cost of Goods Sold | Inventory consumption |
| **DIF** | Price Differences | Material valuation variances |
| **WRX** | Tax Adjustment | Tax corrections |

#### **B. Tax-Related**
| Key | Description |
|-----|------------|
| **MW2** | Output Tax (Sales) |
| **MWS** | Input Tax (Purchases) |

#### **C. Asset Accounting**
| Key | Description |
|-----|------------|
| **ANL** | Asset Acquisition |
| **ANZ** | Asset Retirement |

#### **D. Special Transactions**
| Key | Description |
|-----|------------|
| **ZAC** | Accruals/Deferrals |
| **UMB** | Intercompany Transfers |

---

### **2. Production-Specific Keys**
| Key | Description | Relevance to Production |
|-----|------------|-------------------------|
| **PRD** | Production Cost | Direct material/labor postings |
| **KBS** | Cost Center Activity | Overhead allocation |
| **RKA** | Order Settlement | WIP/cost object clearing |

---

### **3. Custom Keys (Z-Prefix)**
These are client-specific. Common patterns:
- **ZCA/ZCC**: Custom accruals
- **ZDI**: Direct inventory postings
- **ZFR**: Freight charges
- **ZOT**: Overhead taxes

---

### **4. How to Verify**
1. **Table T030** (Account Determination Keys)  
   ```SQL
   SELECT BSCHL, TEXT1 FROM T030 WHERE BSCHL IN ('GBB', 'PRD', 'BSX');
   ```
2. **Transaction OBYC** (Configure Automatic Postings)  
   Shows how keys map to accounts.

---

### **Key Relationships**
- **Material Movements**: `GBB` + `PRD`  
- **Variances**: `DIF` + `KDR`  
- **Taxes**: `MW2` (Sales) / `MWS` (Purchases)  
