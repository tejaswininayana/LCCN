# LCCN
Label-Constrained Cascade Normalization for Emotion Detection in Kannada-English Code-Mixed Text
##  Overview

LCCN is a label-constrained cascade normalization framework for Kannada-English code-mixed social media text. This repository contains:
##  Key Results

- **Language-ID Agreement:** κ = 0.906 (almost perfect)
- **Merge-Precision Audit:** 580/1358 compatible (0.4271 overall precision)
- **LOO Ablation Gains:** +0.0050 F1 (emotion condition), −0.0007 F1 (cluster condition)
- **LCCN + IndicXlit:** +0.0105 F1 (p=0.0194) vs. raw baseline
- **External Validation (Twitter):** ρ = 0.879 (Spearman rank correlation)

---

##  Repository Contents

### Documentation Files
- **README.md** — This overview file
- **RESOURCES.md** — Corpus details, KEEL lexicon availability, baseline models
- **TABLES.md** — All results tables, statistical metrics, effect sizes

### Jupyter Notebooks (32 Total)

All notebooks are executable and available in this repository. Click on any file to view or download it.

#### Core Pipeline & Training
- lccn-r4-train (2).ipynb
- paper1-nb1-lccn-final (2).ipynb
- paper1-nb2-lccn-ml (2).ipynb
- paper1-nb3-lccn-dl (2).ipynb

#### Transformers & Language Models
- paper1-nb4-lccn-xlmroberta (2).ipynb
- paper1-nb5-lccn-muril (2).ipynb
- paper1-nb6-lccn-xlm43-44 (2).ipynb
- paper1-nb5-lccn-cross-dataset-validation (3).ipynb

#### Audits (Language-ID & Merge-Precision)
- lccn-r15-langid-audit (3).ipynb
- lccn-r17-merge-audit.ipynb
- r17-phase2-merge-precision (1).ipynb
- lccn-label-revision (2).ipynb
- paper1-lccn-merge (3).ipynb

#### Ablation Studies
- lccn-r16a-trainonly-arms.ipynb
- lccn-r16b-trainonly-xlmr.ipynb
- lccn-r21a-guard-arms.ipynb
- lccn-r21b-guard-xlmr.ipynb
- lccn-r22a-loo-arms.ipynb
- lccn-r22b-loo-xlmr (1).ipynb
- lccn-r22c-missing-seeds (1).ipynb
- lccn-r24a-xlit-arms.ipynb
- lccn-r24b-xlit-gpu.ipynb

#### Statistics & Sensitivity Analysis
- lccn-r13-perseed-stats (1).ipynb
- lccn-r13-perseed-stats-v2 (1).ipynb
- lccn-mcnemar (2).ipynb
- lccn-mcnemar (3).ipynb
- lccn-sensitivity (2).ipynb
- lccn-r23-external-bootstrap (2).ipynb
- lccn-r25-near-duplicates.ipynb

---

## Quick Start

### To View Notebooks
1. Scroll down to the file listing in this repository
2. Click on any `.ipynb` file
3. GitHub will render it automatically in your browser

### To Run Locally

```bash
git clone https://github.com/tejaswininaryana/LCCN.git
cd LCCN
pip install jupyter pandas numpy scikit-learn torch transformers
jupyter notebook
```

### To Reproduce Results

**Step 1: Core Pipeline**
- Run: `lccn-r4-train (2).ipynb`

**Step 2: Audits**
- Run: `lccn-r15-langid-audit (3).ipynb`
- Run: `r17-phase2-merge-precision (1).ipynb`

**Step 3: Ablations**
- Run: `lccn-r22b-loo-xlmr (1).ipynb`

**Step 4: Statistics**
- Run: `lccn-r13-perseed-stats-v2 (1).ipynb`
- Run: `lccn-mcnemar (3).ipynb`

---

## Datasets

### Kannada-English YouTube Emotion Corpus
- **Size:** 40,000 comments (28K train, 6K val, 6K test)
- **Classes:** 4 emotions (happy, anger, disgust, sad)
- **Agreement:** κ = 0.8313
- **Details:** See RESOURCES.md

### External Validation: Twitter Emotion Corpus
- **Size:** 4,394 tweets
- **Transfer Performance:** ρ = 0.879 (Spearman correlation)

### Lexicon (KEEL)
- **Name:** Kannada-English Emotion Lexicon
- **Availability:** Request-based with institutional clearance
- **License:** CC BY-SA 4.0
- **Fingerprint (SHA-256):** `6a536dd437ba85b0`
- **Contact:** tejaswini@jssstuniv.in

For lexicon request procedure, see RESOURCES.md

---

## Paper Highlights

 **Novel Framework:** First emotion-aware cascade normalization for code-mixed Kannada-English
**Rigorous Audits:** Two-pass merge-precision protocol (κ = 0.902), language-ID audit (κ = 0.906)
**Complete Ablations:** Leave-one-out, guard arms, transliteration arms across 10 conditions
**Statistical Rigor:** Per-seed McNemar tests, effect sizes, external validation on Twitter
 **Reproducibility:** 32 public notebooks, fingerprint verification, complete GitHub release


##  License

- **Code:** MIT License
- **Lexicon (KEEL):** CC BY-SA 4.0 (request-based, institutional clearance required)
- **Datasets:** See individual corpus documentation in RESOURCES.md



**GitHub Repository:** https://github.com/tejaswininaryana/LCCN  
**Manuscript Status:** Under major revision (IJIES)  
**Last Updated:** 2026-10-21
