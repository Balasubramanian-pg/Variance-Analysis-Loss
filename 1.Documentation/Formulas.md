Here's a structured table summarizing the loss calculations for each SKU (330ml and 550ml):

| **Loss Type** | **SKU**      | **Formula**                                                                 | **Standard per Case**                         | **Notes**                                                                 |
|---------------|--------------|-----------------------------------------------------------------------------|-----------------------------------------------|---------------------------------------------------------------------------|
| **Bottle Loss** | 650ml        | `(Actual Bottles - 12 × Production Cases) / (12 × Production Cases)`       | 12 bottles per case                           | Applies only to bottles (650ml).                                          |
| **Can Loss**    | 330ml        | `(Actual Cans - 24 × Production Cases) / (24 × Production Cases)`           | 24 cans per case                              | Applies only to cans (330ml).                                             |
| **Labels Loss** | **330ml**    | `(Actual Labels - 72 × Production Cases) / (72 × Production Cases)`         | 24 cans × 3 labels = **72 labels per case**   | Assumes 3 labels per can (front, back, neck).                            |
|                | **650ml**    | `(Actual Labels - 36 × Production Cases) / (36 × Production Cases)`         | 12 bottles × 3 labels = **36 labels per case** | **Exception:** Woodpecker Crest SKU uses **1 back label per case** (adjust labels accordingly). |
| **Crown Loss**  | 650ml        | `(Actual Crowns - 12 × Production Cases) / (12 × Production Cases)`         | 12 crowns per case (1 per bottle)             | Excludes bottles with ring pulls.                                         |
| **Carton Loss** | **Both SKUs**| `(Actual Cartons - Production Cases) / Production Cases`                    | 1 carton per case                             | Direct comparison of actual vs. expected cartons.                        |

---

### Notes:
1. **Bottle/Can Loss**:  
   - Use actual units (bottles/cans) compared to the expected units based on production cases.

2. **Labels Loss**:  
   - **330ml (Cans)**: 3 labels per can × 24 cans = 72 labels per case.  
   - **550ml (Bottles)**: 3 labels per bottle × 12 bottles = 36 labels per case.  
   - **Woodpecker Crest Exception**: Replace the standard 36 labels per case with `(12 bottles × 2 labels) + 1 back label = 25 labels per case`.

3. **Crown Loss**:  
   - Only applies to bottles requiring crowns (excludes bottles with ring pulls).

4. **Carton Loss**:  
   - Directly compare actual cartons used to production cases (1 carton = 1 case).
