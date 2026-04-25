# Internal Medicine Knowledge Base

**Scope:** Hospital-grade internal medicine reference for clinical decision support.
**Intended use:** Open WebUI RAG system (chunk size 1500, overlap 200, Top K 5).
**Last updated:** 2026-04-10

---

## Table of Contents

1. Cardiology
   - Acute Coronary Syndrome
   - Heart Failure
   - Atrial Fibrillation
   - Valvular Heart Disease
2. Pulmonology
   - COPD
   - Asthma
   - Pulmonary Embolism
   - Community-Acquired Pneumonia
3. Sepsis and Septic Shock
4. Rheumatology
   - Rheumatoid Arthritis
   - Systemic Lupus Erythematosus
   - Gout
5. Hematology
   - Anemia
   - Anticoagulation Management
6. Neurology
   - Ischemic Stroke
   - TIA

---

# CARDIOLOGY

---

## Acute Coronary Syndrome (ACS)

### Definitions and Classification

Acute coronary syndrome encompasses three related conditions caused by acute myocardial ischemia, differentiated primarily by ECG findings and biomarker results.

| Condition | ECG Finding | Troponin | Clinical Significance |
|---|---|---|---|
| STEMI | ST elevation (see criteria below) OR new LBBB | Elevated (may be initially negative) | Complete occlusion — emergent PCI required |
| NSTEMI | ST depression, T-wave inversion, or nonspecific changes (no ST elevation) | Elevated | Partial occlusion — early invasive vs. ischemia-guided strategy |
| Unstable Angina (UA) | Same as NSTEMI | Normal (negative) | Supply-demand mismatch without necrosis |

### STEMI ECG Criteria

ST elevation must be measured at the J-point and meet the following thresholds:

- Leads V2-V3: >=2 mm in men >=40 years; >=2.5 mm in men <40 years; >=1.5 mm in women
- All other leads: >=1 mm in at least two contiguous leads
- Posterior STEMI: ST depression V1-V3 with tall R waves (reciprocal changes from posterior wall)
- New or presumably new LBBB with ischemic symptoms = STEMI equivalent

**Localization by leads:**

| Territory | Leads | Artery |
|---|---|---|
| Anterior | V1-V4 | LAD |
| Lateral | I, aVL, V5-V6 | LCx or diagonal |
| Inferior | II, III, aVF | RCA (80%) or LCx (20%) |
| Posterior | V1-V3 ST depression | RCA or LCx |
| RV infarct | V4R | RCA proximal |

### Troponin Kinetics

High-sensitivity troponin (hs-cTnI or hs-cTnT) is the preferred biomarker. Serial measurements are required to detect rise and fall patterns consistent with acute MI.

| Timepoint | Conventional Troponin | High-Sensitivity Troponin |
|---|---|---|
| Detectable rise above URL | 3-6 hours after symptom onset | 1-3 hours after symptom onset |
| Peak | 12-24 hours | 12-24 hours |
| Normalization | 5-10 days (cTnI); up to 14 days (cTnT) | 5-10 days |

- URL = 99th percentile upper reference limit
- Acute MI pattern: rise and/or fall with at least one value above URL plus ischemic symptoms or ECG changes
- Rapid rule-out protocol (hs-cTn): 0h/2h or 0h/3h algorithms acceptable if values below low-risk threshold

**Non-ACS causes of elevated troponin:**
- Myocarditis, pericarditis, heart failure (chronic elevation)
- PE, RV strain
- Renal failure (impaired clearance)
- Sepsis, critical illness
- Stress cardiomyopathy (Takotsubo)
- Cardiac contusion

---

### TIMI Risk Score for NSTEMI/UA

The TIMI (Thrombolysis in Myocardial Infarction) score for UA/NSTEMI predicts 14-day risk of death, MI, or urgent revascularization.

**Seven variables (1 point each):**

| Variable | Threshold |
|---|---|
| Age >=65 years | Yes = 1 pt |
| >=3 CAD risk factors (HTN, DM, hyperlipidemia, FHx, active smoking) | Yes = 1 pt |
| Known CAD (prior stenosis >=50%) | Yes = 1 pt |
| Aspirin use in past 7 days | Yes = 1 pt (paradoxically higher risk) |
| >=2 anginal events in past 24 hours | Yes = 1 pt |
| ST deviation >=0.5 mm on presenting ECG | Yes = 1 pt |
| Positive cardiac biomarker | Yes = 1 pt |

**Score interpretation:**

| Score | Risk Category | 14-Day Event Rate |
|---|---|---|
| 0-1 | Low | ~5% |
| 2-3 | Intermediate | ~8-13% |
| 4-5 | High | ~20-26% |
| 6-7 | Very High | ~41% |

- Score >=2: Consider early invasive strategy
- Score >=3: Strong evidence favors invasive approach within 24-72 hours

---

### STEMI Management Algorithm

**Time targets:**
- First medical contact (FMC) to device (FMC-to-balloon): <120 minutes
- Door-to-balloon (DTB): <90 minutes at PCI-capable hospital
- FMC-to-thrombolytic: <30 minutes if PCI not available within 120 min

**Immediate pharmacotherapy (initiate in ED, pre-cath lab):**

| Drug | Dose | Route | Timing |
|---|---|---|---|
| Aspirin | 325 mg (non-enteric coated, chewed) | PO | Immediately |
| Ticagrelor | 180 mg loading dose, then 90 mg BID | PO | Preferred P2Y12 (unless CABG planned) |
| Prasugrel | 60 mg loading dose, then 10 mg daily | PO | Alternative to ticagrelor (avoid if age >75, weight <60 kg, or prior stroke/TIA) |
| Clopidogrel | 600 mg loading dose, then 75 mg daily | PO | Use if ticagrelor/prasugrel contraindicated |
| UFH (unfractionated heparin) | 60 U/kg bolus (max 4000 U), then 12 U/kg/hr (max 1000 U/hr) | IV | Preferred during PCI |
| Enoxaparin | 0.5 mg/kg IV bolus | IV | Alternative to UFH |
| Bivalirudin | 0.75 mg/kg bolus, 1.75 mg/kg/hr infusion | IV | Alternative if HIT or bleeding risk |

**Primary PCI:** Preferred reperfusion strategy at PCI-capable hospitals within 90 minutes door-to-balloon.

**Thrombolytic therapy (if PCI unavailable within 120 min of FMC):**

*Alteplase (tPA) dosing for STEMI:*
- Weight-based: 15 mg IV bolus, then 0.75 mg/kg over 30 min (max 50 mg), then 0.5 mg/kg over 60 min (max 35 mg)
- Maximum total dose: 100 mg

*Absolute contraindications to thrombolytics:*
- Any prior intracranial hemorrhage
- Ischemic stroke within 3 months
- Structural cerebral vascular lesion (AVM, aneurysm)
- Intracranial malignancy
- Significant closed-head trauma or facial trauma within 3 months
- Active bleeding (excluding menses)
- Suspected aortic dissection

*Relative contraindications:*
- Severe uncontrolled hypertension (SBP >180 mmHg or DBP >110 mmHg)
- Ischemic stroke >3 months ago
- Traumatic CPR
- Major surgery within 3 weeks
- INR >2, prolonged aPTT
- Pregnancy

**Post-thrombolysis:** Transfer to PCI-capable facility. Pharmacoinvasive strategy: PCI within 3-24 hours if thrombolysis successful; rescue PCI immediately if failed.

---

### NSTEMI/UA Management

**Risk stratification drives timing of invasive strategy:**

| Strategy | Timing | Indication |
|---|---|---|
| Immediate invasive | <2 hours | Refractory ischemia, hemodynamic instability, cardiogenic shock, ventricular arrhythmias |
| Early invasive | <24 hours | TIMI >=3, GRACE score >140, new ST depression, elevated troponin |
| Delayed invasive | 24-72 hours | TIMI 1-2, intermediate risk features |
| Ischemia-guided (conservative) | If no high-risk features | Low TIMI/GRACE, no recurrent symptoms, no high-risk ECG changes |

**Anticoagulation options for NSTEMI/UA:**

| Agent | Dose | Notes |
|---|---|---|
| UFH | 60 U/kg IV bolus (max 4000 U), 12 U/kg/hr infusion (max 1000 U/hr) | aPTT target 50-70 sec; flexible, reversible |
| Enoxaparin | 1 mg/kg SQ BID (or 1 mg/kg IV if PCI within 8 hrs) | Reduce to 1 mg/kg SQ daily if CrCl <30 mL/min |
| Fondaparinux | 2.5 mg SQ daily | Preferred in conservative strategy; add UFH if PCI |
| Bivalirudin | 0.1 mg/kg bolus, 0.25 mg/kg/hr | PCI only; preferred if HIT |

**Antiplatelet:** Aspirin 325 mg loading, then 81 mg daily + P2Y12 inhibitor (ticagrelor preferred over clopidogrel based on PLATO trial)

---

## Heart Failure

### Classification by Ejection Fraction

| Type | EF | Definition |
|---|---|---|
| HFrEF (Heart Failure with Reduced EF) | <40% | Classic "systolic heart failure" — target of most GDMT |
| HFmrEF (mildly reduced EF) | 40-49% | Borderline/intermediate; emerging evidence for GDMT |
| HFpEF (preserved EF) | >=50% | Diastolic dysfunction; fewer proven therapies |

### NYHA Functional Classification

| Class | Description | Symptoms |
|---|---|---|
| I | No limitation | Ordinary activity does NOT cause symptoms |
| II | Slight limitation | Comfortable at rest; ordinary activity causes fatigue, dyspnea, or palpitations |
| III | Marked limitation | Comfortable at rest; less than ordinary activity causes symptoms |
| IV | Symptoms at rest | Unable to carry out any activity without discomfort |

---

### GDMT (Guideline-Directed Medical Therapy) for HFrEF

All four pillars have shown mortality benefit in HFrEF (EF <40%). Initiate and uptitrate each class concurrently when possible.

**Pillar 1: ACE Inhibitors / ARBs / ARNI**

| Drug | Starting Dose | Target Dose | Notes |
|---|---|---|---|
| Lisinopril (ACEi) | 2.5-5 mg daily | 20-40 mg daily | Monitor K+, creatinine, BP; avoid if angioedema history |
| Enalapril (ACEi) | 2.5 mg BID | 10-20 mg BID | Reference drug from SOLVD trial |
| Losartan (ARB) | 25-50 mg daily | 150 mg daily | Use if ACEi intolerant (cough, angioedema) |
| Sacubitril-valsartan (ARNI) | 24/26 mg BID | 97/103 mg BID | Preferred over ACEi (PARADIGM-HF); washout 36h from ACEi before initiating; avoid with ACEi |

**Pillar 2: Beta-Blockers** (only carvedilol, metoprolol succinate, and bisoprolol have proven mortality benefit)

| Drug | Starting Dose | Target Dose | Notes |
|---|---|---|---|
| Carvedilol | 3.125 mg BID | 25 mg BID (50 mg BID if >85 kg) | Alpha + non-selective beta blocker; take with food |
| Metoprolol succinate (XL) | 12.5-25 mg daily | 200 mg daily | Beta-1 selective; once daily dosing |
| Bisoprolol | 1.25 mg daily | 10 mg daily | Beta-1 selective; useful in CKD |

Note: Do NOT initiate in acute decompensated HF. Uptitrate every 2 weeks as tolerated.

**Pillar 3: Mineralocorticoid Receptor Antagonists (MRA)**

| Drug | Starting Dose | Target Dose | Indications/Contraindications |
|---|---|---|---|
| Spironolactone | 12.5-25 mg daily | 25-50 mg daily | NYHA II-IV, EF <=35%; avoid if K+ >5.0, CrCl <30, or on potassium supplement without monitoring |
| Eplerenone | 25 mg daily | 50 mg daily | Post-MI LV dysfunction; fewer anti-androgenic side effects |

**Pillar 4: SGLT2 Inhibitors**

| Drug | Dose | Notes |
|---|---|---|
| Dapagliflozin | 10 mg daily | DAPA-HF trial; reduces hospitalizations and CV death in HFrEF |
| Empagliflozin | 10 mg daily | EMPEROR-Reduced trial; also benefit in HFpEF (EMPEROR-Preserved) |

**Diuretics (symptom management — no mortality benefit, but essential for congestion):**

| Drug | Oral Dose Range | IV Dose | Notes |
|---|---|---|---|
| Furosemide (loop) | 20-240 mg/day (once or twice daily) | IV dose = 1-2.5x oral dose; bolus or continuous infusion | First-line diuretic; monitor electrolytes |
| Torsemide (loop) | 10-200 mg/day | IV available | Better oral bioavailability than furosemide (~80% vs 50%) |
| Bumetanide (loop) | 0.5-5 mg/day | IV available | 1 mg bumetanide = 40 mg furosemide |
| Hydrochlorothiazide (thiazide) | 12.5-25 mg daily | Not available IV | Add-on for diuretic resistance (sequential nephron blockade) |
| Metolazone | 2.5-10 mg daily or PRN | Not available IV | Potent thiazide-like; used for refractory volume overload |

**Loop diuretic resistance strategies:**
1. Increase dose or switch to IV route
2. Add metolazone 30-60 min before loop diuretic
3. Consider continuous IV infusion (DOSE trial: bolus vs. infusion equally effective but infusion may improve symptom control)
4. Evaluate for adherence, dietary sodium intake, NSAID use, CKD progression

---

### Acute Decompensated Heart Failure (ADHF)

**Initial assessment:**
- Identify precipitant: dietary indiscretion, medication non-adherence, ACS, infection, arrhythmia, HTN emergency
- Determine hemodynamic profile: wet/dry (congested vs. not) and warm/cold (adequate vs. poor perfusion)

**Hemodynamic profile-directed therapy:**

| Profile | CO/Perfusion | Congestion | Treatment |
|---|---|---|---|
| Warm & Wet | Adequate | Yes | IV diuresis (first-line), vasodilators if no hypotension |
| Cold & Wet | Reduced | Yes | Inotropes + diuresis; consider invasive monitoring |
| Cold & Dry | Reduced | No | Fluid challenge if truly hypovolemic; inotropic support |
| Warm & Dry (euvolemic) | Adequate | No | Optimize outpatient GDMT |

**IV Diuresis Protocol (ADHF):**
- Furosemide IV: If already on oral furosemide, start IV dose at 1-2.5x total daily oral dose
- Goal: urine output 1-3 mL/kg/hr in first 6 hours
- If inadequate response at 2-6 hours: double the dose or switch to continuous infusion
- Daily electrolytes; replace K+ and Mg2+ as needed

**Non-invasive ventilation:**
- BiPAP (bilevel positive airway pressure): 10/5 cmH2O typical starting settings; reduces intubation rate in cardiogenic pulmonary edema (3CPO trial)
- CPAP: 5-10 cmH2O; effective for flash pulmonary edema

**Vasodilators:**
- Nitroglycerin IV: 5-10 mcg/min, titrate by 5-10 mcg/min every 3-5 min to symptom relief; avoid if SBP <90 mmHg or recent PDE5 inhibitor use
- Nitroprusside: 0.3-0.5 mcg/kg/min; effective but cyanide toxicity risk if prolonged (>48h) or hepatic/renal failure

**Inotropes (for low-output/cardiogenic shock):**

| Drug | Mechanism | Dose | Notes |
|---|---|---|---|
| Dobutamine | Beta-1 agonist | 2-20 mcg/kg/min | Inodilator; increases HR; may worsen ischemia |
| Milrinone | PDE3 inhibitor | 0.125-0.75 mcg/kg/min; optional 50 mcg/kg bolus | Vasodilatory; avoid in hypotension; renally cleared |
| Dopamine | Dopaminergic/Beta-1/Alpha (dose-dependent) | 2-20 mcg/kg/min | Low dose (2-5): renal vasodilation; intermediate (5-10): inotropy; high dose (>10): vasoconstriction |

---

### HFpEF Management

Evidence base is sparser compared to HFrEF. Management is largely directed at symptom control and comorbidities.

- Diuretics: essential for volume management (same as HFrEF); furosemide PO or IV
- Spironolactone: TOPCAT trial — modest reduction in hospitalizations; consider for EF 45-55%, elevated BNP, CrCl >30, K+ <5.0
- SGLT2 inhibitors: Empagliflozin (EMPEROR-Preserved) and dapagliflozin (DELIVER) show meaningful reduction in CV death/HF hospitalization — recommended in ACC/AHA 2022 guidelines
- Blood pressure control: target <130/80 mmHg; ACEi/ARB preferred
- Heart rate control: especially in AF — avoid tachycardia (impairs diastolic filling)
- Treat underlying causes: HTN, obesity, AF, sleep apnea, DM

---

## Atrial Fibrillation

### Classification

| Type | Definition |
|---|---|
| Paroxysmal | Terminates spontaneously or with intervention within 7 days |
| Persistent | Continuous AF lasting >7 days (requires cardioversion to terminate) |
| Long-standing persistent | Continuous AF >12 months |
| Permanent | Ongoing AF where rhythm control is not pursued (joint patient-physician decision) |

### Rate Control

**Target:** Resting heart rate <80 bpm (strict) or <110 bpm (lenient — RACE II trial shows lenient acceptable in most patients without symptoms)

| Drug | IV Dose (Acute) | Oral Dose (Maintenance) | Notes |
|---|---|---|---|
| Metoprolol tartrate | 2.5-5 mg IV over 2 min, up to 3 doses | 25-100 mg BID | Preferred in HFrEF; avoid in decompensated HF |
| Metoprolol succinate | N/A | 25-200 mg daily | Extended release for maintenance |
| Diltiazem | 0.25 mg/kg IV over 2 min; then 5-15 mg/hr infusion | 120-360 mg daily (ER) | Avoid in HFrEF (EF <40%) or decompensated HF |
| Verapamil | 0.075-0.15 mg/kg IV | 120-360 mg daily (ER) | Avoid in HF, WPW |
| Digoxin | 0.25-0.5 mg IV loading (total 0.75-1.5 mg in 24h) | 0.125-0.25 mg daily | Useful in HFrEF or sedentary patients; narrow therapeutic index; target level 0.5-0.9 ng/mL |
| Amiodarone | 150 mg IV over 10 min, then 1 mg/min x6h, 0.5 mg/min x18h | 100-200 mg daily | Rate + rhythm control; use when others fail or in unstable AF with rapid ventricular response |

### Rhythm Control

**Indications:** Symptomatic AF despite rate control, first-episode AF, AF-induced cardiomyopathy, patient preference

**Cardioversion:**
- Electrical cardioversion (DCCV): 120-200 J biphasic (synchronized); effective >90% for termination
- Anticoagulation prior to cardioversion: if AF duration >48h or unknown duration — anticoagulate for >=3 weeks before and >=4 weeks after; or perform TEE to rule out LA thrombus
- If AF <48h duration: cardioversion can proceed without prior anticoagulation (still anticoagulate post-cardioversion for >=4 weeks)

**Antiarrhythmic drugs:**

| Drug | Dose | Use in Structural Heart Disease | Adverse Effects |
|---|---|---|---|
| Flecainide | 50-150 mg BID | Contraindicated if CAD or LV dysfunction | Proarrhythmic (VT); use only with rate control agent |
| Propafenone | 150-300 mg TID or ER 225-425 mg BID | Contraindicated if CAD or LV dysfunction | Metallic taste; GI; avoid in asthma |
| Dronedarone | 400 mg BID | Contraindicated in NYHA III-IV HF (ANDROMEDA trial) | Better safety than amiodarone; less effective |
| Amiodarone | 200-400 mg daily (loading 400 mg BID x4 weeks) | Safe in structural heart disease including HFrEF | Pulmonary toxicity, thyroid dysfunction, hepatotoxicity, photosensitivity; requires monitoring |
| Sotalol | 80-160 mg BID | Use with caution in CAD; avoid in LV dysfunction | QTc prolongation; initiate in monitored setting |
| Dofetilide | 250-500 mcg BID | Safe in structural heart disease | QTc prolongation; requires 3-day inpatient initiation |

---

### CHA2DS2-VASc Score for Stroke Risk in AF

| Risk Factor | Points |
|---|---|
| Congestive heart failure (or EF <40%) | 1 |
| Hypertension | 1 |
| Age >=75 years | 2 |
| Diabetes mellitus | 1 |
| Stroke or TIA history | 2 |
| Vascular disease (prior MI, PAD, or aortic plaque) | 1 |
| Age 65-74 years | 1 |
| Sex category female | 1 |
| **Maximum score** | **9** |

**Anticoagulation thresholds (ACC/AHA 2023):**
- Men: CHA2DS2-VASc >=2: anticoagulate; score 1: consider
- Women: CHA2DS2-VASc >=3: anticoagulate; score 2: consider
- Score 0 (men) or 1 (women, sex-point only): anticoagulation not recommended

---

### DOAC and Anticoagulant Dosing in AF

| Drug | Standard Dose | Dose Reduction Criteria | Renal Threshold for Avoidance |
|---|---|---|---|
| Apixaban (Eliquis) | 5 mg BID | 2.5 mg BID if >=2 of: age >=80, weight <=60 kg, SCr >=1.5 mg/dL | CrCl <25 mL/min (use caution; limited data) |
| Rivaroxaban (Xarelto) | 20 mg daily with evening meal | 15 mg daily if CrCl 15-50 mL/min | Avoid if CrCl <15 mL/min |
| Dabigatran (Pradaxa) | 150 mg BID | 75 mg BID if CrCl 15-30 mL/min | Avoid if CrCl <15 mL/min |
| Edoxaban (Savaysa) | 60 mg daily | 30 mg daily if CrCl 15-50 mL/min, weight <=60 kg, or P-gp inhibitor | Avoid if CrCl >95 mL/min (reduced efficacy) |
| Warfarin | Individualized | N/A — adjust to INR 2-3 | Adjust dose based on INR; usable in dialysis |

**DOAC selection in CKD:**

| CrCl (mL/min) | Preferred Approach |
|---|---|
| >=50 | Any DOAC at standard dose |
| 25-50 | Apixaban (reduced dose if criteria met); rivaroxaban 15 mg; dabigatran use with caution |
| 15-24 | Apixaban 2.5 mg BID preferred (most data); warfarin alternative |
| <15 / Dialysis | Warfarin (target INR 2-3); apixaban 5 mg BID in selected dialysis patients (DOAC-Dialysis trial data emerging) |

---

## Valvular Heart Disease

### Aortic Stenosis

**Auscultation:** Harsh, crescendo-decrescendo systolic ejection murmur, best heard at right upper sternal border (RUSB), radiates to carotids; S4 may be present; paradoxically split S2 in severe AS.

**Echocardiographic severity criteria:**

| Parameter | Mild | Moderate | Severe |
|---|---|---|---|
| Peak velocity (m/s) | 2.0-2.9 | 3.0-3.9 | >=4.0 |
| Mean gradient (mmHg) | <20 | 20-39 | >=40 |
| Aortic valve area (AVA, cm2) | >1.5 | 1.0-1.5 | <1.0 |
| AVA index (cm2/m2) | >0.85 | 0.6-0.85 | <0.6 |

**Low-flow, low-gradient AS:** AVA <1.0 cm2 with mean gradient <40 mmHg — requires dobutamine stress echo or CT calcium scoring to confirm severity.

**Indications for intervention (AHA/ACC 2021):**
- Severe AS + symptoms (angina, syncope, dyspnea): Class I indication
- Severe AS + LVEF <50%: Class I indication
- Asymptomatic severe AS + LVEF 50-55% (very severe: Vmax >=5 m/s): Class IIa

**SAVR vs. TAVR:**

| Patient Profile | Preferred Approach |
|---|---|
| Low surgical risk, age <65, anatomically suitable for durable surgical prosthesis | SAVR |
| Intermediate surgical risk, age 65-80 | Either SAVR or TAVR (shared decision) |
| High/prohibitive surgical risk, age >80 | TAVR preferred |
| Young patients needing concomitant CABG or other valve surgery | SAVR |

### Mitral Regurgitation

**Primary (organic) MR:** Structural valve pathology (MVP, chordal rupture, endocarditis, rheumatic)
- Indications for surgery: Symptomatic severe MR; asymptomatic severe MR with LVEF <=60% or LVESD >=40 mm
- Valve repair preferred over replacement when feasible

**Secondary (functional) MR:** MR due to LV remodeling in HFrEF/ischemic cardiomyopathy
- Medical: Optimize GDMT; cardiac resynchronization therapy if LBBB + EF <=35%
- Interventional: TEER (transcatheter edge-to-edge repair, MitraClip) if patient meets COAPT criteria: symptomatic on GDMT, anatomy favorable, no surgical candidate

### Infective Endocarditis Prophylaxis

**Indications (AHA 2007 guidelines — still standard):**

Dental procedures involving gingival manipulation or perforation of oral mucosa in patients with:
- Prosthetic cardiac valves or prosthetic material used for cardiac valve repair
- Prior infective endocarditis
- Congenital heart disease: unrepaired cyanotic CHD; repaired with prosthetic material within 6 months; repaired with residual defects
- Cardiac transplant with valvulopathy

**NOT indicated** for most other cardiac conditions including MVP without regurgitation, bicuspid AV without regurgitation, CAD, pacemakers.

**Regimen:** Amoxicillin 2g PO 30-60 minutes before procedure; ampicillin 2g IM/IV if unable to take oral; clindamycin 600 mg PO/IV if penicillin-allergic.

---

# PULMONOLOGY

---

## COPD

### GOLD 2023 Spirometric Classification

Diagnosis requires post-bronchodilator FEV1/FVC <0.70.

| GOLD Grade | FEV1 (% predicted, post-BD) | Airflow Limitation Severity |
|---|---|---|
| GOLD 1 (Mild) | >=80% | Mild |
| GOLD 2 (Moderate) | 50-79% | Moderate |
| GOLD 3 (Severe) | 30-49% | Severe |
| GOLD 4 (Very Severe) | <30% | Very severe |

### GOLD ABE Symptom/Risk Assessment

Replaces prior ABCD groups (no longer incorporates spirometry in group assignment). Assessment uses:
- mMRC dyspnea scale (0-4) or CAT score (0-40)
- Exacerbation history in prior year

| Group | Exacerbation History | Symptom Burden |
|---|---|---|
| A | 0-1 (not leading to hospitalization) | Low (mMRC 0-1, CAT <10) |
| B | 0-1 (not leading to hospitalization) | High (mMRC >=2, CAT >=10) |
| E (Exacerbator) | >=2 exacerbations OR >=1 hospitalization | Any |

---

### COPD Pharmacotherapy Ladder

**Initial therapy by group:**

| Group | Recommended Initial Therapy |
|---|---|
| A | SABA or SAMA PRN |
| B | LAMA (preferred) or LABA |
| E | LAMA + LABA; consider adding ICS if eos >=300 cells/uL |

**Escalation pathway:**

- Step 1: SABA (albuterol MDI 2 puffs q4-6h PRN) or SAMA (ipratropium 2 puffs QID)
- Step 2: LAMA monotherapy (tiotropium preferred) or LABA monotherapy
- Step 3: LAMA + LABA combination
- Step 4: ICS + LABA + LAMA (triple therapy)
- Consider roflumilast if Group E + FEV1 <50% + chronic bronchitis phenotype

**Key drug dosing:**

| Drug | Class | Device/Dose | Frequency |
|---|---|---|---|
| Albuterol (ProAir, Ventolin) | SABA | MDI: 90 mcg/puff, 2 puffs | q4-6h PRN |
| Levalbuterol (Xopenex) | SABA | MDI: 45 mcg/puff, 2 puffs | q4-6h PRN |
| Ipratropium (Atrovent) | SAMA | MDI: 17 mcg/puff, 2-3 puffs | QID |
| Tiotropium (Spiriva) | LAMA | Handihaler: 18 mcg dry powder capsule | Once daily |
| Umeclidinium (Incruse Ellipta) | LAMA | DPI: 62.5 mcg/inhalation | Once daily |
| Aclidinium (Tudorza) | LAMA | DPI: 400 mcg/inhalation | BID |
| Salmeterol (Serevent) | LABA | DPI: 50 mcg/inhalation | BID |
| Formoterol (Foradil, Perforomist) | LABA | DPI: 12 mcg capsule | BID |
| Fluticasone/salmeterol (Advair) | ICS/LABA | 250/50 or 500/50 mcg | BID |
| Budesonide/formoterol (Symbicort) | ICS/LABA | 160/4.5 or 320/9 mcg | BID |
| Fluticasone furoate/vilanterol (Breo Ellipta) | ICS/LABA | 100/25 or 200/25 mcg | Once daily |
| Umeclidinium/vilanterol/fluticasone furoate (Trelegy Ellipta) | LAMA/LABA/ICS (triple) | 62.5/25/100 mcg | Once daily |
| Roflumilast (Daliresp) | PDE4 inhibitor | 250 mcg daily x4 weeks, then 500 mcg daily | Once daily |

**ICS use in COPD:** Reserve for Group E with eos >=300 cells/uL or >=2 exacerbations. Avoid in recurrent pneumonia (increased risk with ICS). Withdraw ICS if eos <100 cells/uL.

---

### Acute COPD Exacerbation Management

**Definition:** Acute worsening of respiratory symptoms (dyspnea, sputum volume/purulence, cough) requiring change in therapy.

**Severity classification:**
- Mild: Treated with increased bronchodilators only
- Moderate: Requires systemic steroids and/or antibiotics
- Severe: Hospitalization required
- Very severe: ICU admission, mechanical ventilation

**Inpatient management protocol:**

| Intervention | Drug / Dose | Notes |
|---|---|---|
| SABA | Albuterol 2.5 mg q1-4h nebulized | First-line bronchodilator |
| SAMA | Ipratropium 0.5 mg q6-8h nebulized | Add to SABA; combination superior to either alone |
| Systemic steroids | Prednisone/prednisolone 40 mg PO daily x 5 days | Non-inferior to 14-day course (REDUCE trial); IV methylprednisolone 40 mg q8-24h if NPO |
| Antibiotics | See table below | Indicated if increased sputum purulence + increased dyspnea or volume |
| Supplemental O2 | Target SpO2 88-92% | Avoid excessive O2 — risk of CO2 retention and hypercapnic respiratory failure |
| NIV (BiPAP) | IPAP 12-20 cmH2O / EPAP 4-8 cmH2O | Indicated if pH <7.35, PaCO2 >=45 mmHg, RR >25; reduces intubation and mortality |

**Antibiotic selection for COPD exacerbation:**

| Severity / Risk | Drug | Dose | Duration |
|---|---|---|---|
| Mild-moderate, no Pseudomonas risk | Azithromycin | 500 mg day 1, then 250 mg days 2-5 | 5 days |
| Mild-moderate, no Pseudomonas risk | Doxycycline | 100 mg BID | 5 days |
| Mild-moderate, no Pseudomonas risk | Amoxicillin-clavulanate | 875/125 mg BID | 5-7 days |
| Severe or Pseudomonas risk (frequent steroids, FEV1 <30%, prior Pseudomonas isolation) | Ciprofloxacin or levofloxacin | Cipro 400 mg IV/750 mg PO BID; Levo 750 mg daily | 7-10 days |

**NIV indications in acute COPD exacerbation:**
- pH 7.25-7.35 + hypercapnia (PaCO2 >=45 mmHg): strong indication
- pH <7.25: trial of NIV acceptable but high failure rate; prepare for intubation
- RR >25/min, accessory muscle use, paradoxical breathing

**ICU transfer criteria:**
- Failure of NIV
- pH <7.25 with NIV
- Hemodynamic instability
- Decreased consciousness
- Life-threatening arrhythmia

---

## Asthma

### NAEPP Severity Classification (Persistent vs. Intermittent)

| Parameter | Intermittent | Mild Persistent | Moderate Persistent | Severe Persistent |
|---|---|---|---|---|
| Daytime symptoms | <=2 days/week | >2 days/week but not daily | Daily | Throughout the day |
| Nighttime awakenings | <=2x/month | 3-4x/month | >1x/week but not nightly | Often 7x/week |
| SABA use for symptoms | <=2 days/week | >2 days/week | Daily | Several times/day |
| Interference with normal activity | None | Minor limitation | Some limitation | Extremely limited |
| FEV1 (% predicted) | >80% | >80% | 60-80% | <60% |
| FEV1/FVC | Normal | Normal | Reduced by 5% | Reduced >5% |

### Asthma Step Therapy (NAEPP/GINA Framework)

| Step | Preferred Controller | Alternative | Rescue |
|---|---|---|---|
| Step 1 (Intermittent) | None (PRN SABA) | Consider low-dose ICS | SABA PRN |
| Step 2 (Mild Persistent) | Low-dose ICS | LTRA (montelukast), cromolyn, theophylline | SABA PRN |
| Step 3 (Moderate Persistent) | Low-dose ICS + LABA OR medium-dose ICS | Low-dose ICS + LTRA or theophylline | SABA PRN |
| Step 4 | Medium-dose ICS + LABA | Medium-dose ICS + LTRA | SABA PRN |
| Step 5 | High-dose ICS + LABA; consider biologic | Tiotropium add-on | SABA PRN |
| Step 6 | High-dose ICS + LABA + oral corticosteroid | Add biologic if severe allergic or eosinophilic | SABA PRN |

**Key ICS dosing (low/medium/high by NAEPP):**

| Drug | Low Dose | Medium Dose | High Dose |
|---|---|---|---|
| Fluticasone propionate (MDI, mcg/day) | 88-264 | 264-440 | >440 |
| Budesonide (DPI, mcg/day) | 180-540 | 540-1080 | >1080 |
| Beclomethasone (MDI, mcg/day) | 80-240 | 240-480 | >480 |
| Ciclesonide (MDI, mcg/day) | 80-160 | 160-320 | >320 |

**LTRA:** Montelukast 10 mg PO nightly (adults); 4 mg chewable tablet (ages 2-5), 5 mg (ages 6-14)

**Biologics for severe asthma:**

| Drug | Mechanism | Indication | Dose |
|---|---|---|---|
| Omalizumab (Xolair) | Anti-IgE | Severe allergic asthma, IgE 30-700 IU/mL, positive perennial allergen skin test, uncontrolled on high-dose ICS/LABA | 75-375 mg SQ q2-4 weeks (dose by weight and IgE) |
| Mepolizumab (Nucala) | Anti-IL-5 | Severe eosinophilic asthma, eos >=150 cells/uL on treatment or >=300 cells/uL in prior year | 100 mg SQ q4 weeks |
| Benralizumab (Fasenra) | Anti-IL-5Ralpha | Severe eosinophilic asthma | 30 mg SQ q4 weeks x3, then q8 weeks |
| Dupilumab (Dupixent) | Anti-IL-4Ralpha (blocks IL-4 and IL-13) | Severe type 2/eosinophilic or oral steroid-dependent asthma | 400 mg SQ then 200 mg q2 weeks; or 600 mg then 300 mg q2 weeks |
| Tezepelumab (Tezspire) | Anti-TSLP | Severe uncontrolled asthma (any eosinophil count) | 210 mg SQ q4 weeks |

---

### Acute Severe Asthma / Status Asthmaticus

**Severity markers suggesting severe/life-threatening exacerbation:**
- PEFR or FEV1 <50% predicted after initial treatment
- SpO2 <92% on room air
- PaCO2 normal or elevated (indicates fatigue — impending respiratory failure)
- Inability to speak in full sentences
- Accessory muscle use, pulsus paradoxus >25 mmHg
- Silent chest on auscultation

**Management algorithm:**

| Intervention | Drug / Dose | Frequency / Notes |
|---|---|---|
| SABA | Albuterol 2.5-5 mg nebulized (or 4-8 puffs MDI with spacer) | q20 minutes x3 in first hour, then q1-4h |
| SAMA | Ipratropium 0.5 mg nebulized | q20 minutes x3 (add to albuterol in first hour only) |
| Systemic steroids | Prednisone 40-60 mg PO OR methylprednisolone 125 mg IV | Give immediately; continue 3-7 days |
| Supplemental O2 | Titrate to SpO2 >=94% | Avoid hyperoxia |
| Magnesium sulfate IV | 2 g IV over 20 minutes | Indicated if severe/life-threatening (PEFR <50% after 1h treatment); bronchodilator mechanism via calcium antagonism |
| Heliox | 70% helium / 30% oxygen mixture | Consider if refractory; reduces airway resistance; only if SpO2 maintained on 30% O2 |
| Ketamine | 1-2 mg/kg IV bolus (induction); infusion 0.5-2 mg/kg/hr | Bronchodilator properties; useful in intubation |

**Intubation criteria:**
- Respiratory arrest or near-arrest
- Declining mental status
- Hypoxemia (PaO2 <60 mmHg) despite supplemental O2
- Hypercapnia (PaCO2 >=45-50 mmHg with respiratory acidosis and fatigue)
- Failure to respond to maximal medical therapy

**Ventilator strategy in intubated asthma:**
- Permissive hypercapnia: allow PaCO2 to rise (goal pH >=7.20) to avoid barotrauma
- Low RR (10-14 bpm), long expiratory time (I:E 1:3 to 1:5)
- Low tidal volume (6-8 mL/kg IBW)
- Auto-PEEP monitoring — disconnect from vent briefly to assess if breath stacking

---

## Pulmonary Embolism (PE)

### Diagnostic Algorithm

**Step 1: Clinical probability — Wells PE Score**

| Criterion | Points |
|---|---|
| Clinical signs/symptoms of DVT (leg swelling, pain with palpation) | 3 |
| Alternative diagnosis less likely than PE | 3 |
| Heart rate >100 bpm | 1.5 |
| Immobilization >=3 days or surgery in prior 4 weeks | 1.5 |
| Prior DVT or PE | 1.5 |
| Hemoptysis | 1 |
| Malignancy (treatment within 6 months or palliative) | 1 |

| Score | Probability |
|---|---|
| <2 | Low (~3%) |
| 2-6 | Moderate (~20%) |
| >6 | High (~67%) |

**Step 2: PERC Rule (for LOW pretest probability patients)**

If ALL 8 criteria negative, PE probability <2% — can discharge without further workup:
1. Age <50 years
2. HR <100 bpm
3. SpO2 >=95% on room air
4. No prior DVT or PE
5. No recent surgery or trauma (within 4 weeks)
6. No unilateral leg swelling
7. No hemoptysis
8. No exogenous estrogen use

**Step 3: D-dimer testing**

- Use only in LOW or MODERATE pretest probability
- Standard cutoff: 500 ng/mL (ELISA-based, high-sensitivity)
- Age-adjusted cutoff (if age >50): age x 10 ng/mL
  - Example: age 70 years — threshold = 700 ng/mL
  - ADJUST study validated this approach; increases specificity without reducing sensitivity
- Negative D-dimer + low/moderate probability: PE excluded — no imaging needed
- Positive D-dimer OR high pretest probability: proceed to CT pulmonary angiography (CT-PA)

**CT-PA interpretation:**
- Diagnostic if: filling defects in pulmonary arteries (central, lobar, segmental)
- CT signs of RV strain: RV/LV ratio >0.9, IVS bowing toward LV, contrast reflux into IVC
- Subsegmental PE: clinical significance uncertain; anticoagulation decision individualized

**V/Q scan:**
- Preferred if: CIN risk, contrast allergy, pregnancy, renal failure
- Results: normal (PE excluded), high probability (treat), low/intermediate (non-diagnostic — further workup)

---

### PE Severity Classification

| Class | Definition | Hemodynamics | RV Dysfunction | Management |
|---|---|---|---|---|
| Low risk | No hemodynamic compromise, no RV strain | Stable | No | Anticoagulation; consider outpatient |
| Submassive (intermediate) | Hemodynamically stable | Stable | Present (echo or biomarkers) | Anticoagulate; consider systemic lysis or CDT if deteriorating |
| Massive (high risk) | Hemodynamic instability | SBP <90 mmHg for >=15 min or vasopressors required | Present | Systemic thrombolytics (if no contraindication) or surgical embolectomy or CDT |

**Biomarkers in PE:**
- BNP/NT-proBNP: RV strain/pressure overload
- Troponin: RV myocardial injury
- Both elevated: high-risk submassive PE; consider PESI scoring for outpatient eligibility

---

### PE Treatment

**Anticoagulation — DOAC preferred for most hemodynamically stable PE:**

| Drug | Loading Dose | Maintenance Dose | Notes |
|---|---|---|---|
| Apixaban | 10 mg BID x7 days | 5 mg BID x6 months; then 2.5 mg BID for extended | AMPLIFY trial; no overlap with UFH needed |
| Rivaroxaban | 15 mg BID x21 days | 20 mg daily with evening meal | EINSTEIN-PE trial; no parenteral overlap needed |
| Dabigatran | N/A (requires 5-10 days parenteral first) | 150 mg BID | RE-COVER trial |
| Edoxaban | N/A (requires 5-10 days parenteral first) | 60 mg daily (30 mg if CrCl 15-50 or weight <=60 kg) | Hokusai-VTE trial |
| LMWH (enoxaparin) | 1 mg/kg SQ BID | Continue or bridge to warfarin | Preferred in pregnancy, active cancer |
| Warfarin | 5-10 mg PO day 1 | Adjust to INR 2-3 | Overlap with LMWH/UFH for >=5 days AND INR >=2 for >=24h |

**Duration of anticoagulation:**

| Scenario | Duration |
|---|---|
| Provoked PE (surgery, immobility, trauma) | 3 months |
| Unprovoked (first episode) | >=3 months; consider extended indefinitely |
| Unprovoked (second episode) | Indefinite |
| Active cancer | Indefinite (reassess with disease status); LMWH or DOAC (rivaroxaban, apixaban, edoxaban — HoT-VTE/CARAVAGGIO data) |
| Antiphospholipid syndrome | Indefinite, warfarin preferred (INR 2-3 or 2.5-3.5) |

**Systemic thrombolysis (Alteplase) for massive PE:**
- Dose: 100 mg IV over 2 hours (or 0.6 mg/kg over 15 min in cardiac arrest, max 50 mg)
- Indication: Massive PE with SBP <90 mmHg for >=15 min or shock, AND no absolute contraindications
- Contraindications: Same as stroke thrombolysis — prior ICH, recent surgery/trauma, active bleeding
- Post-thrombolysis: Resume UFH 2-3 hours after infusion (no bolus) once aPTT <80 sec

**Submassive PE management:**
- Anticoagulate with DOAC or parenteral agent
- Systemic thrombolysis NOT routinely recommended (PEITHO trial: reduced hemodynamic decompensation but increased major bleeding and ICH)
- Catheter-directed thrombolysis (CDT): Considered in patients deteriorating on anticoagulation who cannot receive systemic thrombolytics; reduces thrombus burden with lower bleeding risk
- Surgical embolectomy: If thrombolytics contraindicated and hemodynamics deteriorating

**IVC filter indications:**
- Absolute: PE or DVT with absolute contraindication to anticoagulation (e.g., active life-threatening hemorrhage)
- Consider: Recurrent VTE despite therapeutic anticoagulation; massive PE with inadequate cardiopulmonary reserve
- NOT routinely recommended as adjunct to anticoagulation
- Use retrievable filter when possible; retrieve when anticoagulation can be resumed

---

## Community-Acquired Pneumonia (CAP)

### CURB-65 Severity Score

| Criterion | Points |
|---|---|
| Confusion (new disorientation) | 1 |
| BUN >19 mg/dL (>7 mmol/L) | 1 |
| Respiratory Rate >=30 breaths/min | 1 |
| Blood pressure: SBP <90 mmHg OR DBP <=60 mmHg | 1 |
| Age >=65 years | 1 |

| Score | Mortality Risk | Recommendation |
|---|---|---|
| 0-1 | Low (<3%) | Outpatient treatment |
| 2 | Moderate (~9%) | Inpatient or closely supervised outpatient |
| 3-5 | High (15-40%) | Hospitalization; score >=4 or 5 — consider ICU |

### PORT/PSI Risk Class

The Pneumonia Severity Index assigns points for age, comorbidities, exam findings, and lab results. More complex than CURB-65 but validated for outpatient vs. inpatient decisions.

| PSI Class | Risk | 30-Day Mortality | Disposition |
|---|---|---|---|
| I | Minimal | 0.1-0.4% | Outpatient |
| II (score <=70) | Low | 0.6-0.7% | Outpatient |
| III (score 71-90) | Low-moderate | 0.9-2.8% | Outpatient or brief inpatient |
| IV (score 91-130) | Moderate | 8.2-9.3% | Inpatient |
| V (score >130) | High | 27-31% | Inpatient (ICU if severe) |

---

### CAP Antibiotic Regimens (IDSA/ATS 2019 Guidelines)

**Outpatient (no comorbidities, no risk factors for resistant organisms):**
- Amoxicillin 1g PO TID x5 days (preferred — low-cost, narrow spectrum) OR
- Doxycycline 100 mg PO BID x5 days OR
- Azithromycin 500 mg PO day 1, then 250 mg days 2-5 (use only if local pneumococcal resistance <25%)

**Outpatient (with comorbidities: COPD, DM, renal/liver disease, CHF, malignancy, asplenia, or recent antibiotic use):**
- Amoxicillin-clavulanate 875/125 mg BID + azithromycin 500 mg day 1 then 250 mg days 2-5 OR
- Respiratory fluoroquinolone monotherapy:
  - Levofloxacin 750 mg PO daily x5 days OR
  - Moxifloxacin 400 mg PO daily x5 days

**Inpatient — non-ICU (no Pseudomonas risk):**
- Beta-lactam + macrolide:
  - Ceftriaxone 1-2g IV daily + azithromycin 500 mg IV/PO daily x5 days OR
- Respiratory fluoroquinolone monotherapy:
  - Levofloxacin 750 mg IV/PO daily x5 days OR
  - Moxifloxacin 400 mg IV/PO daily x5 days

**Inpatient — ICU (severe CAP):**
- Beta-lactam + macrolide:
  - Ceftriaxone 2g IV daily + azithromycin 500 mg IV daily OR
- Beta-lactam + respiratory fluoroquinolone:
  - Ceftriaxone 2g IV daily + levofloxacin 750 mg IV daily OR
- If Pseudomonas risk (structural lung disease, recent antibiotics, bronchiectasis):
  - Anti-Pseudomonal beta-lactam (piperacillin-tazobactam 4.5g IV q6h OR cefepime 2g IV q8h) + ciprofloxacin 400 mg IV q8h

**MRSA CAP (risk factors: prior MRSA, severe necrotic/cavitary pneumonia, post-influenza pneumonia):**
- Add vancomycin (25-30 mg/kg/day divided q8-12h, target AUC/MIC 400-600) OR
- Linezolid 600 mg IV/PO q12h

**Typical duration:** 5 days for most CAP if clinically improving; extend to 7-10 days for severe CAP, bacteremia, or Legionella

---

### HAP / VAP (Hospital-Acquired and Ventilator-Associated Pneumonia)

**Definition:**
- HAP: Pneumonia occurring >=48 hours after hospital admission, not incubating at admission
- VAP: Pneumonia occurring >=48 hours after intubation

**Empiric therapy (cover Pseudomonas + MRSA):**
- Piperacillin-tazobactam 4.5g IV q6h (or cefepime 2g IV q8h or meropenem 1g IV q8h) PLUS
- Vancomycin (target AUC/MIC 400-600) OR linezolid 600 mg IV q12h
- Adjust to narrowest effective regimen based on culture results at 48-72 hours

---

# SEPSIS AND SEPTIC SHOCK

---

## Sepsis-3 Definitions (JAMA 2016)

| Term | Definition |
|---|---|
| Sepsis | Life-threatening organ dysfunction caused by a dysregulated host response to infection |
| Septic shock | Sepsis + vasopressor requirement to maintain MAP >=65 mmHg AND serum lactate >2 mmol/L despite adequate fluid resuscitation |

**Key distinction:** Sepsis requires organ dysfunction (not just infection + SIRS criteria, which is no longer the Sepsis-2 definition).

---

### SOFA Score (Sequential Organ Failure Assessment)

Used to quantify organ dysfunction. Increase in SOFA >=2 points from baseline = sepsis.

| System | Parameter | Score 0 | Score 1 | Score 2 | Score 3 | Score 4 |
|---|---|---|---|---|---|---|
| Respiratory | PaO2/FiO2 (mmHg) | >=400 | 300-399 | 200-299 | 100-199 | <100 |
| Coagulation | Platelets (x10^3/uL) | >=150 | 100-149 | 50-99 | 20-49 | <20 |
| Liver | Bilirubin (mg/dL) | <1.2 | 1.2-1.9 | 2.0-5.9 | 6.0-11.9 | >=12.0 |
| Cardiovascular | MAP or vasopressors | MAP >=70 | MAP <70 | Dopamine <=5 or Dobutamine | Dopamine 5.1-15 or Epi/Norepi <=0.1 | Dopamine >15 or Epi/Norepi >0.1 |
| Neurologic | GCS | 15 | 13-14 | 10-12 | 6-9 | <6 |
| Renal | Creatinine (mg/dL) or urine output | <1.2 | 1.2-1.9 | 2.0-3.4 | 3.5-4.9 or UO <500 mL/d | >=5.0 or UO <200 mL/d |

### qSOFA (Quick SOFA — Bedside Screening)

Use outside the ICU to identify patients at risk for poor outcomes. Two or more criteria = high suspicion for sepsis, trigger full SOFA assessment.

| Criterion | Threshold |
|---|---|
| Respiratory rate | >=22 breaths/min |
| Altered mental status | Glasgow Coma Scale <15 (any change from baseline) |
| Systolic blood pressure | <=100 mmHg |

Note: qSOFA is NOT a diagnostic criterion — it is a screening tool. Full SOFA score is required for Sepsis-3 diagnosis.

---

### Hour-1 Bundle (SSC 2018 / Surviving Sepsis Campaign)

Within 1 hour of sepsis recognition:

1. **Measure lactate** — obtain serum lactate; remeasure at 2 hours if initial >2 mmol/L
2. **Blood cultures** — obtain >=2 sets (aerobic + anaerobic) BEFORE antibiotics; do not delay antibiotics >45 minutes to obtain cultures
3. **Broad-spectrum antibiotics** — administer within 1 hour of recognition
4. **Crystalloid resuscitation** — 30 mL/kg IV crystalloid (normal saline or lactated Ringer's) for hypotension or lactate >=4 mmol/L; reassess after bolus
5. **Vasopressors** — start if MAP <65 mmHg during/after fluid resuscitation

**Reassessment at 3 hours and 6 hours:**
- Reassess volume status and tissue perfusion
- Remeasure lactate if initial >=2 mmol/L
- Document time of antibiotic administration

---

### Vasopressor Dosing in Septic Shock

| Vasopressor | Mechanism | Dose Range | Notes |
|---|---|---|---|
| Norepinephrine | Alpha-1 >> Beta-1 | 0.01-3 mcg/kg/min | FIRST-LINE vasopressor; titrate to MAP >=65 mmHg |
| Vasopressin | V1 receptor agonist | 0.03 U/min (fixed dose) | Add-on to norepinephrine (VASST trial); may reduce NE requirements; do not exceed 0.06 U/min |
| Epinephrine | Alpha + Beta-1 + Beta-2 | 0.01-1 mcg/kg/min | Second-line if inadequate response to NE + vasopressin; increases lactate (beta effect) — interpret cautiously |
| Phenylephrine | Pure alpha-1 agonist | 0.5-9 mcg/kg/min | Use when tachyarrhythmia limits norepinephrine; avoid in low CO states |
| Dopamine | Dose-dependent | 2-20 mcg/kg/min | No longer preferred; higher arrhythmia risk (SOAP-II trial); may use in bradycardia + septic shock |
| Dobutamine | Beta-1 agonist | 2-20 mcg/kg/min | Add for myocardial dysfunction/low CO despite adequate MAP; vasodilates — may need more vasopressor |

**Corticosteroids in refractory septic shock:**
- Hydrocortisone 200 mg/day IV (50 mg q6h or 200 mg continuous infusion) if shock not responding to fluids + vasopressors after 1-2 hours
- Add fludrocortisone 50 mcg PO daily if available (ADRENAL trial controversy)
- Duration: until vasopressor no longer needed; taper if used >3 days

---

### Empiric Antibiotics by Source in Sepsis

| Source | Common Organisms | Antibiotic Regimen |
|---|---|---|
| Pneumonia (CAP, severe) | Streptococcus pneumoniae, H. influenzae, Legionella, atypicals | Ceftriaxone 2g IV daily + azithromycin 500 mg IV daily (or + levofloxacin 750 mg IV daily) |
| HAP / Ventilator-associated | Pseudomonas, MRSA, Klebsiella | Piperacillin-tazobactam 4.5g IV q6h + vancomycin (AUC/MIC 400-600) |
| Abdominal (intra-abdominal abscess, perforation) | E. coli, Klebsiella, Bacteroides, Enterococcus | Piperacillin-tazobactam 4.5g IV q6h OR meropenem 1g IV q8h (if critically ill or high-risk ESBL); add vancomycin if Enterococcus suspected |
| Urinary tract (pyelonephritis, urosepsis) | E. coli, Klebsiella (ESBL possible) | Ceftriaxone 2g IV daily (low ESBL risk); ertapenem 1g IV daily (high ESBL risk or prior ESBL); piperacillin-tazobactam for Pseudomonas risk |
| Skin/soft tissue (SSTI, necrotizing fasciitis) | MRSA, Streptococcus, gram-negatives, anaerobes | Vancomycin (25-30 mg/kg/day) + piperacillin-tazobactam 4.5g IV q6h; add clindamycin 900 mg IV q8h for toxin-mediated disease (TSS, necrotizing fasciitis) |
| Unknown source / Critically ill | Broad coverage | Piperacillin-tazobactam 4.5g IV q6h (or meropenem) + vancomycin; deescalate based on culture data at 48-72h |
| Neutropenic fever | Pseudomonas, gram-negatives, Viridans strep | Cefepime 2g IV q8h or piperacillin-tazobactam 4.5g IV q6h; add vancomycin if hemodynamically unstable or MRSA suspected |

**Antibiotic stewardship:** Reassess at 24-48 hours with culture data. Deescalate to narrowest effective regimen. Target 7-10 days for most sources (shorter if clinical response rapid).

---

# RHEUMATOLOGY

---

## Rheumatoid Arthritis (RA)

### 2010 ACR/EULAR Classification Criteria

Required: >=1 joint with definite clinical synovitis unexplained by other diagnosis. Score >=6/10 = definite RA.

| Domain | Criteria | Score |
|---|---|---|
| **Joint involvement** | 1 medium-large joint | 0 |
| | 2-10 medium-large joints | 1 |
| | 1-3 small joints | 2 |
| | 4-10 small joints | 3 |
| | >10 joints (at least 1 small) | 5 |
| **Serology** | Negative RF AND negative anti-CCP | 0 |
| | Low-positive RF OR low-positive anti-CCP | 2 |
| | High-positive RF OR high-positive anti-CCP | 3 |
| **Acute-phase reactants** | Normal CRP AND normal ESR | 0 |
| | Abnormal CRP OR abnormal ESR | 1 |
| **Duration of symptoms** | <6 weeks | 0 |
| | >=6 weeks | 1 |

### Disease Activity: DAS28 Score

DAS28 (Disease Activity Score using 28 joints) calculated from: tender joint count (TJC28), swollen joint count (SJC28), ESR or CRP, and patient global assessment.

| DAS28 | Disease Activity |
|---|---|
| <2.6 | Remission |
| 2.6-3.2 | Low disease activity |
| 3.2-5.1 | Moderate disease activity |
| >5.1 | High disease activity |

---

### RA Treatment Strategy

**Target-to-treat (T2T):** Goal is remission or low disease activity; reassess every 1-3 months; change therapy if target not met within 6 months.

**Conventional synthetic DMARDs (csDMARDs):**

| Drug | Dose | Key Monitoring |
|---|---|---|
| Methotrexate (MTX) | Start 7.5-10 mg weekly PO/SQ; uptitrate to 20-25 mg/week | CBC, LFTs every 3 months; folate 1 mg daily to reduce toxicity; hold for significant renal impairment; absolute contraindication in pregnancy |
| Hydroxychloroquine (HCQ) | 200-400 mg daily; max 5 mg/kg/day (lean body weight) | Annual ophthalmology exam after 5 years (macular toxicity); GI effects |
| Sulfasalazine | 500 mg BID initially; uptitrate to 1000-1500 mg BID | CBC, LFTs; GI side effects; contraindicated in sulfa allergy |
| Leflunomide | 10-20 mg daily (optional 100 mg load x3 days) | LFTs; teratogenic; cholestyramine washout procedure if pregnancy planned |

**Combination csDMARD therapy:** MTX + HCQ + sulfasalazine (triple therapy) comparable to MTX + etanercept in 2-year outcomes (O'Dell trial).

**Biologic DMARDs (bDMARDs) — when csDMARDs fail:**

| Drug Class | Drugs | Dose | Key Notes |
|---|---|---|---|
| TNF inhibitors | Etanercept | 50 mg SQ weekly | Screen for latent TB (IGRA/TST) before initiating any biologic |
| | Adalimumab | 40 mg SQ q2 weeks | |
| | Infliximab | 3 mg/kg IV at 0, 2, 6 weeks, then q8 weeks | |
| | Certolizumab pegol | 400 mg SQ at 0, 2, 4 weeks; 200 mg q2 weeks | Safe in pregnancy (minimal placental transfer) |
| | Golimumab | 50 mg SQ monthly | |
| Anti-CD20 | Rituximab | 1000 mg IV x2 doses (2 weeks apart); repeat q6 months | Preferred if lymphoma history or concern for demyelination |
| CTLA4-Ig | Abatacept | 125 mg SQ weekly or IV monthly (weight-based) | Lower infection risk vs. TNFi; preferred in ILD |
| Anti-IL-6R | Tocilizumab | 162 mg SQ weekly or q2 weeks; IV 4-8 mg/kg q4 weeks | Can normalize CRP/ESR (mask infection); monitor LFTs, lipids |
| Anti-IL-6 | Sarilumab | 150-200 mg SQ q2 weeks | |

**JAK inhibitors (targeted synthetic DMARDs — tsDMARDs):**

| Drug | Dose | Notes |
|---|---|---|
| Tofacitinib | 5 mg BID (or 11 mg ER daily) | FDA warning: increased risk of serious CV events, malignancy, thrombosis in high-risk patients; screen for TB |
| Baricitinib | 2 mg daily | |
| Upadacitinib | 15 mg daily | |

---

## Systemic Lupus Erythematosus (SLE)

### 2019 EULAR/ACR Classification Criteria

Entry criterion: ANA >=1:80 titer on HEp-2 cells OR equivalent positive test.

Additional criteria weighted by points (score >=10 = SLE):

| Domain | Criterion | Weight |
|---|---|---|
| Constitutional | Fever | 2 |
| Hematologic | Leukopenia (<4000/uL) | 3 |
| | Thrombocytopenia (<100,000/uL) | 4 |
| | Autoimmune hemolysis | 4 |
| Neuropsychiatric | Delirium | 2 |
| | Psychosis | 3 |
| | Seizures | 5 |
| Mucocutaneous | Non-scarring alopecia | 2 |
| | Oral ulcers | 2 |
| | Subacute or discoid lupus | 4 |
| | Acute cutaneous lupus (malar rash) | 6 |
| Serosal | Pleural or pericardial effusion | 5 |
| | Acute pericarditis | 6 |
| Musculoskeletal | Joint involvement (synovitis or TTP >=2 joints) | 6 |
| Renal | Proteinuria >0.5g/24h | 4 |
| | Renal biopsy Class II or V lupus nephritis | 8 |
| | Renal biopsy Class III or IV lupus nephritis | 10 |
| Immunology | Anti-dsDNA OR anti-Sm antibody | 6 |
| | Antiphospholipid antibodies | 2 |
| | Low complement (C3 or C4) | 3 |
| | Low C3 AND low C4 | 4 |

**Key autoantibodies in SLE:**

| Antibody | Sensitivity | Specificity | Clinical Association |
|---|---|---|---|
| ANA | 95% | 57% | Screening test; not specific |
| Anti-dsDNA | 70% | 95% | Lupus nephritis; correlates with disease activity |
| Anti-Sm | 25% | 99% | Highly specific; no clinical correlation |
| Anti-Ro/SSA | 30% | Moderate | Neonatal lupus, subacute cutaneous lupus, Sjogren overlap |
| Anti-La/SSB | 15% | High | Neonatal lupus; Sjogren overlap |
| Anti-histone | 50-70% | Low (drug-induced lupus in isolation) | Drug-induced lupus (procainamide, hydralazine, INH) |
| Anti-phospholipid | 30-40% | Moderate | Antiphospholipid syndrome, thrombosis, pregnancy loss |

---

### SLE Treatment by Organ Involvement

**Universal:**
- Hydroxychloroquine (HCQ) 200-400 mg daily (max 5 mg/kg/day): ALL lupus patients unless contraindicated. Reduces flares, organ damage, and mortality.
- Sunscreen and sun avoidance
- Vitamin D supplementation
- Annual ophthalmology after 5 years on HCQ

**Mild to moderate (skin, musculoskeletal, constitutional):**
- NSAIDs (short-term for arthritis/serositis)
- Topical corticosteroids (skin)
- Low-dose prednisone (<10 mg/day)
- HCQ (baseline)
- Methotrexate or azathioprine as steroid-sparing agents

**Moderate to severe (nephritis, CNS, hematologic, myocarditis):**
- High-dose prednisone: 1 mg/kg/day (or methylprednisolone 500-1000 mg IV x3 days for severe flare)
- Mycophenolate mofetil (MMF): 2-3g/day — preferred for lupus nephritis Class III/IV induction and maintenance
- Cyclophosphamide: 500-1000 mg/m2 IV monthly x6 doses (NIH protocol) or Euro-Lupus low-dose: 500 mg IV q2 weeks x6 doses; used for severe nephritis, CNS lupus, pulmonary hemorrhage
- Azathioprine: 2 mg/kg/day — maintenance therapy; check TPMT before initiating

**Biologics:**
- Belimumab (anti-BLYS): 10 mg/kg IV monthly or 200 mg SQ weekly; approved for active SLE and active lupus nephritis; reduces flares and corticosteroid use
- Voclosporin: Combined with MMF for lupus nephritis Class III/IV
- Anifrolumab: Anti-interferon type I receptor; approved for moderate-to-severe SLE

---

## Gout

### Pathophysiology and Diagnosis

- Caused by monosodium urate (MSU) crystal deposition in joints due to sustained hyperuricemia (serum urate >6.8 mg/dL)
- Gold standard diagnosis: MSU crystals on polarized light microscopy (needle-shaped, negatively birefringent)
- Clinical diagnosis acceptable if classic presentation: podagra (first MTP joint), rapid onset, severe pain, erythema, and swelling

**Serum urate during acute attack may be normal** — do not use to rule out gout during acute flare.

### Acute Gout Management

| Drug | Dose | Duration | Notes |
|---|---|---|---|
| Colchicine | 1.2 mg PO immediately, then 0.6 mg 1 hour later; then 0.6 mg daily or BID for prophylaxis | Low-dose regimen preferred (AGREE trial); equally effective as high-dose with fewer GI side effects | Start within 36 hours of flare onset for maximal efficacy; reduce dose if CrCl <30 mL/min |
| Naproxen | 500 mg PO BID | 5-7 days | Preferred NSAID; avoid in CKD, GI disease, or CHF |
| Indomethacin | 50 mg PO TID | 5-7 days | Highly effective; higher GI/CNS side effects |
| Prednisone | 30-40 mg daily x3-5 days, taper over 7-10 days | — | Use if NSAIDs + colchicine contraindicated; avoid if uncontrolled DM |
| Triamcinolone | 20-40 mg intra-articular injection | — | Useful if monoarticular and accessible joint |

### Urate-Lowering Therapy (ULT)

**Indications for initiating ULT:**
- >=2 gout attacks per year
- Tophi (any)
- Chronic gouty arthropathy
- Uric acid nephrolithiasis
- Stage >=3 CKD with gout (urate >=8 mg/dL)

**Treatment target:** Serum urate <6 mg/dL (standard target); <5 mg/dL in patients with tophi.

**Wait to initiate ULT:** Traditionally started 2-4 weeks after acute flare resolves, though 2020 ACR guidelines suggest initiation during acute flare is acceptable if patient is initiated on flare prophylaxis.

**Flare prophylaxis during ULT initiation (first 3-6 months):** Colchicine 0.6 mg daily (or BID if tolerated) or low-dose NSAID.

**ULT drugs:**

| Drug | Starting Dose | Target Dose | Mechanism | Key Notes |
|---|---|---|---|---|
| Allopurinol | 50-100 mg daily | Uptitrate 50-100 mg every 2-4 weeks; max 800 mg/day (typical max 300-400 mg/day); adjust to achieve serum urate <6 mg/dL | Xanthine oxidase inhibitor | First-line; start low to reduce risk of allopurinol hypersensitivity syndrome (AHS); check HLA-B*5801 in Asian patients (Han Chinese, Korean, Thai) before initiating; reduce dose in CKD |
| Febuxostat | 40 mg daily | 80 mg daily if target not achieved | Xanthine oxidase inhibitor | Second-line; CV safety concern (CARES trial: increased CV mortality vs. allopurinol); use with caution in CV disease; avoid in patients taking azathioprine/6-MP |
| Probenecid | 250 mg BID x1 week, then 500 mg BID | Max 2g/day | Uricosuric (inhibits renal urate reabsorption) | Avoid if eGFR <30 or urate nephrolithiasis; drug interactions (penicillins, methotrexate); adequate hydration essential |
| Pegloticase (Krystexxa) | 8 mg IV q2 weeks | — | Recombinant uricase | Refractory gout only; normalizes urate rapidly; infusion reactions; premedicate with corticosteroids + antihistamines |
| Lesinurad + allopurinol (Duzallo) | Lesinurad 200 mg daily in combination | — | URAT1 inhibitor (uricosuric) + XO inhibitor | Add-on when allopurinol monotherapy insufficient; avoid if eGFR <45 |

---

# HEMATOLOGY

---

## Anemia — Differential Diagnosis by MCV

### Classification Framework

| Type | MCV | Key Causes |
|---|---|---|
| Microcytic | <80 fL | Iron deficiency anemia (IDA), thalassemia, anemia of chronic disease (some), sideroblastic anemia, lead poisoning |
| Normocytic | 80-100 fL | Anemia of chronic disease (most), hemolytic anemia, aplastic anemia, CKD anemia, acute blood loss, mixed deficiency (IDA + B12/folate) |
| Macrocytic | >100 fL | Megaloblastic: B12 deficiency, folate deficiency; Non-megaloblastic: medications (hydroxyurea, methotrexate, zidovudine), liver disease, hypothyroidism, reticulocytosis (hemolysis), MDS |

---

### Microcytic Anemia

**Iron Deficiency Anemia (IDA):**
- Most common anemia worldwide
- Lab findings: low MCV, low serum iron, low ferritin (<30 ng/mL; <12 ng/mL specific), low transferrin saturation (<16%), high TIBC, high serum transferrin receptor
- Note: ferritin is an acute-phase reactant — may be falsely normal or elevated with concurrent inflammation (ferritin <100 ng/mL + TSAT <20% suggests IDA in inflammatory states)

**Oral iron therapy:**
- Ferrous sulfate 325 mg PO TID (provides ~65 mg elemental iron per tablet) — gold standard, cheapest
- Ferrous gluconate 324 mg PO TID (~37 mg elemental iron)
- Ferrous fumarate 325 mg PO TID (~108 mg elemental iron)
- Take on empty stomach for best absorption; ascorbic acid (vitamin C 200 mg) enhances absorption; antacids, PPIs, calcium reduce absorption
- Expect 1-2 g/dL Hgb rise per 2-3 weeks of therapy; repletion of stores requires 3-6 months after Hgb normalizes

**IV iron therapy indications:**
- Intolerance or non-adherence to oral iron
- Malabsorption (IBD, celiac, post-gastric bypass)
- Ongoing blood loss exceeding oral replacement
- Pre-surgical optimization requiring rapid repletion
- CKD on dialysis (iron required with erythropoiesis-stimulating agents)

| IV Iron Formulation | Dose | Infusion Time | Notes |
|---|---|---|---|
| Ferric carboxymaltose (Injectafer) | 750 mg IV; may repeat after 7 days (max 1500 mg per course) | 15-30 minutes | Low infusion reaction risk; hypophosphatemia risk with repeated dosing |
| Low-molecular-weight iron dextran (INFeD) | Total dose infusion (TDI) based on weight and target Hgb; test dose 25 mg | Can give entire calculated dose in one infusion | Test dose required; anaphylaxis risk (rare); most flexible dosing |
| Iron sucrose (Venofer) | 200-300 mg per infusion; multiple infusions needed | 15-30 minutes per infusion | Very safe; requires multiple doses |
| Ferric gluconate (Ferrlecit) | 125 mg per infusion; multiple infusions needed | 60 minutes | Safe; multiple doses required |
| Ferumoxytol (Feraheme) | 510 mg IV, repeat at 3-8 days | 15 minutes | Risk of serious hypersensitivity; FDA mandates 30-min observation post-infusion |

**Thalassemia:**
- Alpha thal trait: microcytosis, mild anemia or no anemia; hemoglobin electrophoresis normal; dx by molecular testing
- Beta thal trait: microcytosis; Hgb A2 elevated (>3.5%) on electrophoresis
- Iron studies normal (IDA vs. thalassemia distinction)
- Do NOT treat thalassemia with iron unless concurrent IDA confirmed

---

### Macrocytic Anemia

**B12 (Cobalamin) Deficiency:**
- Causes: Pernicious anemia (anti-intrinsic factor antibodies), gastric bypass, atrophic gastritis, vegan diet, metformin use (blocks ileal absorption)
- Neurologic manifestations: subacute combined degeneration of spinal cord (posterior and lateral columns — paresthesias, ataxia, proprioception loss), dementia, psychiatric symptoms
- Lab: low B12 (<200 pg/mL), elevated MCV, hypersegmented neutrophils (>=5 lobes in >=1 PMN, or >=1 with 6+ lobes), elevated homocysteine AND methylmalonic acid (MMA)
- Treatment: Cyanocobalamin 1000 mcg IM daily x7 days, then weekly x4, then monthly; OR high-dose oral 1000-2000 mcg daily (effective even without intrinsic factor via passive absorption)

**Folate Deficiency:**
- Causes: Malnutrition, alcohol use disorder, malabsorption, increased demand (pregnancy, hemolytic anemia), drugs (MTX, phenytoin, trimethoprim)
- Lab: low serum folate, elevated homocysteine (MMA normal — distinguishes from B12 deficiency), hypersegmented neutrophils
- Treatment: Folic acid 1-5 mg PO daily x3-4 months; treat underlying cause
- Important: Correct B12 before or with folate if B12 status uncertain — folate alone can mask hematologic B12 deficiency while neurologic damage progresses

---

## DVT/PE Anticoagulation — Dosing and Duration

### Full Anticoagulation Dosing Table

| Drug | VTE Treatment Dose | Prophylactic Dose | Renal Adjustment |
|---|---|---|---|
| Enoxaparin | 1 mg/kg SQ BID OR 1.5 mg/kg SQ once daily (for DVT) | 40 mg SQ daily | Reduce therapeutic dose to 1 mg/kg SQ daily if CrCl <30 mL/min; monitor anti-Xa levels |
| Fondaparinux | 5 mg (weight <50kg), 7.5 mg (50-100kg), 10 mg (>100kg) SQ daily | 2.5 mg SQ daily | Avoid if CrCl <30 mL/min |
| UFH | 80 U/kg IV bolus, then 18 U/kg/hr infusion; titrate to aPTT 60-100 sec | 5000 U SQ q8-12h | No adjustment; preferred in severe CKD |
| Apixaban | 10 mg PO BID x7 days, then 5 mg PO BID | 2.5 mg PO BID | Avoid if CrCl <25 mL/min |
| Rivaroxaban | 15 mg PO BID x21 days, then 20 mg daily with evening meal | 10 mg daily | Avoid if CrCl <15 mL/min; use with caution 15-30 mL/min |
| Dabigatran | After >=5-10 days parenteral: 150 mg BID | 110 mg BID (after surgery) | Contraindicated if CrCl <30 mL/min (VTE indication) |
| Edoxaban | After >=5-10 days parenteral: 60 mg daily (30 mg if CrCl 15-50 or weight <=60 kg) | — | Avoid if CrCl <15 mL/min |
| Warfarin | 5-10 mg day 1; adjust to INR 2-3 (overlap parenteral anticoagulation >=5 days and INR >=2 for 24h) | — | No renal adjustment needed |

---

### Anticoagulation Reversal Agents

| Drug | Reversal Agent | Dose | Onset |
|---|---|---|---|
| Warfarin | 4-Factor PCC (Kcentra) | 25-50 U/kg IV based on INR and weight | Minutes; immediate INR correction |
| Warfarin | Vitamin K1 (Phytonadione) | 5-10 mg IV (slow infusion, anaphylaxis risk) or PO 2.5-5 mg | IV: 4-6 hours; PO: 12-24 hours |
| Dabigatran | Idarucizumab (Praxbind) | 5g IV (two 2.5g boluses within 15 min) | Minutes |
| Apixaban / Rivaroxaban / Edoxaban | Andexanet alfa (Andexxa) | Low dose: 400 mg IV bolus at 30 mg/min, then 480 mg over 2h; High dose: 800 mg IV bolus, then 960 mg over 2h | Minutes; use low dose if last rivaroxaban dose <=8h <10mg; apixaban <=8h <5mg; use high dose otherwise |
| UFH | Protamine sulfate | 1 mg per 100 U of UFH given in prior 2 hours (max 50 mg); give slowly over 10 min | Minutes; risk of hypotension/bradycardia |
| LMWH | Protamine sulfate | 1 mg per 1 mg enoxaparin given in prior 8 hours (provides ~60-75% reversal) | Partial reversal |

**4F-PCC dosing by INR (Kcentra):**

| INR | Dose (U/kg body weight) | Max dose |
|---|---|---|
| 2-3.9 | 25 U/kg | 2500 U |
| 4-6 | 35 U/kg | 3500 U |
| >6 | 50 U/kg | 5000 U |

---

# NEUROLOGY

---

## Ischemic Stroke

### NIHSS (National Institutes of Health Stroke Scale)

The NIHSS is an 11-item scale used to quantify stroke severity and guide treatment decisions.

| Domain | Score Range | Key Items |
|---|---|---|
| Level of consciousness | 0-3 | Alertness, questions, commands |
| Gaze | 0-2 | Horizontal eye movement |
| Visual fields | 0-3 | Visual field cut |
| Facial palsy | 0-3 | Asymmetry |
| Motor arm (left/right) | 0-4 each | Drift/resistance against gravity |
| Motor leg (left/right) | 0-4 each | Drift/resistance against gravity |
| Limb ataxia | 0-2 | Finger-nose, heel-shin |
| Sensory | 0-2 | Pinprick |
| Language/Aphasia | 0-3 | Naming, reading, description |
| Dysarthria | 0-2 | Articulation |
| Extinction/Inattention | 0-2 | Neglect |
| **Maximum score** | **42** | |

| NIHSS Score | Severity |
|---|---|
| 0 | No stroke symptoms |
| 1-4 | Minor stroke |
| 5-15 | Moderate stroke |
| 15-20 | Moderate to severe |
| >20 | Severe stroke |

---

### IV tPA (Alteplase) — Eligibility and Dosing

**Standard 3-hour window criteria (FDA-approved):**
- Age >=18 years
- Clinical diagnosis of ischemic stroke with measurable neurologic deficit
- Onset of symptoms <3 hours before treatment initiation (or last known well time)
- CT head negative for intracranial hemorrhage

**Extended 3-4.5-hour window (AHA/ASA Class I recommendation, 2019 guidelines):**
Additional eligibility criteria (on top of 3h criteria):
- No combination of: age >80 AND NIHSS >25 AND history of both DM and prior stroke AND oral anticoagulant use (regardless of INR)

**Dosing:**
- Alteplase: 0.9 mg/kg IV; max dose 90 mg
- Give 10% of total dose as IV bolus over 1 minute
- Remaining 90% infused over 60 minutes
- Do NOT give antiplatelet or anticoagulant agents for 24 hours after tPA

**Absolute contraindications to IV tPA:**

| Category | Contraindication |
|---|---|
| Imaging | CT showing intracranial hemorrhage |
| | Large established infarct (>1/3 MCA territory hypodensity) |
| Bleeding risk | Any prior intracranial hemorrhage |
| | Active internal bleeding (excluding menses) |
| | Known intracranial AVM, tumor, or aneurysm |
| | Intracranial or intraspinal surgery within 3 months |
| Vascular | Suspected aortic dissection |
| Coagulopathy | INR >1.7 |
| | aPTT >40 sec |
| | Platelet count <100,000/uL |
| | DOAC use within 48 hours (or with detectable drug levels) |
| Metabolic | Serum glucose <50 mg/dL or >400 mg/dL (correct and reassess) |
| Blood pressure | SBP >185 mmHg or DBP >110 mmHg (can treat to lower and then proceed) |
| Recent procedures | Serious head trauma within 3 months |
| | GI or urinary tract hemorrhage within 21 days |
| | Arterial puncture at non-compressible site within 7 days |
| | Major surgery within 14 days |

**Relative contraindications (risk-benefit decision):**
- Minor or rapidly improving stroke (NIHSS 1-3): may withhold if deficit likely to resolve; PRISMS trial suggests tPA benefit even in mild strokes
- Recent MI: STEMI within 3 months — generally avoid; STEMI >3 months with stabilized cardiac status may be acceptable

**Blood pressure management peri-tPA:**
- Before tPA: Lower BP to <=185/110 mmHg before administering (use labetalol 10-20 mg IV or nicardipine infusion)
- After tPA: Maintain BP <180/105 mmHg for >=24 hours

---

### Mechanical Thrombectomy (Endovascular Treatment)

**Indications (AHA/ASA 2019 Class I):**
- Proximal LVO: ICA, M1, M2 segment of MCA, basilar artery
- Age >=18 years
- Pre-stroke mRS 0-1 (functional independence)
- ASPECTS >=6 (Alberta Stroke Program Early CT Score) — indicates limited early infarct volume
- IVtPA eligible: receive tPA AND transfer to thrombectomy (does not replace tPA)
- Time window: 0-6 hours from symptom onset (Class I)
- Extended window: 6-24 hours if DAWN (DWI/CTP mismatch) or DEFUSE-3 criteria met (penumbral imaging showing viable tissue at risk)

---

### TIA — Workup and Risk Assessment

**ABCD2 Score for short-term stroke risk after TIA:**

| Criterion | Score |
|---|---|
| **A** — Age >=60 years | 1 |
| **B** — BP: SBP >=140 mmHg or DBP >=90 mmHg | 1 |
| **C** — Clinical features: unilateral weakness (2) or speech disturbance without weakness (1) | 0-2 |
| **D** — Duration: >=60 min (2), 10-59 min (1), <10 min (0) | 0-2 |
| **D** — Diabetes | 1 |

| Score | 2-Day Stroke Risk |
|---|---|
| 0-3 | Low (~1%) |
| 4-5 | Moderate (~4%) |
| 6-7 | High (~8%) |

**TIA Workup (complete within 24-48 hours):**
- Brain MRI with DWI (detect acute ischemia — positive in ~30-50% of clinical TIA)
- Vascular imaging: CT angiography or MRA of head and neck (detect carotid stenosis, LVO)
- Cardiac evaluation: 12-lead ECG immediately; continuous cardiac monitoring x24-72 hours (for paroxysmal AF detection); echocardiogram (TTE or TEE)
- Lab work: CBC, BMP, LFTs, fasting lipids, HgbA1c, coagulation studies
- Prolonged cardiac monitoring: 30-day event monitor or implantable loop recorder if etiology unclear (cryptogenic TIA)

**Carotid imaging and revascularization:**
- Ipsilateral carotid stenosis 50-99% in symptomatic patient: carotid endarterectomy (CEA) or carotid artery stenting (CAS) within 2 weeks of index event (greatest benefit)

---

### Secondary Stroke Prevention

**Antiplatelet therapy:**

| Scenario | Regimen | Duration |
|---|---|---|
| Minor ischemic stroke (NIHSS <=3) or high-risk TIA (ABCD2 >=4) — non-cardioembolic | Aspirin 325 mg + clopidogrel 300 mg load, then aspirin 75-100 mg + clopidogrel 75 mg dual therapy (CHANCE/POINT trials) | Dual antiplatelet x21 days, then aspirin monotherapy indefinitely |
| Moderate-severe ischemic stroke — non-cardioembolic | Aspirin 81-325 mg daily | Indefinitely |
| Aspirin failure or intolerance | Clopidogrel 75 mg daily OR aspirin + extended-release dipyridamole 25/200 mg BID | Indefinitely |

**Anticoagulation — cardioembolic stroke:**
- AF: Start DOAC 4-14 days after stroke (timing depends on infarct size and hemorrhagic transformation risk); apixaban, rivaroxaban, dabigatran, or edoxaban preferred over warfarin
- LA thrombus: Anticoagulate; TEE to confirm resolution before converting to antiplatelet
- PFO with cryptogenic stroke age <60: PFO closure superior to antiplatelet alone (CLOSE, REDUCE, RESPECT trials); post-closure antiplatelet therapy
- Mechanical heart valve: Warfarin (INR 2.5-3.5 for mitral prosthesis; 2-3 for aortic prosthesis); DOACs contraindicated

**Statin therapy (all ischemic stroke/TIA):**
- High-intensity statin: atorvastatin 40-80 mg daily or rosuvastatin 20-40 mg daily
- Target LDL <70 mg/dL (or <55 mg/dL in very high-risk/recent event)
- SPARCL trial: atorvastatin 80 mg daily reduced stroke recurrence by 16%

**Blood pressure control:**
- Target: SBP <130 mmHg (for most patients after acute phase)
- Begin or resume antihypertensives >24 hours after acute ischemic stroke if BP elevated
- ACEi + thiazide combination (PROGRESS trial) reduces recurrent stroke risk

---

## Appendix: Key Drug Reference Tables

### Common Antibiotics — Dosing Reference

| Drug | Typical Adult Dose | Renal Adjustment |
|---|---|---|
| Ceftriaxone | 1-2g IV q12-24h | Minimal adjustment needed |
| Cefepime | 1-2g IV q8-12h | Reduce if CrCl <60 mL/min |
| Piperacillin-tazobactam | 3.375-4.5g IV q6h (or 3.375g q8h extended infusion) | Reduce if CrCl <40 mL/min |
| Meropenem | 500 mg - 2g IV q8h | Reduce if CrCl <50 mL/min |
| Vancomycin | 15-20 mg/kg IV q8-12h; target AUC/MIC 400-600 | Dose interval extends in CKD; check AUC |
| Linezolid | 600 mg IV/PO q12h | No adjustment |
| Azithromycin | 500 mg IV/PO daily | No adjustment |
| Levofloxacin | 750 mg IV/PO daily | Reduce dose/frequency if CrCl <50 mL/min |
| Moxifloxacin | 400 mg IV/PO daily | No renal adjustment |
| Metronidazole | 500 mg IV/PO q8h | No renal adjustment; reduce in severe hepatic disease |
| Doxycycline | 100 mg PO/IV BID | No adjustment |
| Clindamycin | 600-900 mg IV q8h; 300-450 mg PO q6h | No adjustment |
| Ciprofloxacin | 400 mg IV q12h; 500-750 mg PO BID | Reduce if CrCl <30 mL/min |

---

### Common Cardiovascular Drugs — Quick Reference

| Drug | Class | Typical Dose | Key Monitoring |
|---|---|---|---|
| Lisinopril | ACEi | 2.5-40 mg daily | K+, Cr, BP; cough (switch to ARB) |
| Losartan | ARB | 25-150 mg daily | K+, Cr, BP |
| Sacubitril-valsartan | ARNI | 24/26 - 97/103 mg BID | K+, Cr, BP; do not combine with ACEi |
| Carvedilol | BB (alpha+beta) | 3.125-25 mg BID | HR, BP; take with food |
| Metoprolol succinate | BB (beta-1 selective) | 12.5-200 mg daily | HR, BP |
| Spironolactone | MRA | 12.5-50 mg daily | K+, Cr (especially with ACEi/ARB) |
| Furosemide | Loop diuretic | 20-240 mg PO/IV daily-BID | K+, Na+, Cr, volume status |
| Atorvastatin | Statin (high-intensity) | 40-80 mg daily | LFTs at baseline; CK if myalgia |
| Rosuvastatin | Statin (high-intensity) | 20-40 mg daily | LFTs at baseline |
| Aspirin | Antiplatelet | 81-325 mg daily | GI bleeding; renal |
| Clopidogrel | P2Y12 inhibitor | 75 mg daily (600 mg load) | Bleeding; CYP2C19 variant affects metabolism |
| Ticagrelor | P2Y12 inhibitor | 90 mg BID (180 mg load) | Dyspnea (benign); bleeding; do not use with high-dose aspirin |
| Amiodarone | Antiarrhythmic | 200 mg daily (PO); various IV protocols | TFTs, PFTs, LFTs, ophthalmology q6-12 months; huge drug interactions (warfarin, digoxin, statins) |
| Digoxin | Cardiac glycoside | 0.125-0.25 mg daily | Digoxin level (target 0.5-0.9 ng/mL); K+, Mg2+, Cr |
| Warfarin | Anticoagulant | Individualized | INR (target 2-3 for most indications); numerous drug/food interactions |

---

*End of document.*
