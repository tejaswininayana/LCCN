# LCCN Paper: Resources & Data

---

## Corpus Details

**Kannada-English YouTube Emotion Corpus**
- **Size:** 40,000 comments
- **Tokens:** 444,541
- **Types:** 55,177 (TTR: 0.1241)
- **Classes:** 4 emotions (happy, anger, disgust, sad)
- **Annotation:** 3 annotators per comment
- **Agreement:** Fleiss' κ = 0.8313
- **Split:** 28K train, 6K val, 6K test (stratified by emotion)

| Emotion | Count | % |
|---------|-------|---|
| Happy | 10,000 | 25% |
| Anger | 10,000 | 25% |
| Disgust | 10,000 | 25% |
| Sad | 10,000 | 25% |

---

## Lexical Resources (KEEL)

**Kannada-English Emotion Lexicon (KEEL)**
- **Resource Type:** Three normalized lexicons used in cascade
  1. Lexicon-based normalization (direct mapping)
  2. KOPE: Phonetic matching
  3. Distributional: Similarity matching

- **Availability:** Request-based with institutional clearance
- **License:** CC BY-SA 4.0
- **SHA-256 Fingerprint:** `6a536dd437ba85b0`

**Why Restricted:**
- Related to patent application in progress
- Institutional IP clearance required
- Verification via fingerprint ensures reproducibility

**Request KEEL:**
Contact: tejaswini@jssstuniv.in  
Include: Your institution, research purpose, intended use

---

## External Validation

**Kannada-English Twitter Emotion Corpus**
- **Source:** [4] in references
- **Size:** 4,394 tweets
- **Classes:** 4 emotions (same as YouTube)
- **Transfer Success:** Spearman rank correlation ρ = 0.879

---

## Computational Resources Used

| Notebook | GPU | Epochs | Batch Size | Time |
|----------|-----|--------|------------|------|
| lccn-r15-langid-audit | CPU | — | — | ~5 min |
| lccn-r17-merge-audit | CPU | — | — | ~2 min |
| lccn-r22a-loo-arms | CPU | — | 32 | ~10 min |
| lccn-r22b-loo-xlmr | Tesla T4 | 10 | 32 | ~15 min |
| lccn-r22c-missing-seeds | Tesla T4 | 10 | 32 | ~20 min |
| paper1-nb4-lccn-xlmroberta | Tesla T4 | 10 | 32 | ~20 min |

**All notebooks run on Kaggle free tier (GPU quotas permitting)**

---

## Baseline Models

The paper evaluates 13 normalization methods:

| Category | Methods |
|----------|---------|
| Baseline | raw (no normalization) |
| Phonetic | Soundex, Metaphone, TERUN, KOPE |
| Guarded | Soundex_guard, IndicSoundex_guard |
| Transliteration | IndicXlit, IndicSoundex |
| Proposed | LCCN, LCCN-base, LCCN-IndicXlit, LCCN-IndicXlit-itrans |

---

## Classifiers Tested

- Logistic Regression (LR)
- Linear SVM
- Multinomial Naive Bayes (MNB)
- Random Forest (RF)
- XGBoost
- XLM-RoBERTa (transformer)

---

## Key Metrics

### Language Identification (Section 3.7 & Table 12)

| Threshold | P | R | F1 | F1_weighted |
|-----------|---|---|----|----|
| 2.0 | 0.811 | 0.846 | 0.8009 | 0.8012 |
| 2.5 | 0.757 | 0.854 | 0.8025 | 0.8047 |
| 3.0 | 0.702 | 0.849 | 0.8009 | 0.8010 |

**Selected:** 2.5 threshold (best balance)

### Merge Precision (Table 13)

| Category | Compatible | Incompatible | Unclear | Precision |
|----------|-----------|--------------|---------|-----------|
| Orthographic Kannada | 39 | 18 | 0 | 0.6842 |
| Phonetic Roman | 441 | 220 | 1 | 0.6662 |
| Unrelated Roman | 100 | 539 | 0 | 0.1565 |
| **OVERALL** | **580** | **777** | **1** | **0.4271** |

---

## Paper Highlights

✅ **Innovation:** First emotion-aware text normalization framework for code-mixed Kannada-English  
✅ **Rigor:** Two-pass audit protocol, 1,358 adjudicated pairs, κ=0.906 agreement  
✅ **Impact:** +0.0105 F1 improvement (p=0.0194) when combined with IndicXlit  
✅ **Reproducibility:** 32 public notebooks, resource fingerprint verification
