# AIWG Metformin & GLP-1 Clinical Decision Support

A client-side clinical decision support (CDS) web application operationalizing the consensus guideline by **Carolan et al. (*Schizophrenia Bulletin*, 2024; DOI: `10.1093/schbul/sbae205`)** for the prevention and management of antipsychotic-induced weight gain (AIWG)[cite: 1].

---

## Clinical Scope & Core Principles

* **Prevalence & Baseline Risk:** 8 in 10 individuals experience antipsychotic-induced weight gain, and individuals with low or normal baseline BMI are at higher risk of clinically significant weight increases[cite: 1].
* **Primary Determinant:** Choice of antipsychotic is the most important baseline risk factor predicting AIWG[cite: 1].
* **Off-Label Prescribing:** Metformin for preventing or treating AIWG and improving cardiometabolic outcomes is an **unlicensed (off-label) indication**[cite: 1].
* **Lifestyle Foundation:** Dietary and exercise interventions should be provided to all patients taking antipsychotic medication and continued if metformin is commenced[cite: 1].

---

## Decision Pathways Implemented

### 1. Antipsychotic Risk Tiers (Initiation, Switch, or Year 1 Review)
* **High Risk (*Olanzapine, Clozapine* — Not first line):** Co-commence metformin immediately alongside lifestyle interventions[cite: 1].
* **Medium Risk (*Quetiapine, Paliperidone, Risperidone*):** Co-commence metformin if **at least one** of the following applies:
  * Hypertension
  * Dyslipidaemia
  * Diabetes (Type 1 or Type 2)
  * Pre-diabetes (HbA1c `42–47 mmol/mol` or fasting glucose `6.1–6.9 mmol/L`)
  * Overweight BMI (`> 25 kg/m²`, adjusted to `> 23 kg/m²` for South Asian, East Asian, Chinese, Black African/Caribbean, or Middle Eastern backgrounds)
  * Age `10–25 years`
  * Or commence if **>3% weight gain** occurs at any time during Year 1[cite: 1].
* **Lower Risk (*All other antipsychotics*):** Provide lifestyle interventions and commence metformin if **>3% weight gain** occurs during Year 1 (for young persons aged 10–25, defined as >3% weight gained outside expected growth trajectory)[cite: 1].

### 2. GLP-1 Agonist Eligibility & Fallback Rule
* **Indication:** Commence a **GLP-1 Agonist** if **BMI ≥ 30 kg/m²**, or **BMI 27–30 kg/m²** with one of: Hypertension, Dyslipidaemia, Diabetes (Type 1 or 2), Pre-diabetes, or Obstructive sleep apnoea[cite: 1].
* **Fallback:** If a GLP-1 Agonist is unavailable, **commence metformin** instead[cite: 1].

---

## Dosing, Safety & Monitoring Rules

* **Pre-Treatment Check:** Mandatory baseline renal function (GFR) assessment[cite: 1].
* **Contraindications (*Avoid metformin with*):**
  * Acute metabolic acidosis
  * Severe renal failure (`GFR < 30 mL/min`)
  * Hepatic insufficiency
  * Acute physical illness (dehydration, severe infection) or harmful alcohol use[cite: 1].
* **Dose Escalation Schedule:**
  * **Week 1:** 500 mg morning (500 mg/day)
  * **Week 2:** 500 mg morning + 500 mg evening (1,000 mg/day) — *check for efficacy*
  * **Week 4:** 1 g morning + 500 mg evening (1,500 mg/day) — *check for efficacy*
  * **Week 6:** 1 g morning + 1 g evening (2,000 mg/day; target `1–2 g/day` taken with or after food; once-daily slow-release tablet optional for GI tolerance or adherence)
  * **Renal Cap:** If `GFR 30–44 mL/min`, maximum dose is capped at **1 g/day**[cite: 1].
* **Ongoing Monitoring:**
  * Weight/BMI and signs/symptoms of lactic acidosis (dyspnoea, muscle cramps, abdominal pain, hypothermia, asthenia)
  * Liver function and HbA1c **annually**
  * Renal function (GFR) **annually**, or **every 6 months** if `> 75 years` or taking concomitant NSAIDs, ACE inhibitors, ARBs, or diuretics (especially loop diuretics)
  * Vitamin B12 **annually**, or **every 6 months** if vegan diet, bariatric surgery, prescribed PPI or colchicine, older age, or GI malabsorption disorders[cite: 1].
* **Discontinuation Thresholds (*When to stop*):**
  * Suspected lactic acidosis or acute risk factors (dehydration, acute alcohol intoxication, decompensated heart/respiratory failure, recent MI, shock, severe infection)
  * Prior to or at administration of iodinated contrast agents (restart `≥ 48 hours` after)
  * `GFR < 30 mL/min`
  * `BMI < 20 kg/m²`
  * Sick day rule (systemically unwell; restart when well)
  * Antipsychotic medication is stopped[cite: 1].

---

## Technical Architecture & Privacy

* **Stack:** Single-file static HTML5, Tailwind CSS (CDN), and vanilla JavaScript—zero build step or backend dependencies.
* **Privacy:** Runs 100% client-side in the browser. No patient identifiers or clinical inputs are stored, logged, or transmitted.
* **EMR Export:** Generates a structured plain-text clinical decision note with one-click clipboard copy for Electronic Medical Record documentation.

---

## Reference

Carolan A, Hynes-Ryan C, Agarwal SM, et al. Guideline on Metformin for Prevention of Antipsychotic-Induced Weight Gain. *Schizophrenia Bulletin*. 2024; sbae205. DOI: `10.1093/schbul/sbae205`[cite: 1].
