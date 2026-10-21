# LCCN
Label-Constrained Cascade Normalization for Emotion Detection in Kannada-English Code-Mixed Text
## 📋 Overview

This repository contains supplementary resources and reproducibility information for the LCCN paper on emotion detection in Kannada-English code-mixed social media text.

The paper proposes Label-Constrained Cascade Normalization (LCCN), a framework that formulates text normalization as a constrained learning-to-rank problem with six emotion-aware conditions to filter harmful merges of morphological variants.

**Key Results:**
- LCCN + IndicXlit: +0.0105 F1 (p=0.0194)
- Merge precision: 0.4271 (580/1358 judgments)
- Language-ID agreement: κ=0.906
- External validation ρ=0.879 (Kannada-English Twitter corpus)

---

## 🔗 Reproducibility

### Kannada-English Emotion Lexicon (KEEL)
- **Availability:** Request-based with institutional clearance
- **Fingerprint (SHA-256):** `6a536dd437ba85b0`
- **License:** CC BY-SA 4.0
- **Contact:** tejaswini@jssstuniv.in

### Complete Computational Code

All computation is implemented in 32 Jupyter notebooks (executed with cached outputs):

**Core Pipeline & Training**
- [paper1-nb1-lccn-final](paper1-nb1-lccn-final__2_.ipynb) — Core LCCN pipeline v5.3
- [lccn-r4-train](lccn-r4-train__2_.ipynb) — Training protocol
- [paper1-nb2-lccn-ml](paper1-nb2-lccn-ml__2_.ipynb) — Classical ML (LR, SVM, RF, XGB, MNB)
- [paper1-nb3-lccn-dl](paper1-nb3-lccn-dl__2_.ipynb) — Deep learning setup

**Transformer Models**
- [paper1-nb4-lccn-xlmroberta](paper1-nb4-lccn-xlmroberta__2_.ipynb) — XLM-RoBERTa (seed 42)
- [paper1-nb6-lccn-xlm43-44](paper1-nb6-lccn-xlm43-44__2_.ipynb) — XLM-RoBERTa (seeds 43, 44)
- [paper1-nb5-lccn-muril](paper1-nb5-lccn-muril__2_.ipynb) — MURIL transformer

**External Validation & Cross-Dataset**
- [paper1-nb5-lccn-cross-dataset-validation](paper1-nb5-lccn-cross-dataset-validation__3_.ipynb) — Twitter corpus validation
- [lccn-r23-external-bootstrap](lccn-r23-external-bootstrap__2_.ipynb) — Bootstrap validation

**Audits & Quality Control**
- [lccn-r15-langid-audit](lccn-r15-langid-audit__3_.ipynb) — Language-ID audit (κ=0.906)
- [r17-phase2-merge-precision](r17-phase2-merge-precision__1_.ipynb) — Merge-precision (Table 13)
- [lccn-label-revision](lccn-label-revision__2_.ipynb) — Label revision audit
- [paper1-lccn-merge](paper1-lccn-merge__3_.ipynb) — Merge analysis

**Ablation Studies**
- [lccn-r16a-trainonly-arms](lccn-r16a-trainonly-arms.ipynb) — Train-only condition (classical)
- [lccn-r16b-trainonly-xlmr](lccn-r16b-trainonly-xlmr.ipynb) — Train-only condition (XLM-R)
- [lccn-r21a-guard-arms](lccn-r21a-guard-arms.ipynb) — Guard arms (classical)
- [lccn-r22a-loo-arms](lccn-r22a-loo-arms.ipynb) — Leave-one-out (classical)
- [lccn-r22b-loo-xlmr](lccn-r22b-loo-xlmr__1_.ipynb) — Leave-one-out (XLM-R seed 42)
- [lccn-r22c-missing-seeds](lccn-r22c-missing-seeds__1_.ipynb) — Leave-one-out (seeds 43, 44)
- [lccn-r24a-xlit-arms](lccn-r24a-xlit-arms.ipynb) — IndicXlit arms (classical)
- [lccn-r24b-xlit-gpu](lccn-r24b-xlit-gpu.ipynb) — IndicXlit arms (XLM-R)

**Statistical Analysis & Sensitivity**
- [lccn-r13-perseed-stats](lccn-r13-perseed-stats__1_.ipynb) — Per-seed statistics (McNemar)
- [lccn-r13-perseed-stats-v2](lccn-r13-perseed-stats-v2__1_.ipynb) — Per-seed statistics v2
- [lccn-mcnemar](lccn-mcnemar__3_.ipynb) — McNemar significance tests
- [lccn-sensitivity](lccn-sensitivity__2_.ipynb) — Language-ID threshold sensitivity
- [lccn-r25-near-duplicates](lccn-r25-near-duplicates.ipynb) — Near-duplicate detection

**See [TABLES.md](TABLES.md) and [RESOURCES.md](RESOURCES.md) for:**
- Table 8: Per-seed statistics (McNemar p-values)
- Table 12: Language-ID threshold sensitivity
- Table 13: Merge-precision breakdown
- Corpus statistics & external validation results

---

## 📊 Results Summary

- **LCCN + IndicXlit:** +0.0105 F1 (p=0.0194) vs. raw
- **Language-ID:** κ=0.906 (almost perfect agreement)
- **Merge precision:** 0.4271 (580 compatible of 1,358)
- **External validation:** ρ=0.879 (Twitter corpus)



## 📧 Contact

For questions about the paper, code, or KEEL resource access:
- **Tejaswini M:** tejaswini@jssstuniv.in
- **Dr. Anil Kumar K M:** (supervisor contact through department)

---

## 📜 License

Code and documentation: MIT License  
KEEL Resource: CC BY-SA 4.0 (restricted, request-based)

---
