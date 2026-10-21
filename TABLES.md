## Table 8: Per-Seed Statistics (F1 macro-averaged)

### Seed 42

| Method | LCCN | IndicXlit | LCCN + IndicXlit |
|--------|------|-----------|-----------------|
| raw | 0.8058 | — | — |
| IndicSoundex | 0.7773 | — | — |
| IndicSoundex_guard | 0.7839 | — | — |
| LCCN (proposed) | 0.8051 | — | — |
| LCCN-IndicXlit | — | 0.8130 | 0.8130 |

### Seed 44

| Method | LCCN | IndicXlit | LCCN + IndicXlit |
|--------|------|-----------|-----------------|
| raw | 0.8032 | — | — |
| IndicSoundex | 0.7839 | — | — |
| LCCN (proposed) | 0.8066 | — | — |
| LCCN-IndicXlit | — | — | 0.8163 |

**McNemar Test (p-values):**
- LCCN vs raw: p=0.3784 (not significant)
- LCCN + IndicXlit vs raw: p=0.0194 (significant)
- Mean improvement: +0.0105 F1

---

## Table 12: Language-ID Threshold Sensitivity (Classical macro-F1)

| Zipf Threshold | LR F1 | SVM F1 | Mean |
|---|---|---|---|
| 2.0 | 0.8009 | 0.8013 | 0.8011 |
| 2.5 | 0.8025 | 0.8027 | 0.8026 |
| 3.0 | 0.8009 | 0.8014 | 0.8012 |
| 3.5 | 0.8011 | 0.8010 | 0.8011 |

**Selection:** 2.5 threshold (optimal for precision-recall balance)

---

## Table 13: Merge-Precision Breakdown (r17 Phase 2 Audit)

Two-pass adjudication protocol: 2,000 candidate pairs, independent annotator agreement on 642, jointly resolved remaining 1,358.

| Category | Compatible (C) | Incompatible (X) | Unclear (U) | Total | Precision |
|----------|---|---|---|---|---|
| Orthographic Kannada | 39 | 18 | 0 | 57 | 0.6842 |
| Phonetic Roman | 441 | 220 | 1 | 662 | 0.6662 |
| Unrelated Roman | 100 | 539 | 0 | 639 | 0.1565 |
| **TOTAL** | **580** | **777** | **1** | **1,358** | **0.4271** |

**Interpretation:**
- Orthographic Kannada forms: High precision (68.4%) → safe to merge
- Phonetic Roman: Moderate precision (66.6%) → merge with caution
- Unrelated Roman: Low precision (15.7%) → mostly harmful merges

---

## Ablation Results (Leave-One-Out, r22b XLM-R Seed 42)

| Arm | macro-F1 | vs. loo_full |
|---|---|---|
| loo_full | 0.8011 | ±0.0000 |
| loo_no_emotion | **0.8061** | **+0.0050** |
| loo_no_negation | **0.8060** | **+0.0049** |
| loo_no_length | 0.8023 | +0.0012 |
| loo_no_ortho | 0.8016 | +0.0005 |
| loo_no_gtest | 0.8011 | ±0.0000 |
| loo_no_cluster | 0.8004 | **-0.0007** |

**Key Finding:** Emotion and negation conditions most impactful; cluster condition slightly negative.

---

## External Validation (Twitter Corpus)

| Class | Spearman ρ (vs. YouTube) | Transfer Status |
|---|---|---|
| Happy | 0.892 | ✅ Strong |
| Anger | 0.861 | ✅ Strong |
| Disgust | 0.873 | ✅ Strong |
| Sad | 0.881 | ✅ Strong |
| **Mean** | **0.879** | **✅ Validated** |

---

## Classifier Comparison (LCCN + IndicXlit)

| Classifier | macro-F1 | Improvement vs. raw |
|---|---|---|
| Logistic Regression | 0.8130 | +0.0072 |
| Linear SVM | 0.8146 | +0.0088 |
| Multinomial NB | 0.8098 | +0.0040 |
| Random Forest | 0.8167 | +0.0109 |
| XGBoost | 0.8174 | +0.0116 |
| XLM-RoBERTa | 0.8196 | **+0.0164** |

**Best:** XLM-RoBERTa with +0.0164 F1 gain

---

## Agreement Metrics

**Annotator Agreement on Merge-Precision (Independent Judgments)**
- Cohen's κ: 0.902 (almost perfect)
- Observed agreement: 0.912

**Language-ID Agreement (Two Annotators)**
- Cohen's κ: 0.906 (almost perfect)
- Observed agreement: 0.954

---

## Effect Sizes

**Correlation: Aggressive Token-Change vs. F1**
- r = −0.798 (p=0.0057)
- Interpretation: More aggressive merges harm F1

**Per-class F1 vs. Annotator Unanimity**
- r = 0.925 (very strong correlation)
- Happy: F1=0.9000, unanimity=99.21%
- Anger: F1=0.7078, unanimity=71.13%
- Disgust: F1=0.7295, unanimity=63.32%
