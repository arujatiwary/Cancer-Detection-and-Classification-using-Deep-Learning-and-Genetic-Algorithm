Cancer classification is complicated by molecular heterogeneity.  
This project presents a hybrid approach that:

- Uses **Genetic Algorithms** for gene subset selection.  
- Trains **TabNet** and **SAINT** for binary and multiclass cancer prediction.  
- Applies **gradient-based interpretability** to find biologically meaningful gene biomarkers.

The models achieved up to **98.7% accuracy** on binary tasks and **95.6% on multiclass** classification while recovering known oncogenes like *BRCA1*, *TP53*, and *KRAS*.

---

## Dataset

**Source:** [UCSC Xena TCGA Pan-Cancer](https://xenabrowser.net/)  
**Samples:** 10,459  **Genes:** 17,950  **Classes:** 33 tumor types  

### Preprocessing
- Exon-to-gene collapsing  
- Median imputation for missing values  
- Low-variance filtering  
- Z-score normalization  
- Metadata mapping via GDC API

---

### Deep Learning Models

**TabNet** – interpretable attention-based model for tabular data.  
**SAINT** – transformer with dual (row + column) attention and contrastive pretraining.  

Both models were trained using the **Adam/AdamW** optimizers, cosine learning rate decay, and early stopping.

---

### Gradient-Based Interpretability

Used gradient attribution and Integrated Gradients to identify key biomarkers.  
Top genes recovered include:  
- *BRCA1*, *ESR1*, *PGR* — Breast cancer  
- *TP53*, *KRAS*, *EGFR* — Lung and colon cancers  
- *APC*, *SMAD4* — Colorectal cancer  

---
 
