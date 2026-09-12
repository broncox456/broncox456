# Cristian Arias Ramírez, MD, MSc

**Nephrologist & Internal Medicine Specialist · Precision Medicine and Bioinformatics · Clinical Data Science · Real-World Evidence**

Practicing nephrologist in the Dominican Republic. I see the patients and I analyse the data — clinical questions come from the consultation room and the dialysis unit, and the answers are built with reproducible transcriptomic, proteomic and real-world clinical data pipelines.

📍 Santo Domingo / Baní, Dominican Republic · 🔗 [LinkedIn](https://www.linkedin.com/in/cristian-arias-healthcare-data/)

---

## Clinical + Computational Focus

```
Clinical Nephrology → Real-World Clinical Data → Bioinformatics → Multi-Omics → Precision Medicine
```

The bridge is the point. Molecular datasets are interpreted with a nephrologist's understanding of the disease; clinical datasets are analysed with a bioinformatician's discipline about reproducibility, cohort definition and what a result can and cannot support.

---

## Selected Research

### 1. DKD Multi-Omics — Kidney Tissue ↔ Urine
**Question** · Are molecular signals observed in kidney tissue preserved at the protein level in urine?
**Data** · Kidney tissue RNA-seq (GSE142025: control / early DKD / advanced DKD) + published urinary proteomics (~239 samples, DKD stage 3 vs 4). Unpaired, cross-compartment.
**Methods** · `limma` differential expression (adj. p < 0.05, |logFC| ≥ 1), gene-symbol harmonisation, concordance classification.
**Result** · 1,743 significant genes and 555 detected proteins, 81 overlapping. Concordance: 42 down–down, 9 up–up, 30 discordant. Dominant signal is metabolic/tubular decline (SORD, GSTA1/2, ALDH1L1, ASS1, MME) with complement-linked inflammatory activation (C3, CFH) — not fibrosis alone.
**Relevance** · Supports the feasibility of tracking tissue-level DKD biology through non-invasive urinary markers, and shows where that translation breaks down.
**Stack** · R (limma), Python · **Status** · Research project, public + published data; manuscript in preparation
→ [`dkd-multiomics-fibrosis-metabolism-signature`](https://github.com/broncox456/dkd-multiomics-fibrosis-metabolism-signature)

---

### 2. Intradialytic Hypotension — Real-World Hemodynamic Phenotyping
**Question** · Is intradialytic hypotension driven by the dialysis session, or by the patient?
**Data** · 394 hemodialysis sessions from 52 patients, extracted directly from Nikkiso DBB-06 machines at a Dominican dialysis unit. Real-world, longitudinal, machine-derived.
**Methods** · Feature engineering (ΔMAP, maximum systolic drop, UFR, IDWG), descriptive comparison by IDH status, a simple clinical risk score, and patient-level K-means clustering (k = 3).
**Result** · IDH rate 43.15% (170 events). Classical session-level predictors (UFR, IDWG, haemoglobin) discriminated poorly. Three hemodynamic phenotypes emerged; the most unstable one was **not** the highest-UFR group.
**Relevance** · Argues for phenotype-based risk stratification and individualised ultrafiltration rather than session-parameter thresholds.
**Stack** · Python (pandas, scikit-learn) · **Status** · Retrospective observational analysis; exploratory ML model presented as poster and oral conference at the XIV Congreso Dominicano de Nefrología / VI Encuentro Mayo Clinic (2025); manuscript in preparation
→ [`hemodialysis-intradialytic-hypotension-risk-analysis`](https://github.com/broncox456/hemodialysis-intradialytic-hypotension-risk-analysis)

---

### 3. CKD in Dominican Primary Care — Real-World Evidence and Social Determinants
**Question** · What is the CKD burden detected by primary-care screening in a low-resource setting, and which social barriers shape it?
**Data** · UNAPS primary-care screening cohort, n = 400, Peravia province; nested sociodemographic subcohort, n = 50 linked patients.
**Methods** · Reproducible Python pipeline: data audit → cleaning → derived-ID linkage → quality-control flagging of discordant fields → descriptive epidemiology → sociodemographic analysis.
**Result** · Substantial renal-risk burden with hypertension and diabetes as dominant drivers; the linked subcohort surfaces education, insurance coverage and economic barriers that clinical variables alone do not capture. Linkage inconsistencies were flagged rather than silently harmonised.
**Relevance** · Directly usable for prevention policy and health-system planning in underserved settings.
**Stack** · Python (pandas, matplotlib) · **Status** · Cross-sectional descriptive study; manuscript in preparation
→ [`ckd-primary-care-dominican-republic`](https://github.com/broncox456/ckd-primary-care-dominican-republic)

---

### 4. TCGA-KIRC — Multi-Omics Survival Stratification
**Question** · Can proteomic profiling identify renal-cancer subgroups with distinct survival, and is the signal reproduced at RNA level?
**Data** · TCGA-KIRC, 475 patients with matched RNA-seq and RPPA.
**Methods** · 11-script reproducible R workflow: acquisition → cohort matching → unsupervised clustering → survival comparison → cross-layer marker discovery.
**Result** · Two proteomic clusters; the smaller subgroup (n = 86) showed a higher event rate (~39% vs ~34%) and concordant protein/RNA signatures of proliferative signalling, DNA-repair activation and metabolic dysregulation.
**Relevance** · Demonstrates cross-layer multi-omics integration with survival endpoints; hypothesis-generating, not a prognostic classifier.
**Stack** · R (survival, clustering, differential analysis) · **Status** · Public-data reanalysis; no external validation
→ [`tcga-kirc-multiomics-survival-signature`](https://github.com/broncox456/tcga-kirc-multiomics-survival-signature)

---

### 5. Human Kidney Single-Cell Injury Transcriptomics
**Question** · Which cell populations and cell *states* carry the injury signal in human kidney tissue?
**Data** · GSE131685, human kidney scRNA-seq.
**Methods** · Seurat v5 pipeline — QC (nFeature_RNA 200–6,000; mitochondrial ≤ 15%), normalisation, clustering, manual marker-based annotation.
**Result** · Resolved nephron segments (proximal tubule, distal tubule, collecting duct) alongside T/NK, B and myeloid populations, with transcriptional programmes consistent with oxidative stress and epithelial injury across multiple compartments.
**Relevance** · Kidney injury reads as a multi-compartment process, not a single-cell-type event — the framing that precision nephrology depends on.
**Stack** · R (Seurat v5, dplyr, ggplot2) · **Status** · Public-data reanalysis; manual annotation, no trajectory analysis
→ [`human-kidney-singlecell-injury-transcriptomic-analysis`](https://github.com/broncox456/human-kidney-singlecell-injury-transcriptomic-analysis)

---

## Supporting Work

| Project | Data | Result | Status |
|---|---|---|---|
| [FSGS RNA-seq fibrosis/inflammation signature](https://github.com/broncox456/fsgs-rnaseq-fibrosis-inflammation-signature) | NEPTUNE-derived RNA-seq (GSE254957 / GSE197307) | Two transcriptomic clusters (11 vs 90 samples); DESeq2 + GO/KEGG enrichment showing ECM-remodelling and immune activation | Public-data reanalysis; unbalanced clusters, no external validation |
| [Lupus nephritis glomerular signature](https://github.com/broncox456/lupus-nephritis-glomerular-signature) | GSE32591, glomerular compartment, 46 samples (32 LN / 14 control) | Interferon-driven signature: IFI44, IFI44L, MX1, MX2, TYROBP, C1QA | Public-data reanalysis |
| [CKD transcriptomics — MSc thesis](https://github.com/broncox456/tfm-erc-transcriptomica) | GSE12682, 52 samples (23 CKD / 29 control), Affymetrix | 365 differentially expressed genes (138 up / 227 down); inflammatory–fibrotic activation and ECM remodelling; `renv`-pinned reproducible pipeline | MSc thesis, Universidad Alfonso X el Sabio |
| [Glomerulonephritis gene-prioritisation pipeline](https://github.com/broncox456/gn-gene-prioritization-pipeline) | Public expression data | Reproducible ranking combining effect size, significance and renal relevance | Methodological / educational pipeline — explicitly not a diagnostic or biomarker-validation tool |

### Methodological Demonstration — Synthetic Data
[`hemodialysis-survival-catheter-vs-fistula-ml`](https://github.com/broncox456/hemodialysis-survival-catheter-vs-fistula-ml) — XGBoost + SHAP model for 1-year mortality in hemodialysis, examining vascular access, inflammation and nutritional status.
**The dataset is synthetic (n = 2,500), clinically grounded but not a real registry.** Held-out test ROC-AUC 0.758; cross-validated ROC-AUC ≈ 0.63 (± 0.04), i.e. moderate and unstable. Built to demonstrate modelling, interpretability and clinical reasoning — **not** a validated or deployable clinical tool.

---

## Research Areas

Chronic kidney disease · Diabetic kidney disease · Glomerular disease (FSGS, lupus nephritis) · Hemodialysis outcomes and risk stratification · Kidney precision medicine · Biomarker discovery · Multi-omics integration · Transcriptomics and single-cell analysis · Real-world evidence · Clinical epidemiology in low-resource settings

## Technical Toolkit

**R** — limma, DESeq2, Seurat v5, clusterProfiler, survival, Bioconductor, renv
**Python** — pandas, scikit-learn, XGBoost, SHAP, matplotlib
**Data & reporting** — SQL, Power BI
**Practice** — reproducible pipelines, scripted end-to-end workflows, documented QC and linkage decisions, version control

## Presentations

- *El futuro de la Nefrología Dominicana* — exploratory machine-learning model for intradialytic hypotension. Poster and oral conference, XIV Congreso Dominicano de Nefrología / VI Encuentro Mayo Clinic, 2025.
- *Estrategias de Prevención y Manejo de la Enfermedad Renal Crónica en la Población Rural* — invited lecture, 2021.

Manuscripts in preparation: DKD multi-omics; intradialytic hypotension phenotyping; CKD in Peravia primary care. No claim of acceptance or publication is made for these.

## Current Interests

Kidney precision medicine for Latin American and Caribbean populations; non-invasive biomarkers in diabetic kidney disease; phenotype-based risk stratification in dialysis; making real-world clinical data from low-resource health systems usable for research.

## Training

MD, Universidad Autónoma de Santo Domingo · Internal Medicine (2016) and Nephrology (2019), UASD / Hospital Docente Padre Billini · MSc in Bioinformatics (Máster Universitario en Bioinformática), Universidad Alfonso X el Sabio, Spain — studies completed July 2026

Member, Scientific and Research Committee — Sociedad Dominicana de Nefrología (SODONEF), 2026 Board · Research Committee Board Member, Hospital Nuestra Señora de Regla

---

**Disclaimer** — Every repository here is research or methodological work. None of it is a validated clinical decision-support tool, none has regulatory clearance, and none should be used for patient-level decisions. Datasets are public, published, de-identified, or synthetic; raw identifiable clinical data are not shared.

📩 Open to collaboration and to roles in precision medicine, translational and clinical research, clinical data science and real-world evidence — [LinkedIn](https://www.linkedin.com/in/cristian-arias-healthcare-data/) · [ORCID 0009-0009-7503-222X](https://orcid.org/0009-0009-7503-222X)
