# Liver Disease: Comprehensive Clinical Reference

**Purpose:** Open WebUI RAG knowledge base for clinical decision support.
**Scope:** Cirrhosis, portal hypertension complications, NAFLD/NASH, alcoholic liver disease, viral hepatitis, DILI, acute liver failure, transplant, autoimmune and cholestatic diseases.
**Chunking guidance:** Each ## or ### section is designed as an independent RAG chunk.

---

## Cirrhosis Overview

Cirrhosis is the end-stage of chronic liver injury characterized by replacement of normal hepatic parenchyma with fibrotic scar tissue and regenerative nodules, resulting in loss of normal hepatic architecture and function.

### Etiology of Cirrhosis

Common causes of cirrhosis in the United States and worldwide:

| Etiology | Key Features | Prevalence |
|---|---|---|
| Alcohol-related liver disease (ALD) | History of heavy alcohol use; typically >40g/day men, >20g/day women for years | ~30-40% of cases |
| NAFLD/NASH | Metabolic syndrome, obesity, T2DM, dyslipidemia; steatosis on imaging | ~25-30% of cases |
| Chronic hepatitis C (HCV) | Anti-HCV positive, HCV RNA detectable; genotype matters for treatment | ~15-20% of cases |
| Chronic hepatitis B (HBV) | HBsAg positive >6 months; HBeAg/HBV DNA quantification | ~5-10% of cases |
| Autoimmune hepatitis (AIH) | Elevated IgG, ANA/anti-SMA positive, interface hepatitis on biopsy | ~5% of cases |
| Primary biliary cholangitis (PBC) | Anti-mitochondrial antibody (AMA) positive; cholestatic pattern | ~3-5% of cases |
| Primary sclerosing cholangitis (PSC) | ERCP/MRCP: beading of bile ducts; associated with IBD | ~2-4% of cases |
| Hemochromatosis | HFE gene mutation; elevated transferrin saturation, ferritin | ~2-3% of cases |
| Wilson's disease | Kayser-Fleischer rings; low ceruloplasmin; young patients | Rare (~1%) |
| Cryptogenic | No identifiable cause; often burnt-out NASH | ~5-10% of cases |

Additional less common causes:
- Alpha-1 antitrypsin deficiency (PiZZ phenotype)
- Budd-Chiari syndrome (hepatic vein thrombosis)
- Cardiac cirrhosis (congestive heart failure, constrictive pericarditis)
- Drug-induced (methotrexate, amiodarone)
- Biliary atresia (pediatric)
- Schistosomiasis (worldwide leading cause of portal hypertension)

### Compensated vs. Decompensated Cirrhosis

#### Compensated Cirrhosis
- Liver maintains enough synthetic and metabolic function to sustain life without major complications
- Often asymptomatic; may have fatigue, spider angiomata, palmar erythema, leukonychia
- Thrombocytopenia and splenomegaly may be present (portal hypertension)
- Median survival: >12 years
- Transition to decompensated state: ~5-7% per year

#### Decompensated Cirrhosis
Defined by the presence of one or more of the following complications:

1. **Ascites** — Most common first decompensating event (~50-60% of cases at time of first decompensation). Results from portal hypertension + sodium retention.
2. **Variceal hemorrhage** — Upper GI bleed from rupture of esophageal or gastric varices. Life-threatening; 6-week mortality ~20-30%.
3. **Hepatic encephalopathy (HE)** — Neuropsychiatric dysfunction from accumulation of ammonia and other neurotoxins.
4. **Jaundice** — Bilirubin elevation due to failure of hepatic conjugation and excretion. Total bilirubin >2mg/dL clinically apparent.
5. **Spontaneous bacterial peritonitis (SBP)** — Bacterial infection of ascitic fluid without obvious intra-abdominal source.
6. **Hepatorenal syndrome (HRS)** — Functional renal failure in setting of advanced liver disease.

Prognosis after first decompensation: median survival ~2 years without transplant.

---

## Child-Pugh Score

The Child-Pugh score is a widely used clinical scoring system to assess severity of cirrhosis and prognosis.

### Child-Pugh Scoring Table

| Parameter | 1 Point | 2 Points | 3 Points |
|---|---|---|---|
| Total Bilirubin (mg/dL) | <2.0 | 2.0 - 3.0 | >3.0 |
| Serum Albumin (g/dL) | >3.5 | 2.8 - 3.5 | <2.8 |
| PT Prolongation (seconds) / INR | <4 sec / <1.7 | 4-6 sec / 1.7-2.3 | >6 sec / >2.3 |
| Ascites | None | Mild to moderate (diuretic-responsive) | Severe (diuretic-refractory) |
| Hepatic Encephalopathy | None | Grade 1-2 | Grade 3-4 |

### Child-Pugh Classification

| Class | Total Score | 1-Year Survival | 2-Year Survival | Interpretation |
|---|---|---|---|---|
| A | 5-6 | ~100% | ~85% | Well-compensated cirrhosis |
| B | 7-9 | ~80% | ~60% | Significant functional compromise |
| C | 10-15 | ~45% | ~35% | Decompensated cirrhosis |

Clinical uses of Child-Pugh:
- Assessing operative risk for hepatic resection
- Predicting 30-day mortality for variceal hemorrhage
- TIPS procedure candidacy
- Dosing guidance for hepatically metabolized drugs
- Limitations: subjective components (ascites, encephalopathy grading); does not incorporate renal function

---

## MELD and MELD-Na Scores

### MELD Score

The Model for End-Stage Liver Disease (MELD) score predicts 90-day mortality in cirrhotic patients and drives organ allocation in the United States.

**MELD Formula:**
```
MELD = 3.78 x [ln(serum bilirubin mg/dL)]
      + 11.2 x [ln(INR)]
      + 9.57 x [ln(serum creatinine mg/dL)]
      + 6.43
```

Rules for laboratory values:
- Minimum value for bilirubin, INR, and creatinine: 1.0 (to avoid negative log values)
- Maximum creatinine: 4.0 mg/dL (dialysis patients capped at 4.0)
- Values used should be most recent lab results within 48 hours

### MELD-Na Score

MELD-Na incorporates serum sodium to better capture patients with refractory ascites (who have worse prognosis than MELD alone predicts).

**MELD-Na Formula:**
```
MELD-Na = MELD
          + 1.32 x (137 - Na)
          - [0.24 x (137 - Na) x MELD]
```

Rules for sodium:
- Minimum sodium value used: 125 mEq/L
- Maximum sodium value used: 137 mEq/L (values above 137 have no effect on score)
- Hypervolemic or dilutional hyponatremia is the relevant clinical context

### MELD Score Interpretation

| MELD Score | 90-Day Mortality | Clinical Significance |
|---|---|---|
| <10 | ~2% | Low mortality risk; transplant may not be urgently needed |
| 10-14 | ~6% | Moderate risk; evaluate for transplant listing |
| 15-19 | ~20% | Transplant listing strongly considered (threshold for benefit) |
| 20-29 | ~40% | High mortality; active transplant candidacy |
| 30-39 | ~55-60% | Very high mortality; urgent transplant evaluation |
| >=40 | >70% | Extremely high mortality; critical transplant priority |

MELD >=15: The threshold at which the survival benefit of liver transplantation exceeds the surgical risk.

---

## Non-Invasive Fibrosis Markers

### Platelet Count as Cirrhosis Proxy

Thrombocytopenia is a marker of portal hypertension due to splenic sequestration and reduced thrombopoietin production by the injured liver.

- Platelet count <150,000/mm3: suggests advanced fibrosis or cirrhosis (sensitivity ~50%, specificity ~80%)
- Platelet count <100,000/mm3: strongly associated with clinically significant portal hypertension
- Platelet count <50,000/mm3: very high risk of variceal hemorrhage

Platelet count alone is insufficient for diagnosis but useful as a quick screening tool.

### FIB-4 Index

**Formula:**
```
FIB-4 = (Age [years] x AST [U/L]) / (Platelet count [10^9/L] x sqrt(ALT [U/L]))
```

**Interpretation:**

| FIB-4 Value | Fibrosis Stage | Clinical Action |
|---|---|---|
| <1.30 | F0-F1 (minimal fibrosis) | Low risk; routine monitoring |
| 1.30 - 2.67 | Indeterminate | Consider liver biopsy or elastography |
| >2.67 | F3-F4 (advanced fibrosis/cirrhosis) | High risk; specialist referral |

FIB-4 <1.30 has a negative predictive value of ~90% for advanced fibrosis in NAFLD populations. FIB-4 is the preferred non-invasive test in most NAFLD/NASH guidelines for initial fibrosis risk stratification.

### APRI Score (Alternative)

APRI (AST to Platelet Ratio Index):
```
APRI = (AST / Upper Limit of Normal for AST) x 100 / Platelet count (10^9/L)
```
- <0.5: low probability of significant fibrosis
- >1.5: high probability of significant fibrosis
- Primarily used in HCV; less validated in NAFLD

### Liver Elastography

- Transient elastography (FibroScan): measures liver stiffness in kPa
  - <7.0 kPa: minimal fibrosis (F0-F1)
  - 7.0-9.5 kPa: significant fibrosis (F2)
  - 9.5-12.5 kPa: severe fibrosis (F3)
  - >12.5 kPa: cirrhosis (F4)
  - Limitations: obesity, ascites, inflammation (falsely elevated stiffness)
- MR elastography: more accurate, not limited by obesity; reference standard for non-invasive fibrosis assessment

---

## Portal Hypertension

Portal hypertension is defined as an elevated hepatic venous pressure gradient (HVPG) >=5 mmHg. It is the primary driver of the major complications of cirrhosis.

- Clinically significant portal hypertension (CSPH): HVPG >=10 mmHg
- At HVPG >=10 mmHg: risk of varices, decompensation
- At HVPG >=12 mmHg: risk of variceal hemorrhage

Consequences of portal hypertension:
- Esophageal and gastric varices
- Ascites
- Hepatic encephalopathy
- Splenomegaly with thrombocytopenia
- Hepatorenal syndrome
- Hepatopulmonary syndrome
- Portopulmonary hypertension
- Spontaneous bacterial peritonitis

---

## Esophageal and Gastric Varices

### Screening and Surveillance

- All newly diagnosed cirrhotic patients should undergo upper endoscopy (EGD) to screen for varices
- Compensated cirrhosis without varices: repeat EGD every 2-3 years
- Compensated cirrhosis with small varices: repeat EGD every 1-2 years
- Decompensated cirrhosis: repeat EGD every 1 year
- Baveno VII consensus: transient elastography + platelet count can identify patients who can safely avoid screening endoscopy (LSM <20 kPa + platelets >150,000/mm3 = low risk)

### High-Risk Variceal Features

Endoscopic features that predict bleeding risk:
- Large varices (>5mm diameter)
- Red wale signs (longitudinal red streaks on varices)
- Red spots or cherry red spots
- Location in the distal esophagus
- Child-Pugh Class B or C status

### Primary Prophylaxis of Variceal Hemorrhage

Goal: prevent first variceal bleed in patients with medium or large varices, or small varices with high-risk features.

#### Non-Selective Beta-Blockers (NSBB)

Mechanism: reduce portal pressure by decreasing cardiac output (beta-1 blockade) and causing splanchnic vasoconstriction (beta-2 blockade).

| Drug | Starting Dose | Target Dose | Titration Goal |
|---|---|---|---|
| Propranolol | 20-40mg BID | 80-160mg BID | Resting HR 55-60 bpm; max tolerated dose |
| Nadolol | 40mg daily | 80-240mg daily | Resting HR 55-60 bpm; max tolerated dose |
| Carvedilol | 6.25mg daily | 12.5mg BID | Preferred in Child B/C; lower systolic BP by >=10mmHg; resting HR 55-60 bpm |

Carvedilol advantages: also has alpha-1 blocking activity, providing additional portal pressure reduction. More effective than nadolol in some studies. Preferred agent per current guidelines.

NSBB contraindications:
- Systolic BP <90 mmHg
- Resting heart rate <55 bpm
- Severe reactive airway disease (asthma)
- Second or third degree heart block
- Refractory ascites (relative contraindication — may worsen hyponatremia and renal function; NSBB may need to be held or reduced)

#### Endoscopic Variceal Ligation (EVL)

Indicated for:
- Large varices (>5mm)
- Small varices with red wale signs
- Child-Pugh Class B or C with any variceal size
- Patients intolerant of or with contraindications to NSBB

EVL procedure:
- Band ligation every 2-4 weeks until varices are obliterated
- Follow-up EGD at 1-3 months post-obliteration, then every 6-12 months
- First-line alternative to NSBB; combination of EVL + NSBB not clearly superior to monotherapy for primary prophylaxis

---

## Acute Variceal Hemorrhage

Acute variceal hemorrhage carries a 6-week mortality of approximately 20-30% and represents a medical emergency.

### Management Sequence

#### Step 1: Airway Protection

- Assess GCS and gag reflex immediately on presentation
- Intubation threshold: GCS <8, active hematemesis, inability to protect airway, severe encephalopathy
- Intubation preferred before EGD if patient has altered mental status to prevent aspiration
- RSI (rapid sequence intubation) preferred

#### Step 2: Volume Resuscitation and Blood Products

Restrictive transfusion strategy:

- Target Hgb 7-8 g/dL (liberal transfusion worsens portal hypertension and increases rebleeding)
- Fresh frozen plasma (FFP): give if INR >2.0 and active bleeding; not routinely needed
- Platelets: transfuse if platelet count <50,000/mm3 and active bleeding
- Two large-bore peripheral IVs or central venous access
- Avoid aggressive saline resuscitation (worsens ascites and portal hypertension)
- Type and crossmatch on admission

#### Step 3: Vasoactive Therapy — Octreotide

- Octreotide IV bolus: 50 mcg IV push
- Octreotide infusion: 50 mcg/hour continuous IV for 5 days
- Mechanism: somatostatin analog that causes splanchnic vasoconstriction, reducing portal blood flow and pressure
- Alternative: terlipressin 2mg IV q4h (superior evidence, FDA approved 2022), vasopressin + nitroglycerin (largely replaced)
- Start vasoactive therapy as soon as variceal hemorrhage is suspected — before endoscopy

#### Step 4: Antibiotic Prophylaxis

- Ceftriaxone 1g IV daily for 7 days (preferred in advanced cirrhosis or in settings with high quinolone resistance)
- Alternative: norfloxacin 400mg PO BID for 7 days (if ceftriaxone unavailable or oral route feasible)
- Rationale: cirrhotic patients have high risk of bacterial translocation and infection during GI bleed; antibiotics reduce rebleeding rate, infections, and mortality
- Start immediately — before endoscopy

#### Step 5: Proton Pump Inhibitor

- IV PPI (pantoprazole 40mg IV BID or continuous infusion) to minimize mucosal injury and optimize visualization
- PPI does not directly reduce portal pressure but improves mucosal healing post-ligation

#### Step 6: Urgent Endoscopy

- Upper EGD within 12 hours of presentation (6 hours in high-risk patients: active hematemesis, hemodynamic instability)
- Endoscopic variceal ligation (EVL) is the preferred endoscopic treatment
- Sclerotherapy (injection of sclerosant into varix): alternative if EVL technically difficult; higher complication rate
- Gastric varices: cyanoacrylate glue injection or coil embolization preferred over EVL

#### Step 7: Transjugular Intrahepatic Portosystemic Shunt (TIPS)

Indications for early TIPS (within 72 hours):
- Child-Pugh Class C (score 10-13) or Class B with active bleeding at EGD
- MELD <18 for better outcomes
- Failure to control bleeding with initial endoscopic and medical therapy
- Rebleeding after two attempts at endoscopic therapy

TIPS procedure:
- Radiologic creation of portosystemic shunt via jugular vein approach
- Stent placed between hepatic vein and portal vein
- Reduces portal pressure gradient typically to <12 mmHg
- Covered stents (ePTFE) preferred over bare metal

TIPS contraindications (absolute):
- Severe hepatic encephalopathy (HE Grade 3-4) uncontrolled prior to TIPS
- Bilirubin >5 mg/dL (relative — extremely high mortality post-TIPS)
- Portal vein thrombosis (relative; TIPS may still be technically feasible)
- Severe right heart failure or tricuspid regurgitation
- Hepatocellular carcinoma in the TIPS tract
- Severe pulmonary hypertension (mean PAP >45 mmHg)

Balloon-occluded retrograde transvenous obliteration (BRTO): preferred for gastric variceal bleeding when gastric varices drain into a gastrorenal shunt.

### Secondary Prophylaxis of Variceal Hemorrhage

After index variceal bleed, risk of rebleeding without prophylaxis is ~60-70% within 1 year.

- Combination therapy: NSBB (propranolol or nadolol or carvedilol) + EVL
- EVL: every 2-4 weeks until variceal obliteration, then surveillance EGD at 3-6 months
- NSBB: start after hemostasis is achieved and patient is hemodynamically stable
- If failed combination therapy: consider TIPS

---

## Ascites

Ascites is the most common complication of cirrhosis, occurring in approximately 50% of cirrhotic patients within 10 years of diagnosis.

### Pathophysiology

- Sinusoidal portal hypertension leads to increased hydrostatic pressure in the peritoneal capillaries
- Hepatic dysfunction reduces albumin synthesis, lowering oncotic pressure
- Splanchnic vasodilation (nitric oxide-mediated) causes effective arterial underfilling
- Activation of RAAS (aldosterone) and ADH leads to sodium and water retention
- Net result: sodium retention and water accumulation in the peritoneal cavity

### Serum-Ascites Albumin Gradient (SAAG)

**Formula:**
```
SAAG = Serum albumin (g/dL) - Ascites albumin (g/dL)
```

**Interpretation:**

| SAAG Value | Etiology | Examples |
|---|---|---|
| >=1.1 g/dL | Portal hypertension | Cirrhosis, cardiac cirrhosis, Budd-Chiari, hepatic vein thrombosis |
| <1.1 g/dL | Non-portal hypertension | Peritoneal carcinomatosis, tuberculosis, pancreatitis, nephrotic syndrome |

SAAG accuracy for portal hypertension: ~97% when interpreted with clinical context.

### Diagnostic Paracentesis

Indications:
- All patients with new-onset ascites
- All cirrhotic patients admitted to hospital
- Any patient with clinical deterioration, suspected SBP, or abdominal symptoms

Ascitic fluid analysis:

| Test | Clinical Use |
|---|---|
| Cell count with differential | PMN >250/mm3 = SBP; total WBC >500/mm3 suspicious |
| Culture in blood culture bottles | Increase sensitivity of SBP diagnosis to ~80% |
| Albumin | SAAG calculation |
| Total protein | <1.5g/dL = high SBP risk; >3g/dL suggests exudate |
| LDH | Elevated in malignancy or secondary peritonitis |
| Glucose | Low (<50mg/dL) in secondary peritonitis or malignancy |
| Amylase | Elevated in pancreatic ascites |
| Cytology | Suspected peritoneal carcinomatosis (low sensitivity ~20-40%) |
| Bilirubin | Biliary leak if ascites bilirubin > serum bilirubin |

Complications of paracentesis:
- Hematoma at puncture site (~1%)
- Infection (~0.1%)
- Bowel perforation (rare)
- Persistent fluid leak (rare)
- Coagulopathy is not an absolute contraindication; INR <2 and platelets >50,000 preferred but not required

### Spontaneous Bacterial Peritonitis (SBP)

#### Diagnosis
- PMN count >=250 cells/mm3 in ascitic fluid (even if culture negative = culture-negative neutrocytic ascites, treated the same)
- Most common organisms: E. coli, Klebsiella, Streptococcus pneumoniae (gram-negative enteric bacteria via bacterial translocation)
- Culture positive in only ~40-50% of cases

#### Treatment
- Cefotaxime 2g IV every 8 hours for 5 days (drug of choice)
- Alternatives: amoxicillin-clavulanate, ciprofloxacin (if uncomplicated and patient tolerates oral)
- Albumin infusion (critical for preventing HRS):
  - Day 1: 1.5g/kg IV albumin
  - Day 3: 1.0g/kg IV albumin
  - Albumin significantly reduces risk of renal impairment and mortality
- Repeat paracentesis at 48 hours: PMN should decrease >25% from baseline

#### SBP Prophylaxis

Indications:
1. Prior episode of SBP: norfloxacin 400mg PO daily (long-term)
2. Acute GI hemorrhage in cirrhotic patient: ceftriaxone 1g IV daily x7 days or norfloxacin 400mg BID x7 days
3. Low-protein ascites (<1.5g/dL) with any of: Cr >=1.2, BUN >=25, Na <=130, Child-Pugh >=9 + bilirubin >=3 — norfloxacin 400mg PO daily (primary prophylaxis)

Alternatives if norfloxacin unavailable: trimethoprim-sulfamethoxazole 1 double-strength tablet daily.

Note: long-term antibiotic prophylaxis is associated with increased risk of resistant organisms (MRSA, resistant gram-negatives); use clinical judgment.

### Medical Management of Ascites

#### Step 1: Sodium Restriction
- Restrict dietary sodium to 2g/day (88 mEq/day)
- Avoid NSAIDs (impair renal prostaglandins, worsen sodium retention)
- Avoid ACE inhibitors and ARBs in decompensated cirrhosis (hypotension, worsens renal function)

#### Step 2: Diuretic Therapy

| Drug | Starting Dose | Maximum Dose | Mechanism |
|---|---|---|---|
| Spironolactone | 100mg/day | 400mg/day | Aldosterone antagonist; first-line |
| Furosemide | 40mg/day | 160mg/day | Loop diuretic; add-on to spironolactone |

Dosing principles:
- Maintain a 100mg:40mg ratio of spironolactone to furosemide
- Standard initial regimen: spironolactone 100mg + furosemide 40mg simultaneously
- Escalate both drugs together (200:80 → 300:120 → 400:160 mg ratio)
- Adjust dose every 3-5 days to target weight loss:
  - If no edema: maximum 0.5 kg/day
  - If peripheral edema present: maximum 1.0 kg/day
  - Faster diuresis risks electrolyte disturbances and renal impairment
- Check BMP (electrolytes, creatinine) within 1 week of any dose change
- Amiloride: alternative to spironolactone for patients with painful gynecomastia

Diuretic complications:
- Hyperkalemia (spironolactone): reduce or hold if K+ >5.5 mEq/L
- Hyponatremia: restrict fluid to <1.5L/day if Na <125; consider holding diuretics if Na <120
- Azotemia: hold diuretics if creatinine rises >50% above baseline
- Encephalopathy: reduce or hold if HE worsens

#### Step 3: Large Volume Paracentesis (LVP)

- Indicated for tense or refractory ascites
- Remove up to 4-6 liters per session safely; larger volumes require albumin replacement
- Albumin replacement: 6-8g of 25% albumin per liter of ascitic fluid removed if >5 liters drained
- Without albumin replacement with LVP >5L: risk of post-paracentesis circulatory dysfunction (PPCD) — hemodynamic compromise from plasma volume contraction

#### Step 4: Refractory Ascites Management

Refractory ascites defined as:
- Ascites that cannot be mobilized with maximum diuretic doses (spironolactone 400mg + furosemide 160mg), OR
- Early recurrence after LVP despite maximum diuretic doses, OR
- Diuretic-induced complications (HE, hyponatremia, renal impairment, hypokalemia) that prevent adequate dosing

Management options:

**Midodrine:**
- Dose: 7.5-12.5mg three times daily (TID)
- Mechanism: alpha-1 adrenergic agonist; increases systemic vascular resistance and MAP
- Indicated for refractory ascites with low mean arterial pressure (MAP <82 mmHg)
- Goal: increase MAP by >=15 mmHg
- Useful in conjunction with LVP and octreotide for HRS-related ascites

**TIPS for Refractory Ascites:**
Criteria for TIPS consideration:
- Requires frequent LVP (>3 times per month) despite maximum diuretic therapy
- Child-Pugh Class B (score <=11) or Class A
- No severe hepatic encephalopathy
- MELD <=18 (above this threshold, TIPS complications may outweigh benefits)
- Absence of contraindications listed above

Post-TIPS ascites resolution: ~75-85% of patients have improved ascites control; majority can stop or reduce diuretics.

**Transjugular approach (TIPS technical details):**
- Access via right internal jugular vein
- Hepatic vein to portal vein connection with ePTFE-covered stent
- Target portal pressure gradient post-TIPS: <8-12 mmHg for ascites indication
- Requires 4-6 week post-procedure monitoring for stent dysfunction

---

## Hepatic Encephalopathy (HE)

Hepatic encephalopathy is a brain dysfunction caused by hepatic insufficiency and/or portosystemic shunting, manifesting as a wide spectrum of neurological and psychiatric abnormalities.

### West Haven Criteria for HE Grading

| Grade | Consciousness | Intellectual Function | Behavior | Neurological Signs |
|---|---|---|---|---|
| 0 (Covert) | Normal | Normal; no clinical abnormalities | Normal | No asterixis; minimal cognitive changes on testing |
| 1 (Covert) | Mildly impaired; sleep disturbances | Mildly impaired; shortened attention span | Mild anxiety, euphoria, or depression | Tremor, asterixis possible |
| 2 (Overt) | Moderate lethargy or apathy | Gross disorientation; poor arithmetic | Personality change; inappropriate behavior | Asterixis present; dysarthria; ataxia |
| 3 (Overt) | Marked confusion/somnolence; responsive to stimuli | Profound disorientation; unable to perform mental tasks | Bizarre behavior; intermittent aggression | Muscular rigidity; clonus; hyperreflexia |
| 4 (Overt) | Coma | Absent | Absent | Areflexia; decerebrate posturing |

### Classification of HE

- **Covert HE (CHE):** Grades 0-1; detectable only with neuropsychological testing (e.g., Psychometric HE Score, PHES); impairs driving ability and quality of life
- **Overt HE (OHE):** Grades 2-4; clinically apparent; requires immediate evaluation and treatment
- **Episodic HE:** Single acute episode with an identifiable precipitant
- **Recurrent HE:** >=2 episodes within 6 months
- **Persistent HE:** Continuous neurological dysfunction with behavioral changes

### Common Precipitants of HE

- Gastrointestinal hemorrhage (protein load in gut; most common precipitant)
- Infection (SBP, urinary tract infection, pneumonia)
- Constipation (increased ammonia production in colon)
- Electrolyte disturbances (hypokalemia, hyponatremia, metabolic alkalosis)
- Benzodiazepines and narcotics (CNS depressants)
- Dehydration and hypovolemia (reduced hepatic blood flow)
- TIPS procedure (increased portosystemic shunting)
- Dietary protein excess
- Renal failure (reduced ammonia clearance)
- Hepatocellular carcinoma (liver function deterioration)

### Treatment of HE

#### Lactulose

- Mechanism: non-absorbable disaccharide; colonic acidification reduces NH3 production; osmotic cathartic reduces gut transit time
- Dosing for overt HE (acute):
  - 30-45mL orally every 1 hour until bowel movement occurs
  - Then titrate to 2-3 soft stools per day
- Dosing for maintenance/prophylaxis:
  - 30-45mL orally 3-4 times daily (TID-QID)
  - Adjust dose to maintain 2-3 soft stools per day
- For patients unable to take orally: lactulose enemas (300mL in 700mL water, retain 30-60 min)
- Complications: diarrhea, electrolyte imbalances, aspiration risk if over-sedated; over-aggressive dosing causes hyponatremia and dehydration

#### Rifaximin

- Mechanism: non-absorbable antibiotic; reduces gut ammonia-producing bacteria
- Dose: 550mg PO twice daily (BID)
- Indication: secondary prophylaxis of overt HE (reduces recurrence by ~60%)
- Often used in combination with lactulose for better efficacy
- Generally well-tolerated; minimal systemic absorption; low resistance risk
- Also used adjunctively in acute HE not responding to lactulose alone

#### Additional Treatments

**Zinc supplementation:**
- Cirrhosis is associated with zinc deficiency (reduced hepatic synthesis of zinc-binding proteins)
- Zinc is a cofactor for urea cycle enzymes; deficiency worsens hyperammonemia
- Dose: zinc acetate 220mg BID or zinc sulfate 600mg daily
- Particularly useful in patients with chronic or persistent HE
- Low cost, minimal side effects

**Ornithine phenylacetate (OPA):**
- Emerging therapy; promotes alternative ammonia detoxification pathways
- Ornithine stimulates urea cycle; phenylacetate combines with glutamine to form excretable phenylacetylglutamine
- Clinical trials ongoing; not yet standard of care

**Branched-chain amino acids (BCAA):**
- Supplement with leucine, isoleucine, valine
- May improve HE symptoms and nutritional status in advanced cirrhosis
- Used when protein restriction is considered but enteral protein provision is essential

**Dietary considerations:**
- Do NOT restrict protein in HE (historical recommendation now abandoned)
- Target: 1.2-1.5g/kg/day protein to prevent sarcopenia
- Prefer vegetable-based proteins (lower ammoniogenic potential vs. animal protein)
- Small frequent meals (4-6 per day) with late-evening snack to avoid catabolism
- Avoid prolonged fasting (>3-4 hours in decompensated cirrhosis)

### Ammonia Level in HE Management

- Serum ammonia does NOT reliably correlate with degree of HE
- Ammonia level NOT recommended to guide treatment decisions or diagnose HE in isolation
- Clinical scenario + neurological examination are the primary diagnostic tools
- Hyperammonemia (>60 micromol/L) supports the diagnosis but is neither sensitive nor specific
- Exception: extremely high ammonia (>200 micromol/L) in acute liver failure may predict cerebral herniation

---

## Hepatorenal Syndrome (HRS)

HRS is a potentially reversible form of functional renal failure occurring in patients with advanced cirrhosis, ascites, and portal hypertension in the absence of an identifiable cause of renal disease.

### Pathophysiology

- Splanchnic vasodilation (NO-mediated) causes effective arterial underfilling
- Compensatory activation of vasoconstrictors: RAAS, sympathetic nervous system, ADH
- Renal vasoconstriction leads to dramatically reduced GFR
- Kidneys are intrinsically normal (transplanted kidneys from HRS patients function normally in recipients)

### Classification of HRS

#### HRS-AKI (formerly Type 1 HRS)
- Rapid and progressive impairment of renal function
- Doubling of serum creatinine to >2.5 mg/dL within 2 weeks
- Often precipitated by SBP, variceal hemorrhage, infection, LVP without albumin
- High short-term mortality (median survival 2-4 weeks without treatment)

#### HRS-CKD (formerly Type 2 HRS)
- Moderate, stable or slowly progressive renal impairment
- Creatinine typically 1.5-2.5 mg/dL
- Associated with refractory ascites
- Less dramatic but carries poor prognosis (median survival 4-6 months)

### Diagnostic Criteria for HRS

All of the following must be present:
1. Cirrhosis with ascites (or acute liver failure)
2. Serum creatinine >1.5 mg/dL (or acute rise >=0.3 mg/dL within 48 hours)
3. No improvement in creatinine after >=2 days of diuretic withdrawal AND albumin volume expansion (1g/kg/day up to 100g/day)
4. Absence of shock
5. No current or recent use of nephrotoxic drugs (NSAIDs, aminoglycosides, contrast agents)
6. Absence of parenchymal renal disease (no proteinuria >500mg/day, no microhematuria >50 RBC/HPF, normal renal ultrasound)

### Treatment of HRS

#### First-Line: Terlipressin + Albumin

- Terlipressin: FDA approved September 2022
- Dose: 0.85mg IV every 6 hours; titrate up to 1.7mg IV every 6 hours if creatinine does not decrease by >=30% from baseline on day 3
- Mechanism: vasopressin analog; causes splanchnic vasoconstriction, increases MAP, improves renal perfusion
- Combined with albumin: 20-40g IV daily
- Duration: until creatinine reversal (return to within 0.3 mg/dL of baseline), maximum 14 days
- Response rate: ~35-45% creatinine reversal
- Adverse effects: cardiac ischemia, limb ischemia, respiratory failure (particularly in patients with PaO2 <70)
- Contraindications: significant cardiac disease, respiratory failure, septic shock, ischemic colitis

#### Alternative: Midodrine + Octreotide + Albumin

Used when terlipressin is unavailable or contraindicated:
- Midodrine: 7.5-12.5mg PO TID (start 7.5mg, increase if MAP does not rise by 15 mmHg)
- Octreotide: 100-200mcg SQ TID (or 50mcg/hour IV continuous)
- Albumin: 20-40g IV daily
- Less effective than terlipressin but widely used in the United States prior to terlipressin approval
- Response rate: ~20-30%

#### Norepinephrine (Alternative)

- Continuous IV infusion: 0.5-3 mg/hour; titrate to increase MAP by >=10 mmHg
- Requires ICU monitoring
- Combined with albumin 1g/kg/day
- Evidence comparable to terlipressin in some studies; used in ICU settings

#### Renal Replacement Therapy (RRT)

- Bridging therapy to liver transplant only
- Not indicated for HRS alone (does not treat underlying cause)
- CRRT preferred in hemodynamically unstable patients

#### Liver Transplant

- Definitive therapy for HRS
- Renal function usually recovers within 4-8 weeks post-transplant
- Combined liver-kidney transplant (SLKT): considered if renal failure persists >4-8 weeks on dialysis
- SLKT indications: HRS on RRT >8 weeks; CKD with GFR <25 mL/min; DM with proteinuria

---

## Hepatopulmonary Syndrome (HPS)

### Definition and Pathophysiology

- Intrapulmonary vascular dilatations (IPVDs) leading to right-to-left shunting and hypoxemia in the setting of liver disease
- Intravascular pulmonary shunting: dilated pulmonary capillaries result in inadequate O2 transfer despite normal lung parenchyma
- Key diagnostic feature: hypoxemia that worsens in the upright position (orthodeoxia) and improves when supine

### Diagnostic Criteria

1. Liver disease (cirrhosis or portal hypertension)
2. PaO2 <70 mmHg on room air OR alveolar-arterial oxygen gradient >=15 mmHg
3. Evidence of intrapulmonary vascular dilatation

### Diagnostic Testing

- Contrast echocardiography (bubble study): IV agitated saline injected; detection of microbubbles in left heart after 3-5 cardiac cycles (>normal 2 cycles) indicates pulmonary shunting
- Technetium-99m macroaggregated albumin (MAA) lung perfusion scan: detects extrapulmonary uptake indicating shunt fraction
- Pulmonary angiography: rarely needed; identifies discrete arteriovenous malformations amenable to coil embolization

### Grading

| Grade | PaO2 (room air) |
|---|---|
| Mild | >=80 mmHg |
| Moderate | 60-79 mmHg |
| Severe | 50-59 mmHg |
| Very severe | <50 mmHg |

### Treatment

- Supplemental oxygen: mainstay of symptomatic management
- No effective medical therapy (inhaled nitric oxide, garlic, methylene blue — limited evidence)
- Liver transplantation: only cure; indicated even when MELD is low
- MELD exception points: HPS qualifies for exception points (priority listing) when PaO2 <60 mmHg on room air
- Post-transplant: HPS resolves in ~80% of patients within 6-12 months; severe HPS (PaO2 <50 mmHg) has higher post-transplant mortality

---

## NAFLD and NASH

### Spectrum of Disease

NAFLD (Non-Alcoholic Fatty Liver Disease) encompasses a spectrum from benign steatosis to progressive inflammatory/fibrotic disease:

1. **Simple steatosis (NAFL):** Fat accumulation >5% of hepatocytes; minimal inflammation; low progression risk
2. **NASH (Non-Alcoholic Steatohepatitis):** Steatosis + hepatocellular injury (ballooning) + inflammation ± fibrosis; risk of progression to cirrhosis
3. **NASH-related cirrhosis:** End-stage; may have minimal steatosis (burnt-out NASH)
4. **Hepatocellular carcinoma:** Can develop in cirrhotic or non-cirrhotic NASH

Prevalence: NAFLD ~25% of global population; NASH ~3-5%; cirrhosis develops in ~20% of NASH patients over 20 years.

### Risk Factors and Associated Conditions

- Obesity (BMI >25; especially central adiposity)
- Type 2 diabetes mellitus (strongest independent predictor of NASH and fibrosis)
- Insulin resistance / metabolic syndrome
- Hypertriglyceridemia
- Hypertension
- Polycystic ovary syndrome (PCOS)
- Hypothyroidism
- Obstructive sleep apnea
- Certain medications: corticosteroids, tamoxifen, methotrexate, amiodarone, antiretrovirals

### Diagnosis

Diagnosis requires:
1. Evidence of hepatic steatosis on imaging or histology
2. Exclusion of significant alcohol use (>21 drinks/week men, >14 drinks/week women)
3. Exclusion of other causes: viral hepatitis, autoimmune hepatitis, drug-induced steatosis

Imaging:
- Ultrasound: first-line screening; sensitive for steatosis >33%; cannot grade fibrosis
- CT: similar sensitivity to ultrasound; radiation exposure
- MRI-PDFF (proton density fat fraction): most accurate for steatosis quantification; non-invasive
- MR elastography: gold standard non-invasive fibrosis assessment

Liver biopsy indications:
- Indeterminate FIB-4 (1.3-2.67) + clinical suspicion for significant fibrosis
- Exclude competing diagnoses
- Before initiating hepatotoxic therapies (e.g., methotrexate)
- Clinical trials enrollment

### FIB-4 Index in NAFLD

```
FIB-4 = (Age [years] x AST [U/L]) / (Platelet count [10^9/L] x sqrt(ALT [U/L]))
```

| FIB-4 | Interpretation | Action |
|---|---|---|
| <1.30 (<35 years old: <2.0) | Low risk for advanced fibrosis | Routine care; reassess in 1-2 years |
| 1.30-2.67 | Indeterminate | Elastography or gastroenterology referral |
| >2.67 | High risk for advanced fibrosis (F3-F4) | Hepatology referral; consider biopsy |

### NAFLD Activity Score (NAS)

Histological scoring system for NASH assessment on liver biopsy:

| Component | Score | Description |
|---|---|---|
| Steatosis | 0-3 | 0: <5%; 1: 5-33%; 2: 33-66%; 3: >66% |
| Lobular inflammation | 0-3 | 0: none; 1: <2 foci/200x; 2: 2-4 foci; 3: >4 foci |
| Hepatocellular ballooning | 0-2 | 0: none; 1: few balloon cells; 2: many balloon cells |
| **Total NAS** | 0-8 | NAS <3: not NASH; NAS >=5: NASH likely |

### Management

#### Weight Loss (Most Effective Intervention)

- 7% total body weight loss: improves steatosis and inflammation
- 10% total body weight loss: significant fibrosis improvement; may achieve NASH resolution
- >10% sustained weight loss: documented fibrosis regression in controlled trials
- Methods: dietary modification (Mediterranean diet preferred), caloric restriction, physical activity

#### Exercise

- Aerobic exercise >=150 min/week moderate intensity reduces hepatic fat
- Resistance training also beneficial
- Exercise reduces liver fat independent of weight loss

#### Control of Metabolic Comorbidities

- Glycemic control: reduces hepatic gluconeogenesis and lipogenesis
- Statin therapy: safe in NAFLD (statins do NOT cause worsening liver disease); should not be withheld for elevated transaminases in NAFLD
- Treatment of hypertriglyceridemia: omega-3 fatty acids, fibrates
- RAAS blockade: benefit in reducing fibrosis progression (observational data)

#### Pharmacotherapy for NASH

| Drug | Evidence Level | Indication | Dose |
|---|---|---|---|
| Pioglitazone | Strong (RCTs) | Biopsy-proven NASH + T2DM or pre-DM | 30-45mg/day |
| Vitamin E | Moderate (RCTs) | Biopsy-proven NASH without DM or cirrhosis | 800 IU/day |
| Semaglutide | Emerging (Phase 3 trials) | NASH + obesity/T2DM | 2.4mg SQ weekly |
| Resmetirom | FDA approved March 2024 | NASH with fibrosis F2-F3, compensated cirrhosis | 80-100mg/day PO |
| Obeticholic acid | Not approved for NASH (ongoing trials) | — | — |

**Resmetirom (Rezdiffra):** First FDA-approved medication specifically for NASH. Thyroid hormone receptor beta-selective agonist. Reduces liver fat and improves fibrosis. Indicated for adults with non-cirrhotic NASH with moderate-to-advanced fibrosis (F2-F3). Phase 3 MAESTRO-NASH trial demonstrated statistically significant fibrosis improvement.

**Pioglitazone notes:** Weight gain and fluid retention common side effects; use with caution in heart failure; associated with bladder cancer risk with prolonged use (monitor); benefits persist only during use.

**Vitamin E notes:** Avoid in men with prostate cancer history; concern for hemorrhagic stroke at high doses with prolonged use (>400 IU/day data mixed); contraindicated in DM (inferior to pioglitazone) and cirrhosis.

#### Bariatric Surgery

- Highly effective for NASH and fibrosis improvement
- RYGB and sleeve gastrectomy: most evidence
- Appropriate for patients with obesity and NASH, especially BMI >40 or BMI >35 with comorbidities
- Not performed in decompensated cirrhosis (high perioperative mortality)

---

## Alcoholic Liver Disease (ALD)

ALD encompasses a spectrum from alcoholic fatty liver (steatosis) to alcoholic hepatitis (AH) to alcoholic cirrhosis.

### Alcoholic Hepatitis (AH)

Clinical presentation:
- Abrupt onset jaundice (bilirubin often >3 mg/dL)
- Fever (often low-grade; may be >38.5°C)
- Tender hepatomegaly
- Leukocytosis (neutrophilia without left shift in absence of infection)
- Recent heavy alcohol use (often within weeks of presentation)
- AST:ALT ratio typically >2:1 (ALD hallmark); absolute AST usually <300 U/L

Diagnosis requires exclusion of other causes of liver decompensation in a patient with confirmed heavy alcohol use.

### Maddrey Discriminant Function (MDF)

Identifies severe alcoholic hepatitis requiring treatment:

**Formula:**
```
MDF = 4.6 x (Patient PT - Control PT [seconds]) + Total bilirubin (mg/dL)
```

| MDF Score | Severity | 30-Day Mortality | Action |
|---|---|---|---|
| <32 | Mild-moderate | <10% | Abstinence, nutrition; no steroids |
| >=32 | Severe | 30-50% | Consider corticosteroids |

### MELD Score in Alcoholic Hepatitis

MELD >20 also identifies severe AH and may be used alongside MDF to guide steroid therapy (equivalent predictive value).

### Corticosteroid Therapy

Indication: Severe AH (MDF >=32 or MELD >20)

- Prednisolone 40mg orally daily for 28 days (preferred over prednisone)
- **Note:** Prednisone requires hepatic conversion to active prednisolone — impaired in severe hepatic failure, making prednisolone the preferred agent
- Do NOT use methylprednisolone IV unless patient cannot swallow (equivalent efficacy to oral prednisolone if oral route available)

Contraindications to steroids in AH:
- Active infection (bacterial, fungal, viral — must screen and treat before starting)
- GI hemorrhage
- Renal failure (serum creatinine >2.5 mg/dL — relative)
- HBV reactivation risk (screen for HBsAg; if positive, add HBV treatment)
- Uncontrolled DM

### Lille Score

Predicts steroid response at day 7 to guide continuation or cessation:

**Formula:**
```
Lille Score = 3.19 - (0.101 x Age)
             - (0.147 x Albumin at day 0)
             - (0.0165 x Bilirubin change [day0 - day7])
             - (0.206 x Renal insufficiency [1 = yes, 0 = no])
             - (0.0065 x Bilirubin at day 0)
             - (0.0096 x PT)
```

| Lille Score | Interpretation | Action |
|---|---|---|
| <0.45 | Steroid responder | Continue prednisolone to 28 days then taper |
| >=0.45 | Non-responder (high mortality) | Stop steroids (no benefit; infection risk); palliative care discussion |

### Pentoxifylline

- No longer recommended for alcoholic hepatitis
- STOPAH trial (2015) definitively showed no survival benefit over placebo
- Historical rationale was anti-TNF activity and prevention of HRS

### Nutrition in Alcoholic Hepatitis

- Malnutrition is nearly universal in AH and independently predicts mortality
- Target: 35-40 kcal/kg/day total calories
- Target: 1.2-1.5g/kg/day protein (do not restrict protein in AH)
- Route: enteral is preferred; nasogastric tube if patient cannot meet caloric goals orally
- Enteral nutrition is as effective as steroids for short-term survival in some studies
- Parenteral nutrition only if enteral not feasible

### Thiamine Deficiency and Wernicke Encephalopathy

Wernicke encephalopathy (WE) is an acute neurological emergency caused by thiamine (B1) deficiency, common in alcoholic patients.

**Classic triad (present together in only ~10% of cases):**
1. Confusion / altered mental status
2. Ophthalmoplegia / nystagmus
3. Ataxia

**Treatment Protocol:**
- Thiamine 500mg IV three times daily (TID) for 3 days — high-dose IV essential
- Then thiamine 250mg IV or IM once daily for 5 days
- Then oral thiamine maintenance
- **Critical:** Thiamine MUST be administered BEFORE any glucose (IV dextrose can precipitate or worsen WE by consuming residual thiamine for glucose metabolism)
- Oral thiamine absorption is unreliable in alcoholic patients; IV route required for treatment

### Abstinence

- Most important intervention at all stages of ALD
- Complete abstinence can lead to significant histological improvement, even in cirrhosis
- Alcohol use disorder management: naltrexone (avoid in hepatic failure), acamprosate, baclofen (studied in cirrhosis; renally cleared — safer than naltrexone)
- Addiction psychiatry and counseling: essential component of management
- Baclofen: 5-10mg TID; only agent with RCT evidence in cirrhotic patients with alcohol use disorder

---

## Viral Hepatitis

### Hepatitis A (HAV)

- Transmission: fecal-oral route; contaminated water, shellfish, food
- Incubation: 2-6 weeks
- Never becomes chronic; self-limited in virtually all cases
- Fulminant hepatic failure: rare (~0.1-0.3%); higher risk in patients with underlying liver disease

**Serology:**
- HAV IgM: acute infection (positive 1-2 weeks after onset, persists ~6 months)
- HAV IgG: past infection or successful vaccination (lifelong immunity)
- Elevated AST/ALT, elevated bilirubin during acute phase

**Treatment:** Supportive care only; no specific antiviral therapy.

**Vaccination:**
- Two-dose series: dose 1 at time 0; dose 2 at 6-18 months
- Brands: Havrix (GlaxoSmithKline), Vaqta (Merck)
- Combined HAV/HBV vaccine: Twinrix — 3-dose series
- Indications: travelers to endemic areas, chronic liver disease, MSM, persons experiencing homelessness, IV drug users, clotting factor disorder

---

### Hepatitis B (HBV)

#### HBV Serology Interpretation

| Marker | Acute HBV | Chronic HBV (Immune Active) | Inactive Carrier | Resolved HBV | Vaccine Immunity |
|---|---|---|---|---|---|
| HBsAg | + | + | + | - | - |
| Anti-HBs (HBsAb) | - | - | - | + | + |
| Anti-HBc IgM | + (high titer) | - (low titer possible) | - | - | - |
| Anti-HBc IgG | +/- | + | + | + | - |
| HBeAg | + | + | - | - | - |
| Anti-HBe (HBeAb) | - | - | + | +/- | - |
| HBV DNA | Very high | High | Low/Undetectable | Undetectable | Not tested |

**Key distinctions:**
- Acute HBV: HBsAg + AND Anti-HBc IgM + (high titer)
- Chronic HBV: HBsAg positive >6 months
- Occult HBV: HBsAg negative, Anti-HBc positive, HBV DNA detectable; clinical significance in immunosuppressed patients
- Window period: HBsAg cleared, Anti-HBs not yet detectable; only Anti-HBc IgM indicates acute infection

#### HBV Treatment Indications

| Indication | Threshold | Treatment |
|---|---|---|
| Immune-active phase | HBV DNA >2000 IU/mL + elevated ALT (>ULN) | Antiviral therapy |
| Compensated cirrhosis | Any detectable HBV DNA | Antiviral therapy |
| Decompensated cirrhosis | Regardless of DNA level | Antiviral therapy (urgent) |
| Immunosuppression/chemotherapy | Prophylactic even if low-level | Antiviral therapy pre-emptively |
| HCC risk | DNA >2000 IU/mL regardless of ALT | Antiviral therapy |

HBV immune-tolerant phase (young patients, very high DNA, normal ALT, minimal fibrosis): treatment controversial; most guidelines recommend monitoring without therapy.

#### HBV Antiviral Agents

| Drug | Dose | Resistance | Notes |
|---|---|---|---|
| Tenofovir Disoproxil Fumarate (TDF) | 300mg PO daily | Very low | First-line; caution in osteoporosis and renal disease |
| Tenofovir Alafenamide (TAF) | 25mg PO daily | Very low | Preferred over TDF: better renal/bone safety profile |
| Entecavir (ETV) | 0.5mg PO daily (treatment-naive) / 1mg (lamivudine-resistant) | Very low | First-line; excellent safety profile |
| Pegylated Interferon alfa-2a | 180mcg SQ weekly x48 weeks | N/A (not applicable) | Finite therapy; HBeAg seroconversion; not for decompensated cirrhosis |
| Lamivudine | 100mg PO daily | High (>70% at 5 years) | No longer recommended as monotherapy |

Treatment duration: indefinite in most cases; HBeAg seroconversion + 1 year consolidation required to consider stopping in non-cirrhotic HBeAg-positive patients. HBsAg clearance = "functional cure" (rare).

#### HCC Surveillance in HBV

- Ultrasound + AFP every 6 months regardless of fibrosis stage in:
  - HBV-related cirrhosis
  - Asian male HBV patients >40 years
  - Asian female HBV patients >50 years
  - African HBV patients >20 years
  - HBV patients with family history of HCC
  - High-level HBV replication (HBV DNA >10,000 IU/mL) with elevated ALT

---

### Hepatitis C (HCV)

#### HCV Testing Algorithm

1. Anti-HCV antibody (ELISA) — initial screening test
2. If reactive: HCV RNA confirmatory test (NAAT)
3. HCV RNA positive: active infection — proceed to genotyping
4. HCV RNA negative + anti-HCV positive: resolved infection or false positive (repeat NAAT in 12 weeks if recent exposure suspected)

#### HCV Genotypes

- Genotype 1: most common in North America (~75% of US HCV); historically most difficult to treat (pre-DAA era)
- Genotype 2: ~15% of US cases; historically easiest to treat
- Genotype 3: ~5-7%; associated with accelerated fibrosis, steatosis, higher HCC risk
- Genotypes 4-6: less common in US; prevalent in Africa, Middle East, Southeast Asia

#### HCV Direct-Acting Antivirals (DAA)

**Pan-genotypic regimens (preferred):**

| Regimen | Genotypes | Duration | SVR Rate |
|---|---|---|---|
| Sofosbuvir/Velpatasvir (Epclusa) | 1-6 (pan-genotypic) | 12 weeks | >95% |
| Glecaprevir/Pibrentasvir (Mavyret) | 1-6 (pan-genotypic) | 8 weeks (treatment-naive, no cirrhosis) / 12 weeks (compensated cirrhosis) | >97% |

**Genotype-specific regimens:**

| Regimen | Genotypes | Duration | Notes |
|---|---|---|---|
| Ledipasvir/Sofosbuvir (Harvoni) | 1a, 1b, 4, 5, 6 | 12 weeks | 8 weeks if treatment-naive, low viral load, no cirrhosis |
| Elbasvir/Grazoprevir (Zepatier) | 1b, 4 | 12 weeks | Genotype 1a requires resistance testing |
| Sofosbuvir + Ribavirin | 2 | 12 weeks | Largely replaced by pan-genotypic options |

**Special populations:**
- Decompensated cirrhosis (Child B/C): sofosbuvir/velpatasvir ± ribavirin 12-24 weeks; NS3/4A protease inhibitors (glecaprevir, grazoprevir) contraindicated in decompensated cirrhosis (Child B/C)
- Post-transplant: same DAA regimens; monitor drug interactions with immunosuppressants (tacrolimus levels affected by protease inhibitors)
- On hemodialysis: glecaprevir/pibrentasvir preferred (renally eliminated ribavirin and sofosbuvir avoided)

#### SVR (Sustained Virologic Response)

- SVR12: undetectable HCV RNA 12 weeks after completing therapy = cure
- SVR12 rates with current DAAs: >97% across genotypes
- Post-SVR: check HCV RNA at 12 weeks post-treatment completion
- Post-SVR liver benefits: regression of fibrosis, reduction in HCC risk (not eliminated in cirrhosis), reduction in liver-related mortality by ~80%
- Post-SVR surveillance: if cirrhosis present, HCC surveillance every 6 months with ultrasound ± AFP is lifelong (SVR does not eliminate HCC risk)
- Reinfection: possible after SVR if high-risk behaviors continue; re-test HCV RNA annually in high-risk populations (PWID)

---

## Drug-Induced Liver Injury (DILI)

### Definition

DILI is liver injury caused by a medication, herbal product, or dietary supplement, after exclusion of other causes.

- Intrinsic (predictable, dose-dependent): acetaminophen
- Idiosyncratic (unpredictable, dose-independent, immune-mediated or metabolic): most drug reactions

### Common DILI Culprits

| Drug | Pattern | Mechanism | Notes |
|---|---|---|---|
| Acetaminophen | Hepatocellular (severe) | Intrinsic; dose-dependent; NAPQI metabolite | Leading cause of ALF in US; threshold dose 3g/day in alcoholics |
| Amoxicillin-clavulanate | Cholestatic/mixed | Idiosyncratic; clavulanate responsible | Most common antibiotic DILI; delayed onset up to 6 weeks post-course |
| Isoniazid (INH) | Hepatocellular | Idiosyncratic; toxic metabolites | Hold if ALT >3x ULN with symptoms or >5x ULN; fatal if continued |
| Nitrofurantoin | Chronic hepatitis, cirrhosis | Autoimmune-like mechanism | Long-term use (>6 months); presents as AIH |
| Statins | Hepatocellular (mild) | Idiosyncratic; usually asymptomatic | True DILI rare; transaminase elevation in ~3%; continue statin if <3x ULN |
| NSAIDs | Hepatocellular | Idiosyncratic | Diclofenac and sulindac most hepatotoxic NSAIDs |
| Halothane | Hepatocellular (severe) | Immune-mediated (CYP2E1 hapten) | Multiple exposures; fulminant hepatic failure |
| Methotrexate | Hepatic fibrosis/cirrhosis | Cumulative dose toxicity | Cumulative dose >1.5-2g; monitor with FIB-4 or elastography |
| Azathioprine | Cholestasis, veno-occlusive disease | Idiosyncratic; TPMT deficiency risk | Check TPMT activity before starting |
| Propylthiouracil (PTU) | Hepatocellular (fulminant) | Idiosyncratic | Pediatric patients at higher risk |
| Herbal supplements | Variable | — | Black cohosh, kava, green tea extract, pennyroyal |

### Injury Pattern Classification: R Ratio

The R ratio distinguishes hepatocellular from cholestatic injury pattern:

**Formula:**
```
R = (ALT / ULN for ALT) / (ALP / ULN for ALP)
```

| R Ratio | Pattern | Common Causes |
|---|---|---|
| >5 | Hepatocellular | Acetaminophen, isoniazid, statins, NSAIDs |
| 2-5 | Mixed | Phenytoin, sulfonamides |
| <2 | Cholestatic | Amoxicillin-clavulanate, estrogens, anabolic steroids |

### RUCAM Scale (Causality Assessment)

The Roussel Uclaf Causality Assessment Method scores the likelihood that a drug caused liver injury:

Domains assessed:
1. Time from drug start to reaction (and time to improvement after stopping)
2. Course of reaction
3. Risk factors (age, alcohol, pregnancy)
4. Concomitant drugs
5. Non-drug causes excluded
6. Previous published reports
7. Rechallenge (if done)

Score interpretation: >8 = highly probable; 6-8 = probable; 3-5 = possible; 1-2 = unlikely; <=0 = excluded.

### Acetaminophen Overdose Management

#### Rumack-Matthew Nomogram

- Plots serum acetaminophen level vs. time since ingestion
- Treatment line: level >=150 mcg/mL at 4 hours post-ingestion (or equivalent on log-linear scale)
- If level above treatment line: N-acetylcysteine (NAC) indicated

#### NAC Protocol

**IV N-acetylcysteine (Acetadote) — 21-hour protocol:**

| Phase | Dose | Duration | Volume |
|---|---|---|---|
| Loading dose | 150 mg/kg | 1 hour | 200 mL D5W |
| Second dose | 50 mg/kg | 4 hours | 500 mL D5W |
| Third dose | 100 mg/kg | 16 hours | 1000 mL D5W |
| Total dose | 300 mg/kg over 21 hours | | |

**Oral NAC protocol (72-hour):**
- Loading dose: 140 mg/kg orally
- Maintenance: 70 mg/kg orally every 4 hours for 17 additional doses
- Total: 1330 mg/kg over 72 hours

IV preferred in patients with ALF, vomiting, or inability to tolerate oral route. Continue IV NAC beyond 21 hours if ALT still rising, INR >2, or encephalopathy.

---

## Acute Liver Failure (ALF)

### Definition

Acute liver failure (ALF) is defined as:
- Evidence of coagulation abnormality (INR >=1.5)
- Any degree of encephalopathy
- Occurring within 26 weeks of symptom onset
- In the absence of pre-existing liver disease (with exceptions: Wilson's disease, autoimmune hepatitis, Budd-Chiari)

Subcategories by time from jaundice onset to encephalopathy:
- Hyperacute: <7 days (acetaminophen, ischemia; better prognosis)
- Acute: 7-28 days (viral hepatitis)
- Subacute: 4-26 weeks (drug reactions, seronegative hepatitis; worst prognosis)

### Etiology of ALF

| Cause | Frequency in US | Notes |
|---|---|---|
| Acetaminophen | ~50% | Most common in US, UK, Australia |
| Idiosyncratic drug reactions | ~12% | Isoniazid, nitrofurantoin, halothane |
| Seronegative/cryptogenic | ~15% | Unknown cause; often autoimmune |
| Viral hepatitis | ~12% | HBV reactivation, HAV, HEV; HCV rare |
| Autoimmune hepatitis | ~5% | May present without prior diagnosis |
| Ischemic hepatitis | ~4% | Cardiogenic shock, hypotension |
| Acute Wilson's disease | ~2% | Young patients; hemolytic anemia |
| Budd-Chiari syndrome | ~1% | Hepatic vein thrombosis |
| Acute fatty liver of pregnancy | Rare | Third trimester; fetal/maternal risk |
| Malignant infiltration | Rare | Lymphoma, breast cancer, melanoma |

### ICU Management

- ICU admission mandatory for all ALF patients with Grade 2+ HE
- Transfer to liver transplant center early

Key management principles:
1. **Prevent hypoglycemia:** Continuous 10-20% dextrose infusion; glucose monitoring every 1-2 hours; target glucose 140-180 mg/dL
2. **Lactulose and rifaximin:** Standard HE management; prevent worsening encephalopathy
3. **Coagulopathy:** Do NOT correct INR with FFP unless active bleeding or invasive procedure — INR is prognostic marker; coagulation in ALF is actually "rebalanced" (reduced both pro- and anticoagulant factors)
4. **Renal support:** CRRT for renal failure or fluid overload
5. **ICP monitoring:** Considered in Grade 3-4 HE with suspected cerebral edema; invasive ICP monitor placement
6. **Cerebral edema treatment:** Head elevation 30 degrees, target Na 145-150 mEq/L (hypernatremia reduces cerebral edema), mannitol 0.5-1g/kg IV bolus for intracranial hypertension
7. **Infection surveillance:** Pan-culture regularly; broad-spectrum antibiotics for Grade 3-4 HE (high risk of occult infection)
8. **Vasopressors:** Norepinephrine for hemodynamic instability

### N-Acetylcysteine in ALF

- NAC: indicated for all ALF regardless of cause (not just acetaminophen)
- Evidence: NAC improves transplant-free survival in early-stage non-acetaminophen ALF (Grade 1-2 HE)
- IV NAC preferred in ALF; continue until transplant, recovery, or death
- Mechanism in non-acetaminophen ALF: antioxidant, improves microcirculatory blood flow, anti-inflammatory

### King's College Criteria for Transplant Listing

#### Acetaminophen-related ALF (any one criterion):
- pH <7.30 (irrespective of encephalopathy grade)
- OR all three of:
  - INR >6.5
  - Creatinine >3.4 mg/dL
  - Grade 3 or 4 HE

#### Non-acetaminophen ALF:
**Primary criterion:**
- INR >6.5 (PT >100 seconds)

**OR any three of the following five:**
- Age <10 or >40 years
- Etiology: non-A, non-B hepatitis; drug toxicity; Wilson's disease; autoimmune
- Duration of jaundice >7 days before encephalopathy
- INR >3.5 (PT >50 seconds)
- Bilirubin >17.5 mg/dL

Sensitivity ~70-80%; specificity ~90%. Other criteria used: UKELD, MELD >30.

---

## Liver Transplantation

### Indications for Liver Transplantation

- MELD >=15 (survival benefit exceeds operative risk threshold)
- Hepatocellular carcinoma within Milan criteria (T2: single lesion 2-5cm, or 2-3 lesions all <=3cm, no vascular invasion, no extrahepatic spread)
- Hepatopulmonary syndrome (PaO2 <60 mmHg)
- Acute liver failure (King's College or equivalent criteria)
- Recurrent cholangitis (PSC)
- Refractory ascites/encephalopathy
- Metabolic liver diseases: Wilson's disease, hereditary hemochromatosis, alpha-1 antitrypsin deficiency
- Polycystic liver disease

### MELD Exception Points

Conditions where standard MELD score underestimates waitlist mortality:

| Condition | Exception Criteria | MELD Equivalent |
|---|---|---|
| Hepatocellular carcinoma (T2) | Single 2-5cm lesion or 2-3 lesions <=3cm; AFP escalation criteria | MELD 28-34+ depending on wait time |
| Hepatopulmonary syndrome | PaO2 <60 mmHg room air | Priority listing |
| Primary sclerosing cholangitis | Recurrent cholangitis; biliary dysplasia | Case-by-case |
| Recurrent HE | Refractory to medical management | Case-by-case |
| Familial amyloid polyneuropathy | Dominant Val30Met mutation | Standard exception |

AFP escalation policy (HCC): patients with AFP >1000 ng/mL and rising are removed from exception; requires AFP <500 ng/mL for exception eligibility.

### Contraindications to Liver Transplant

**Absolute contraindications:**
- Extrahepatic malignancy not in remission (except: certain skin cancers, early-stage cancers with curative resection)
- Active, uncontrolled alcohol or substance use disorder
- Severe cardiac or pulmonary disease (LVEF <40%, mean PAP >50 mmHg)
- Active systemic infection/sepsis
- Cholangiocarcinoma (perihilar/intrahepatic) — most centers; exception: some centers perform transplant for perihilar CCA with neoadjuvant protocol
- Anatomic contraindications to surgery

**Relative contraindications:**
- HIV (not a contraindication if controlled on ART with undetectable viral load)
- Obesity (BMI >40 — some centers; risk of perioperative complications)
- Age >70 years (individual assessment required)
- Medical non-compliance (active psychosocial concerns)
- Minimal social support

### Post-Transplant Management

#### Immunosuppression

Standard protocol:
- Calcineurin inhibitor (CNI): tacrolimus (target trough 8-12 ng/mL in first year, then 5-8 ng/mL)
- Antimetabolite: mycophenolate mofetil (MMF) 1g BID (or azathioprine)
- Corticosteroids: methylprednisolone taper over 3-6 months; many centers discontinue by 6-12 months
- mTOR inhibitors (sirolimus, everolimus): used when renal-sparing CNI minimization is needed; delay initiation post-transplant (wound healing concerns)

Common immunosuppression side effects:
- Tacrolimus: nephrotoxicity, neurotoxicity (tremor), hypertension, DM, drug interactions (CYP3A4 inhibitors/inducers)
- MMF: GI side effects (nausea, diarrhea), cytopenias
- Steroids: DM, bone loss, hypertension, cataracts

#### Prophylaxis

- CMV prophylaxis: valganciclovir 900mg daily for 3-6 months (D+/R- recipients: 6 months)
- PCP prophylaxis: trimethoprim-sulfamethoxazole 1 DS tablet daily (or dapsone if sulfa-allergic) for 6-12 months
- Aspirin: 81mg daily (some centers) for cardiovascular disease prevention
- Calcium and vitamin D supplementation

#### HCC Recurrence Monitoring Post-Transplant

- CT chest/abdomen/pelvis or MRI abdomen every 3-6 months for first 2 years, then annually
- AFP if elevated pre-transplant
- Recurrence rate ~10-15% for Milan criteria patients
- Treatment for recurrence: sorafenib, resection if feasible, local ablation

---

## Autoimmune Hepatitis (AIH)

### Presentation and Diagnosis

- Predominantly affects women (70-80%); all ages; bimodal peak 10-30 years and 40-60 years
- Presentation: ranges from asymptomatic aminotransferase elevation to acute liver failure
- Often associated with other autoimmune conditions: thyroid disease, IBD, celiac disease, rheumatoid arthritis

### Diagnostic Features

| Marker | AIH Type 1 | AIH Type 2 |
|---|---|---|
| ANA | Positive (>1:40 titer) | Negative or low titer |
| Anti-smooth muscle antibody (ASMA/anti-SMA) | Positive | Negative |
| Anti-LKM1 (liver-kidney microsomal) | Negative | Positive |
| Anti-LC1 (liver cytosol) | Negative | Positive (young patients) |
| IgG | Elevated (typically >1.1x ULN) | Elevated |
| Liver biopsy | Interface hepatitis, rosette formation, plasma cell infiltration | Same pattern |

Simplified AIH Scoring System (Hennes criteria): includes serological markers, IgG level, histology, and viral hepatitis exclusion.

### Treatment

- Induction: prednisone 30-60mg/day OR budesonide 3mg TID (non-cirrhotic AIH only)
- Maintenance: azathioprine 1-2mg/kg/day + prednisone taper to lowest effective dose
- Azathioprine requires 3-6 months to exert full effect; not used for acute induction
- Check TPMT activity before starting azathioprine (deficiency leads to severe bone marrow toxicity)
- Goal: normalization of ALT, AST, IgG
- Treatment withdrawal: after >=2 years of remission; biopsy should show no inflammation before withdrawal; relapse rate ~50% within 1 year of withdrawal
- Budesonide advantages: first-pass hepatic metabolism reduces systemic steroid side effects; not effective in cirrhosis (portosystemic shunting bypasses liver)

---

## Primary Biliary Cholangitis (PBC)

### Overview

- Chronic autoimmune cholestatic liver disease
- Destruction of small intrahepatic bile ducts by T-cell mediated injury
- Almost exclusively women (90-95%); middle age
- Classic presentation: fatigue, pruritus, elevated ALP and GGT, minimal or absent transaminase elevation

### Diagnosis

- Anti-mitochondrial antibody (AMA): positive in >95% of PBC; highly specific
- AMA subtype M2 (anti-PDC-E2): most specific
- ANA with speckled or nuclear dot pattern: AMA-negative PBC
- Elevated IgM (characteristic)
- Liver biopsy: granulomatous bile duct destruction (florid duct lesion), portal inflammation, fibrosis
- Biopsy not required if AMA positive + cholestatic labs + consistent symptoms

### Treatment

| Drug | Dose | Indication | Response |
|---|---|---|---|
| Ursodeoxycholic acid (UDCA) | 13-15mg/kg/day PO | First-line for all PBC | Normalizes or improves ALP; slows fibrosis progression |
| Obeticholic acid (OCA) | 5mg/day, titrate to 10mg | Inadequate UDCA response (ALP >1.67x ULN or elevated bilirubin) | Reduces ALP; approved 2016 |
| Seladelpar | 10mg/day | Inadequate UDCA response | FDA approved 2024 |
| Bezafibrate / Fenofibrate | Standard doses | Off-label; inadequate response; reduces ALP | Emerging evidence |

UDCA response criteria (Paris II criteria at 1 year): ALP <=1.5x ULN AND AST <=1.5x ULN AND bilirubin <=1mg/dL.

Management of symptoms:
- Pruritus: cholestyramine 4-16g/day (first-line); rifampicin 150-300mg BID; naltrexone; sertraline; bezafibrate
- Fatigue: no effective treatment; exclude hypothyroidism, anemia, depression
- Fat-soluble vitamin supplementation (A, D, E, K) if steatorrhea or fat malabsorption

---

## Primary Sclerosing Cholangitis (PSC)

### Overview

- Progressive fibroinflammatory disease causing multifocal biliary strictures
- Medium and large bile ducts (intrahepatic and extrahepatic)
- 70% male; peak onset 30-50 years
- Strong association with IBD: 70-80% of PSC patients have IBD (usually UC)
- No proven disease-modifying medical therapy

### Diagnosis

- ERCP or MRCP: classic "beading" pattern of intrahepatic and/or extrahepatic bile ducts (alternating strictures and dilations)
- ALP markedly elevated; GGT elevated; bilirubin rises as disease progresses
- pANCA positive in 60-80% (non-specific)
- Liver biopsy: "onion-skin" periductal fibrosis (characteristic but not always present); not required if imaging diagnostic

### Complications

- Dominant stricture: defined as CBD <=1.5mm or hepatic duct <=1mm; requires ERCP with balloon dilation and/or stenting
- Cholangiocarcinoma (CCA): lifetime risk 10-20%; annual MRCP + CA 19-9 surveillance
- Colorectal cancer: colonoscopy at PSC diagnosis; annual surveillance if IBD present
- Cholangitis (recurrent bacterial): fever, RUQ pain, jaundice (Charcot's triad)

### Treatment

- UDCA: controversial; high doses (28-30mg/kg/day) associated with worse outcomes in one trial; not routinely recommended
- ERCP: symptomatic dominant stricture management
- Liver transplantation: only proven effective therapy; recurrence post-transplant ~20% at 5 years
- Liver transplant indications in PSC: recurrent cholangitis, biliary dysplasia, end-stage liver disease (MELD >=15)

---

## Wilson's Disease

### Overview

- Autosomal recessive copper metabolism disorder
- ATP7B gene mutation on chromosome 13
- Impaired hepatic copper excretion into bile → copper accumulation in liver, brain, eyes, kidneys
- Presentation typically in adolescence or young adulthood (5-35 years)

### Clinical Features

- Hepatic: acute hepatitis, chronic hepatitis, fulminant liver failure, cirrhosis
- Neurological/psychiatric: dysarthria, tremor, dystonia, Parkinsonism, psychiatric symptoms (behavioral changes, depression, psychosis)
- Kayser-Fleischer (KF) rings: copper deposits in Descemet's membrane of cornea; golden-brown rings; detected by slit-lamp examination
- Coombs-negative hemolytic anemia (copper-mediated RBC membrane damage)
- Renal tubular dysfunction (Fanconi syndrome)

### Diagnosis

| Test | Diagnostic Value |
|---|---|
| Serum ceruloplasmin | <20 mg/dL in ~95% of Wilson's disease (low sensitivity in liver failure) |
| 24-hour urine copper | >100 mcg/24hr (baseline); >25 mcg/24hr post-penicillamine challenge |
| Serum copper (free/non-ceruloplasmin-bound) | Elevated (>1.6 micromol/L) |
| Liver copper content (biopsy) | >250 mcg/g dry weight (gold standard) |
| KF rings | Present in >95% of neurological Wilson's; absent in ~50% of hepatic-only presentation |
| ATP7B gene sequencing | Confirms diagnosis; identifies compound heterozygotes |

Leipzig scoring system: combines serology, urine copper, KF rings, neurological features, and biopsy.

### Treatment

| Drug | Dose | Notes |
|---|---|---|
| Penicillamine | 750-1500mg/day in 2-4 divided doses | First-line; copper chelation; start low and titrate; pyridoxine 25mg/day supplement |
| Trientine (Triethylene tetramine) | 750-1500mg/day in 2-3 divided doses | Alternative to penicillamine; fewer side effects; preferred if penicillamine intolerance |
| Zinc acetate | 50mg elemental zinc TID (adults); 25mg TID (children <50kg) | First-line for maintenance or presymptomatic patients; inhibits intestinal copper absorption |
| Tetrathiomolybdate | Investigational | Rapid copper chelation for acute neurological Wilson's; prevent chelation-mediated neurological deterioration |

Monitoring: 24-hour urine copper, serum free copper, neurological exams. Liver transplant: indicated for fulminant Wilson's or decompensated cirrhosis not responding to medical therapy.

---

## Hereditary Hemochromatosis (HH)

### Overview

- Most common hereditary liver disease in Northern European descent populations
- HFE gene mutations: C282Y/C282Y homozygotes account for ~85-90% of classic HH
- Penetrance: clinical iron overload in ~28% of male C282Y homozygotes; ~1% of female homozygotes
- Iron deposition in liver, pancreas, heart, pituitary, joints, skin

### Clinical Features

- Cirrhosis (occurs with hepatic iron index >1.9)
- Diabetes mellitus ("bronze diabetes")
- Cardiomyopathy / arrhythmias
- Hypogonadism (pituitary iron deposition)
- Arthropathy (2nd and 3rd metacarpophalangeal joints)
- Bronze skin pigmentation
- Hepatocellular carcinoma (200x increased risk in HH cirrhosis vs. general population)

### Diagnosis

| Test | Finding |
|---|---|
| Transferrin saturation (fasting) | >45% (diagnostic threshold); >60% in men, >50% in women highly suggestive |
| Serum ferritin | Elevated (>200 mcg/L women; >300 mcg/L men); non-specific (acute phase reactant) |
| HFE gene mutation testing | C282Y/C282Y, C282Y/H63D compound heterozygote |
| Liver biopsy + hepatic iron index | HIQ (iron mcg/g dry weight / 56 / age) >1.9 = HH; Perl's Prussian blue stain |
| MRI liver | T2* gradient echo: quantifies hepatic iron; non-invasive |

### Treatment

- Therapeutic phlebotomy: 1 unit (500mL) of whole blood = ~200-250mg of iron removed
- Induction phase: weekly phlebotomy until ferritin <50 mcg/L and transferrin saturation <30%
- Maintenance phase: phlebotomy every 2-4 months to maintain ferritin 50-100 mcg/L
- Monitor: CBC (hold phlebotomy if Hgb <11 g/dL), ferritin, transferrin saturation
- Chelation therapy (deferasirox, deferoxamine): reserved for patients unable to tolerate phlebotomy (anemia); less effective
- Genetic screening: first-degree relatives should be screened with HFE testing + transferrin saturation

Reversibility: fibrosis and some cirrhosis can regress with treatment; HCC risk remains elevated even after iron depletion in cirrhosis; HCC surveillance mandatory.

---

## Hepatocellular Carcinoma (HCC) Surveillance

### Indications for HCC Surveillance

All cirrhotic patients regardless of etiology.

Additional non-cirrhotic patients requiring surveillance:
- HBV infection with risk factors (see HBV section above)
- NASH-related advanced fibrosis (F3)

### Surveillance Protocol

- Ultrasound every 6 months (standard of care)
- AFP (alpha-fetoprotein) added to ultrasound at most centers (increases sensitivity ~13% vs. ultrasound alone)
- CT or MRI liver: diagnostic workup for nodule detected on surveillance; not used for routine surveillance
- Alternative to ultrasound in poor acoustic window (obesity, cirrhosis): contrast-enhanced CT or MRI every 6 months

### LI-RADS Diagnostic Criteria for HCC

Liver Imaging Reporting and Data System (LI-RADS) for CT/MRI in cirrhotic patients:

| Category | Definition |
|---|---|
| LR-1 | Definitely benign |
| LR-2 | Probably benign |
| LR-3 | Intermediate probability of HCC |
| LR-4 | Probably HCC |
| LR-5 | Definitely HCC (diagnostic without biopsy) |
| LR-M | Probably malignant, not HCC specific |
| LR-TIV | Tumor in vein |

LR-5 criteria (major features): arterial phase hyperenhancement (APHE) + washout appearance + enhancing capsule + threshold growth (>50% diameter increase in <6 months).

### HCC Treatment Options by Stage

| Stage | Treatment |
|---|---|
| Very early (single <2cm, Child A) | Resection or ablation (RFA/MWA) |
| Early (Milan criteria, any Child) | Liver transplant (best outcomes), resection (Child A), or ablation |
| Intermediate (multifocal, no vascular invasion) | TACE (transarterial chemoembolization) |
| Advanced (vascular invasion or metastases) | Sorafenib, lenvatinib, atezolizumab + bevacizumab |
| Terminal (Child C, PS 3-4) | Best supportive care |

---

## Key Laboratory Reference Ranges for Liver Disease

| Lab Value | Normal Range | Clinical Significance in Liver Disease |
|---|---|---|
| ALT | 7-56 U/L | Hepatocellular injury marker; >10x ULN = severe injury |
| AST | 10-40 U/L | Less specific than ALT; elevated in muscle disease; AST:ALT >2 suggests ALD |
| ALP | 44-147 U/L | Cholestatic disease; bile duct obstruction; bone disease |
| GGT | 8-61 U/L | Sensitive for biliary disease and alcohol use; not specific |
| Total bilirubin | 0.2-1.2 mg/dL | >2.5mg/dL produces clinical jaundice; critical marker in Child-Pugh and MELD |
| Direct bilirubin | 0-0.3 mg/dL | Conjugated; elevated in hepatocellular disease and cholestasis |
| Albumin | 3.5-5.0 g/dL | Synthetic function; half-life ~20 days; decreases with chronic hepatic failure |
| PT/INR | INR 0.9-1.1 | Best acute synthetic function marker; half-life of factors hours to days |
| Ammonia | 15-60 mcg/dL | Elevated in HE; not used alone for HE diagnosis or management |
| Platelet count | 150-400 x 10^9/L | Thrombocytopenia = portal hypertension / splenic sequestration |
| Creatinine | 0.7-1.3 mg/dL (men) | Critical in MELD calculation; HRS threshold >=1.5mg/dL |
| Sodium | 135-145 mEq/L | Hyponatremia = poor prognosis; MELD-Na adjustment |

---

## Summary of Scoring Systems

| Score | Components | Use |
|---|---|---|
| Child-Pugh | Bilirubin, albumin, INR, ascites, encephalopathy | Surgical risk; transplant candidacy; prognosis |
| MELD-Na | Bilirubin, INR, creatinine, sodium | Waitlist priority; 90-day mortality prediction |
| Maddrey DF | PT prolongation, bilirubin | Severe alcoholic hepatitis; steroid indication |
| Lille Score | Age, albumin, bilirubin change, renal failure, PT | Day-7 steroid response in AH |
| FIB-4 | Age, AST, ALT, platelets | Non-invasive fibrosis staging (NAFLD, HCV) |
| SAAG | Serum albumin - ascites albumin | Ascites etiology (portal vs. non-portal) |
| NAS | Steatosis, inflammation, ballooning | NASH histological activity grading |
| RUCAM | 7-domain causality scoring | Drug-induced liver injury attribution |
| King's College | pH, INR, Cr, bilirubin, age, etiology | ALF transplant listing criteria |
| West Haven | Consciousness, cognition, behavior, neuro signs | Hepatic encephalopathy grading |
| HVPG | Measured via hepatic vein catheterization | Portal pressure; bleeding risk threshold |
| LI-RADS | CT/MRI enhancement characteristics | HCC diagnosis and reporting |

---

*This knowledge base is intended for clinical reference and RAG-assisted decision support. All clinical decisions should incorporate complete patient history, current guidelines, and specialist consultation. Information current as of early 2026.*
