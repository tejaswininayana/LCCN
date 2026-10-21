# LCCN
Label-Constrained Cascade Normalization for Emotion Detection in Kannada-English Code-Mixed Text
## 📋 Overview

LCCN is a label-constrained cascade normalization framework for Kannada-English code-mixed social media text. This repository contains:

- **Revised manuscript** (Draft 8)
- **Response letter** (point-by-point reviewer feedback)
- **Complete computational reproducibility** (32 Jupyter notebooks)
- **Public resource documentation** (KEEL lexicon, corpus details, external validation)

---

## 📖 Citation

```bibtex
@article{tejaswini2026lccn,
  title={Label-Constrained Cascade Normalization for Emotion-Aware Text Normalization in Kannada-English Code-Mixed Data},
  author={Tejaswini, M and Kumar, Anil K M},
  journal={IJIES},
  year={2026}
}
```

---

## 📊 Key Results

- **Language-ID Agreement:** κ = 0.906 (almost perfect)
- **Merge-Precision Audit:** 580/1358 compatible (0.4271 overall precision)
- **LOO Ablation Gains:** +0.0050 F1 (emotion condition), −0.0007 F1 (cluster condition)
- **LCCN + IndicXlit:** +0.0105 F1 (p=0.0194) vs. raw baseline
- **External Validation (Twitter):** ρ = 0.879 (Spearman rank correlation)

---

## 🗂️ Repository Contents

### **Documentation**
- **README.md** — This file (overview and quickstart)
- **RESOURCES.md** — Corpus details, KEEL lexicon availability, baseline models
- **TABLES.md** — All results tables, statistical metrics, effect sizes

### **Notebooks (32 Total)**

**Core Pipeline & Training:**
- `lccn-r4-train__2_.ipynb` — Model training pipeline
- `paper1-nb1-lccn-final__2_.ipynb` — Final LCCN implementation
- `paper1-nb2-lccn-ml__2_.ipynb` — Machine learning baselines
- `paper1-nb3-lccn-dl__2_.ipynb` — Deep learning models

**Transformers & Language Models:**
- `paper1-nb4-lccn-xlmroberta__2_.ipynb` — XLM-RoBERTa fine-tuning
- `paper1-nb5-lccn-muril__2_.ipynb` — MuRIL model experiments
- `paper1-nb6-lccn-xlm43-44__2_.ipynb` — Missing seeds (43, 44)
- `paper1-nb5-lccn-cross-dataset-validation__3_.ipynb` — Twitter validation

**Audits (Language-ID & Merge-Precision):**
- `lccn-r15-langid-audit__2_.ipynb` — Language identification audit (main)
- `lccn-r15-langid-audit__3_.ipynb` — Language ID backup run
- `lccn-r17-merge-audit.ipynb` — Merge-precision Phase 1
- `r17-phase2-merge-precision__1_.ipynb` — Merge-precision Phase 2 (Table 13)
- `lccn-label-revision__2_.ipynb` — Label verification
- `paper1-lccn-merge__3_.ipynb` — Merge statistics

**Ablation Studies:**
- `lccn-r16a-trainonly-arms.ipynb` — Train-only ablation (classical)
- `lccn-r16b-trainonly-xlmr.ipynb` — Train-only ablation (XLM-R)
- `lccn-r21a-guard-arms.ipynb` — Guarded phonetic arms
- `lccn-r22a-loo-arms.ipynb` — Leave-one-out ablation (classical)
- `lccn-r22b-loo-xlmr__1_.ipynb` — Leave-one-out ablation (XLM-R seed 42, v1)
- `lccn-r22b-loo-xlmr.ipynb` — Leave-one-out ablation (XLM-R seed 42, v2)
- `lccn-r22c-missing-seeds.ipynb` — Missing seeds (seeds 43/44, v1)
- `lccn-r22c-missing-seeds__1_.ipynb` — Missing seeds (seeds 43/44, v2)
- `lccn-r24a-xlit-arms.ipynb` — Transliteration ablation (classical)
- `lccn-r24b-xlit-gpu.ipynb` — Transliteration ablation (GPU)

**Statistics & Sensitivity:**
- `lccn-r13-perseed-stats__1_.ipynb` — Per-seed F1 statistics (v1)
- `lccn-r13-perseed-stats-v2__1_.ipynb` — Per-seed F1 statistics (v2)
- `lccn-mcnemar__2_.ipynb` — McNemar test implementation (v1)
- `lccn-mcnemar__3_.ipynb` — McNemar test implementation (v2)
- `lccn-sensitivity__2_.ipynb` — Threshold sensitivity analysis
- `lccn-r23-external-bootstrap__2_.ipynb` — External validation bootstrap
- `lccn-r25-near-duplicates.ipynb` — Near-duplicate detection

---

## 🚀 Quick Start

### **To View Notebooks**

Click any notebook in the list above. GitHub renders Jupyter notebooks automatically.

### **To Run Locally**

```bash
git clone https://github.com/tejaswininaryana/LCCN.git
cd LCCN
pip install jupyter pandas numpy scikit-learn torch transformers
jupyter notebook
```

### **To Reproduce Results**

1. Run core pipeline: `lccn-r4-train__2_.ipynb`
2. Run audits: `lccn-r15-langid-audit__2_.ipynb` → `r17-phase2-merge-precision__1_.ipynb`
3. Run ablations: `lccn-r22b-loo-xlmr.ipynb`
4. Run statistics: `lccn-r13-perseed-stats-v2__1_.ipynb` + `lccn-mcnemar__3_.ipynb`

---

## 📚 Resources

### **Datasets**

**Kannada-English YouTube Emotion Corpus**
- 40,000 comments (28K train, 6K val, 6K test)
- 4 emotions: happy, anger, disgust, sad
- Annotator agreement: κ = 0.8313
- Details: See RESOURCES.md

**External Validation: Twitter Emotion Corpus**
- 4,394 tweets
- Transfer performance: ρ = 0.879

### **Lexicon (KEEL)**

**Kannada-English Emotion Lexicon**
- Availability: Request-based with institutional clearance
- License: CC BY-SA 4.0
- Fingerprint (SHA-256): `6a536dd437ba85b0`
- Contact: tejaswini@jssstuniv.in

See RESOURCES.md for details and request procedure.

---

## 📈 Paper Highlights

✅ **Novel Framework:** First emotion-aware cascade normalization for code-mixed Kannada-English  
✅ **Rigorous Audits:** Two-pass merge-precision protocol (κ = 0.902), language-ID audit (κ = 0.906)  
✅ **Complete Ablations:** Leave-one-out, guard arms, transliteration arms (10 conditions)  
✅ **Statistical Rigor:** Per-seed McNemar tests, effect sizes, external validation  
✅ **Reproducibility:** 32 public notebooks, fingerprint verification, GitHub release

---

## 📞 Contact

**Author:** Tejaswini M  
**Email:** tejaswini@jssstuniv.in  
**Affiliation:** JSS Science and Technology University (JSSSTU), Mysuru, India

---

## 📜 License

- **Code:** MIT License
- **Lexicon (KEEL):** CC BY-SA 4.0 (request-based, institutional clearance required)
- **Datasets:** See individual corpus documentation
