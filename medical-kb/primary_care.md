# Primary Care Medical Knowledge Base

**Scope:** Evidence-based clinical guidelines for primary care practice  
**Sources:** USPSTF, ACC/AHA, JNC8, ADA, AAFP, ACOG, CDC, Rome IV  
**Last updated:** 2026  
**Intended use:** Open WebUI RAG system (chunk size 1500, overlap 200)

---

## Preventive Medicine and Screening

### USPSTF Screening Guidelines — Adults

| Condition | Population | Test | Frequency | Grade |
|-----------|-----------|------|-----------|-------|
| Breast cancer | Women 40–74 | Mammography | Every 2 years (40–49: individualize) | B |
| Cervical cancer | Women 21–65 | Pap smear alone | Every 3 years (21–29) | A |
| Cervical cancer | Women 30–65 | Pap + HPV co-test | Every 5 years | A |
| Colorectal cancer | Adults 45–75 | Colonoscopy, FIT, CT colonography, stool DNA | Various (colonoscopy q10y; FIT annually) | A/B |
| Lung cancer | Adults 50–80, 20 pack-year history, current or quit <15 yrs | Low-dose CT chest | Annually | B |
| Prostate cancer | Men 55–69 | PSA (shared decision-making) | Individualize | C |
| Skin cancer (melanoma) | General adult | Visual exam | Not routinely recommended | I |
| Ovarian cancer | General women | Ultrasound + CA-125 | Not recommended | D |
| Pancreatic cancer | General adult | Screening | Not recommended | D |
| Hypertension | Adults 18+ | Office BP measurement | Every visit or annually if normal | A |
| Type 2 diabetes | Adults 35–70, overweight/obese | Fasting glucose or HbA1c | Every 3 years | B |
| Prediabetes | Adults 35–70, overweight | HbA1c or fasting glucose | Every 3 years | B |
| Lipid disorders (CVD) | Men 35+, women 45+ at average risk | Fasting lipid panel | Every 5 years | A/B |
| Abdominal aortic aneurysm | Men 65–75, ever-smokers | One-time ultrasound | Once | B |
| Osteoporosis | Women 65+; younger postmenopausal women at elevated risk | DEXA bone density scan | Every 2 years if normal | B |
| Depression | Adults 18+ | PHQ-2/PHQ-9 | Annually | B |
| Anxiety | Adults 18–64 | GAD-7 | When indicated | B |
| HIV | Adults 15–65 | HIV-1/2 antigen/antibody | At least once; repeat if at risk | A |
| Syphilis | Adults at increased risk | RPR or VDRL | Annually if high risk | A |
| Gonorrhea/chlamydia | Sexually active women 24 and younger; older women at risk | NAAT | Annually | B |
| Hepatitis C | Adults born 1945–1965; adults 18–79 | Anti-HCV antibody | Once for birth cohort; at-risk more often | B |
| Hepatitis B | Adults at risk | HBsAg | When indicated | B |
| Tuberculosis | Persons at increased risk | TST or IGRA | When indicated | B |
| Obesity | Adults 18+ | BMI calculation | At every visit | B |
| Tobacco use | All adults | Ask + advise | Every visit | A |
| Unhealthy alcohol use | Adults 18+ | AUDIT-C | Annually | B |
| Intimate partner violence | Women of reproductive age | Screening tool | Annually | B |
| Cognitive impairment | Adults 65+ | Clinician judgment (no universal USPSTF rec) | I | I |

### Cancer Screening — High-Risk Modifications

- Familial adenomatous polyposis (FAP): colonoscopy starting age 10–12, annually
- Lynch syndrome: colonoscopy every 1–2 years starting age 20–25
- BRCA1/2 mutation carriers: annual mammography + MRI starting age 25–30
- Personal history of breast cancer: annual mammography starting after treatment
- Barrett's esophagus: EGD every 3–5 years (dysplasia-free)
- First-degree relative with CRC: colonoscopy at age 40 or 10 years before relative's diagnosis (whichever earlier), every 5 years

---

### Adult Immunization Schedule

| Vaccine | Recommended Population | Dose / Schedule | Notes |
|---------|----------------------|----------------|-------|
| Influenza (IIV4 or RIV4) | All adults annually | 1 dose each fall | Live attenuated (LAIV) for healthy non-pregnant 18–49 |
| Tdap | All adults (if never received) | 1 dose, then Td q10 yrs | Give in pregnancy 27–36 weeks regardless of prior history |
| Td booster | All adults | 1 dose every 10 years | Or Tdap if never given |
| COVID-19 (mRNA) | All adults | Updated formulation annually | Immunocompromised: additional doses per ACIP guidance |
| Zoster (RZV, Shingrix) | Adults 50+; immunocompromised 19+ | 2 doses, 2–6 months apart | Preferred over ZVL; give even if prior zoster or ZVL |
| PCV15 + PPSV23 | Adults 65+; high-risk adults 19–64 | PCV15 followed by PPSV23 1 year later | OR PCV20 alone (1 dose) for adults 65+ |
| PCV20 | Adults 65+ | 1 dose | If no prior PCV or PPSV23 |
| Hepatitis A (HepA) | At-risk adults; universal catch-up | 2 doses (Havrix) or 3 doses (Twinrix) | Risk: travel, liver disease, MSM, IVDU, unhoused |
| Hepatitis B (HepB) | Adults 19–59 (universal); 60+ as needed | 3-dose series (0, 1, 6 months) or 2-dose Heplisav-B (0, 1 month) | Check anti-HBs 1–2 months post-series in immunocompromised |
| HPV (9vHPV, Gardasil 9) | All persons through age 26; shared decision 27–45 | 2-dose (9–14 yrs, 0, 6–12 months) or 3-dose (15+, 0, 2, 6 months) | Vaccination does not replace cervical screening |
| MMR | Adults born after 1957 without documented immunity | 1–2 doses | Contraindicated in pregnancy; 2 doses for healthcare workers, international travelers, students |
| Varicella (VAR) | Adults without documented immunity | 2 doses, 4–8 weeks apart | Contraindicated in pregnancy and severe immunosuppression |
| Meningococcal (MenACWY) | Adults at risk (asplenia, complement deficiency, college freshmen in dorms, travelers to endemic areas) | 1–2 doses; boost every 5 years if ongoing risk | — |
| MenB | Adults at risk (asplenia, complement deficiency, outbreak) | 2–3 doses (brand-dependent) | 16–23 yrs: shared decision |

---

### Well-Visit Components by Age Group

#### Ages 18–39
- Complete history and physical examination
- BMI measurement; counseling if overweight/obese
- Blood pressure measurement
- Fasting lipid panel (if risk factors present or per clinical judgment)
- Diabetes screening if BMI > 25 and risk factors
- Tobacco, alcohol, and substance use screening
- Depression and anxiety screening (PHQ-9, GAD-7)
- Reproductive health: contraception counseling, STI screening if indicated
- Immunization review and update
- Skin exam counseling for sun protection
- Safety counseling (seatbelts, firearms, domestic violence)

#### Ages 40–64
- All of the above
- Fasting lipid panel every 5 years (more often if abnormal)
- Diabetes screening every 3 years (BMI > 25)
- Colorectal cancer screening beginning at age 45
- Lung cancer CT if smoking history criteria met (age 50+)
- Mammography discussion beginning at age 40; strongly recommended by 50
- Cervical cancer screening (Pap/HPV co-test every 5 years through age 65)
- Bone density in women approaching menopause if risk factors
- Hearing and vision assessment
- Consider ASCVD risk calculation and statin discussion

#### Ages 65 and Older
- All of the above
- DEXA scan (women 65+)
- Abdominal aortic aneurysm one-time ultrasound (men 65–75, ever-smokers)
- Cognitive and functional assessment
- Fall risk assessment: Timed Up and Go (TUG) test
- Depression screening with attention to somatic symptoms
- Polypharmacy review; consider Beer's Criteria medications
- Advance care planning discussion
- Prostate cancer discussion (men 55–69 with life expectancy > 10 years)
- PCV20 or PCV15/PPSV23 series
- Zoster vaccine (Shingrix 2-dose series)
- Annual influenza vaccine

---

## Hypertension

### Blood Pressure Classification — 2017 ACC/AHA

| Category | Systolic (mmHg) | Diastolic (mmHg) |
|----------|----------------|-----------------|
| Normal | < 120 | and < 80 |
| Elevated | 120–129 | and < 80 |
| Stage 1 Hypertension | 130–139 | or 80–89 |
| Stage 2 Hypertension | >= 140 | or >= 90 |
| Hypertensive Crisis | > 180 | and/or > 120 |

> Clinical Pearl: The 2017 ACC/AHA guidelines lowered the threshold for Stage 1 HTN to 130/80. JNC8 (2014) still used 140/90 as the treatment threshold for most adults. Many clinicians and health systems blend both. Always confirm with at least 2 readings on 2 separate visits before diagnosing HTN.

### JNC8 Treatment Thresholds (2014)

| Population | Initiate Drug Therapy at | BP Target |
|-----------|------------------------|-----------|
| General population < 60 years | >= 140/90 | < 140/90 |
| General population >= 60 years | >= 150/90 | < 150/90 |
| Diabetes (all ages) | >= 140/90 | < 140/90 |
| CKD (all ages) | >= 140/90 | < 140/90 |

### ACC/AHA 2017 BP Targets

| Population | Target BP |
|-----------|-----------|
| General adults with confirmed HTN | < 130/80 |
| Adults >= 65 with HTN (community-dwelling) | < 130/80 |
| High CVD risk (ASCVD >= 10%) | < 130/80 |
| Diabetes mellitus | < 130/80 |
| CKD (with or without proteinuria) | < 130/80 |
| CKD with proteinuria > 1g/day | < 125/75 (some guidelines) |
| Heart failure with reduced EF | < 130/80 |
| Older frail adults | Individualize; avoid SBP < 110 |

### First-Line Antihypertensive Drug Classes

#### Thiazide Diuretics
- **Agents:** Hydrochlorothiazide (HCTZ), chlorthalidone (preferred), indapamide
- **Mechanism:** Inhibit NaCl cotransporter in distal convoluted tubule; initially reduce plasma volume, then reduce peripheral vascular resistance
- **Dosing:** Chlorthalidone 12.5–25 mg daily; HCTZ 12.5–50 mg daily
- **Indications:** First-line for most patients; especially effective in Black patients
- **Contraindications:** Gout (relative), severe hyponatremia, sulfonamide allergy (relative)
- **Side effects:** Hypokalemia, hyponatremia, hyperuricemia, hyperglycemia, hyperlipidemia (minor), hypomagnesemia
- **Monitor:** BMP at 4–6 weeks after initiation

#### ACE Inhibitors (ACEi)
- **Agents:** Lisinopril, enalapril, ramipril, benazepril, perindopril
- **Mechanism:** Block conversion of angiotensin I to angiotensin II; reduce aldosterone; reduce preload and afterload
- **Dosing:** Lisinopril 10–40 mg daily; enalapril 5–40 mg daily
- **Indications:** First-line; especially preferred in CKD with proteinuria, diabetes, heart failure, post-MI
- **Contraindications:** Pregnancy (teratogenic — category X), bilateral renal artery stenosis, prior angioedema from ACEi, hyperkalemia
- **Side effects:** Dry cough (10–15%), angioedema (0.1–0.7%), hyperkalemia, acute kidney injury (especially with dehydration or NSAIDs), teratogenicity
- **Monitor:** BMP at 1–2 weeks; hold if creatinine rises > 30% from baseline

#### Angiotensin Receptor Blockers (ARBs)
- **Agents:** Losartan, valsartan, irbesartan, olmesartan, candesartan, telmisartan
- **Mechanism:** Block angiotensin II at AT1 receptor; similar effects to ACEi without bradykinin accumulation (hence no cough)
- **Dosing:** Losartan 50–100 mg daily; valsartan 80–320 mg daily
- **Indications:** First-line; preferred when ACEi cough is intolerable; CKD, diabetes, heart failure
- **Contraindications:** Pregnancy, bilateral renal artery stenosis, prior angioedema from ARB (note: ACEi angioedema is NOT a contraindication — different mechanism, low cross-reactivity)
- **Side effects:** Hyperkalemia, renal impairment, dizziness; no cough
- **Do not combine** ACEi + ARB (increased risk of hyperkalemia, renal failure without added BP benefit — ONTARGET trial)

#### Calcium Channel Blockers (CCBs)
- **Agents — Dihydropyridines (DHPs):** Amlodipine (preferred for HTN), nifedipine XL, felodipine
- **Agents — Non-DHPs:** Diltiazem, verapamil (more cardiac than vascular)
- **Mechanism:** DHPs: block L-type Ca2+ channels in vascular smooth muscle causing vasodilation; Non-DHPs: also suppress SA/AV node
- **Dosing:** Amlodipine 2.5–10 mg daily; diltiazem ER 120–540 mg daily
- **Indications:** First-line; especially in Black patients (guideline-preferred); elderly patients; angina
- **Contraindications:** Non-DHPs: heart failure with reduced EF, significant bradycardia, heart block, Wolff-Parkinson-White syndrome
- **Side effects:** DHPs: peripheral edema, flushing, reflex tachycardia; Non-DHPs: bradycardia, constipation, heart block

### Resistant Hypertension

**Definition:** BP above goal despite concurrent use of 3 antihypertensive agents at optimal doses (including a diuretic), or BP controlled only on 4 or more agents.

**Workup for Resistant HTN:**
1. Confirm true resistance (rule out white-coat HTN with ambulatory BP monitoring)
2. Assess medication adherence (directly observed therapy, pill counts, pharmacy refill history)
3. Rule out contributing medications: NSAIDs, decongestants, OCPs, stimulants, chronic steroid use, licorice, cocaine
4. Screen for secondary causes:
   - Renal artery stenosis: renal Doppler ultrasound or CT angiography
   - Primary hyperaldosteronism: plasma aldosterone-to-renin ratio (PAC/PRA; positive if > 30 with aldosterone > 15 ng/dL)
   - Obstructive sleep apnea: Epworth scale, polysomnography
   - Pheochromocytoma: 24-hour urine catecholamines and metanephrines, or plasma metanephrines
   - Cushing's syndrome: 24-hour urine free cortisol, late-night salivary cortisol
   - Hypothyroidism/hyperthyroidism: TSH
   - Chronic kidney disease: eGFR, urine albumin-to-creatinine ratio

**Additional agents for resistant HTN:** Spironolactone 25–50 mg daily (especially if hyperaldosteronism or low-renin HTN); clonidine; hydralazine; minoxidil; direct renin inhibitors (aliskiren)

### Hypertensive Urgency vs Emergency

| Feature | Urgency | Emergency (Crisis) |
|---------|---------|-------------------|
| BP level | SBP > 180 or DBP > 120 | SBP > 180 or DBP > 120 |
| End-organ damage | Absent | Present |
| Examples of end-organ damage | N/A | Encephalopathy, intracranial hemorrhage, ACS, acute pulmonary edema, aortic dissection, hypertensive nephropathy, eclampsia |
| Symptoms | Headache, anxiety (non-focal) | Chest pain, neurologic deficits, dyspnea, altered mental status, visual changes |
| Management | Oral antihypertensives, reduce BP over 24–48 hours, no rapid correction | IV medications (labetalol, nicardipine, hydralazine, nitroprusside); ICU admission; target 25% reduction in first hour |
| Setting | Can manage outpatient | Emergency department + ICU |

> Clinical Pearl: In hypertensive urgency, do NOT rapidly lower BP to normal in hours — abrupt decreases can cause cerebral hypoperfusion, especially in chronically hypertensive patients who have reset their cerebrovascular autoregulation.

---

## Hyperlipidemia

### ASCVD Risk Calculation

Use the Pooled Cohort Equations (PCE) to estimate 10-year atherosclerotic cardiovascular disease risk (ACC/AHA 2013).

**Inputs:** Age, sex, race, total cholesterol, HDL, systolic BP, BP treatment status, diabetes, smoking

**Interpreting Results:**

| 10-Year ASCVD Risk | Category | Statin Recommendation |
|-------------------|---------|----------------------|
| < 5% | Low risk | Lifestyle; statin if LDL >= 190 |
| 5% to < 7.5% | Borderline risk | Lifestyle; shared decision on statin |
| 7.5% to < 20% | Intermediate risk | Moderate-intensity statin recommended |
| >= 20% | High risk | High-intensity statin recommended |

**Statin Benefit Groups (ACC/AHA 2018):**
1. Clinical ASCVD (prior MI, stroke, PAD, ACS): high-intensity statin
2. LDL-C >= 190 mg/dL (severe hypercholesterolemia): high-intensity statin
3. Diabetes, age 40–75, LDL-C 70–189 mg/dL: moderate-intensity statin (high-intensity if 10-yr risk >= 20%)
4. Primary prevention, age 40–75, LDL-C 70–189, 10-yr risk >= 7.5%: moderate-to-high-intensity statin

> Clinical Pearl: "Risk-enhancing factors" that support initiating or intensifying therapy include: family history of premature ASCVD, chronic kidney disease, chronic inflammatory conditions (lupus, RA, psoriasis), HIV, premature menopause, South Asian ancestry, elevated Lp(a) (> 50 mg/dL), elevated hs-CRP (> 2 mg/L), elevated ABI (< 0.9). Coronary artery calcium (CAC) score can reclassify borderline-risk patients.

### Statin Intensity Table

| Intensity | Agents and Doses | Expected LDL-C Reduction |
|-----------|----------------|--------------------------|
| High | Atorvastatin 40–80 mg; rosuvastatin 20–40 mg | >= 50% |
| Moderate | Atorvastatin 10–20 mg; rosuvastatin 5–10 mg; simvastatin 20–40 mg; pravastatin 40–80 mg; lovastatin 40 mg; fluvastatin XL 80 mg; pitavastatin 2–4 mg | 30–49% |
| Low | Simvastatin 10 mg; pravastatin 10–20 mg; lovastatin 20 mg; fluvastatin 20–40 mg; pitavastatin 1 mg | < 30% |

**Statin Side Effects and Monitoring:**
- Myopathy/myalgia: most common; check CK if symptomatic; rhabdomyolysis rare (< 0.1%)
- Hepatotoxicity: rare; baseline LFTs; recheck only if symptomatic
- New-onset diabetes: modest increase in risk (especially high-dose); benefit outweighs risk in most populations
- Avoid simvastatin 80 mg (high myopathy risk)
- Drug interactions: CYP3A4 inhibitors (azole antifungals, macrolide antibiotics, cyclosporine) increase simvastatin/lovastatin levels significantly

### Add-On Lipid-Lowering Therapy

#### Ezetimibe
- **Mechanism:** Inhibits NPC1L1 transporter at intestinal brush border; reduces cholesterol absorption
- **Dose:** 10 mg daily (fixed dose)
- **Effect:** Reduces LDL-C by ~18–20% on top of statin
- **Indication:** When statin alone does not achieve LDL-C target; post-ACS if LDL >= 70 mg/dL on maximally tolerated statin; as add-on in statin-intolerant patients
- **Evidence:** IMPROVE-IT trial showed reduction in MACE when added to simvastatin in post-ACS patients

#### PCSK9 Inhibitors
- **Agents:** Evolocumab (Repatha) 140 mg SC every 2 weeks or 420 mg monthly; alirocumab (Praluent) 75–150 mg SC every 2 weeks
- **Mechanism:** Monoclonal antibodies against PCSK9; prevent LDLR degradation; increase hepatic LDL-C clearance
- **Effect:** Reduce LDL-C by 50–60% on top of statin
- **Indications:** Clinical ASCVD with LDL-C >= 70 mg/dL on maximally tolerated statin + ezetimibe; heterozygous FH; statin intolerance
- **Evidence:** FOURIER (evolocumab) and ODYSSEY OUTCOMES (alirocumab) trials showed CV event reduction
- **Cost:** High; prior authorization often required; patient assistance programs available

#### Bile Acid Sequestrants
- **Agents:** Cholestyramine 4–24 g/day; colesevelam 3.75 g/day; colestipol 5–30 g/day
- **Mechanism:** Bind bile acids in gut, interrupting enterohepatic circulation; force hepatic synthesis of new bile acids from cholesterol
- **Effect:** Reduce LDL-C by 15–30%; may increase TG (avoid in hypertriglyceridemia > 300 mg/dL)
- **Side effects:** Constipation, bloating, interference with drug absorption (take other meds 1 hour before or 4 hours after)

### Triglyceride Management

| TG Level | Category | Management |
|---------|---------|-----------|
| < 150 mg/dL | Normal | — |
| 150–199 mg/dL | Borderline high | Lifestyle modification |
| 200–499 mg/dL | High | Lifestyle + consider pharmacotherapy if ASCVD risk high |
| >= 500 mg/dL | Very high | Immediate treatment (pancreatitis risk); fibrates or high-dose omega-3 |

**Lifestyle for Hypertriglyceridemia:** Eliminate refined carbohydrates, sugar, and alcohol; increase aerobic exercise; reduce saturated fat; achieve weight loss

**Pharmacotherapy for TG >= 500 mg/dL:**
- **Fibrates:** Fenofibrate 145 mg daily; gemfibrozil 600 mg BID (avoid with statins — myopathy risk); reduce TG 30–50%
- **Omega-3 fatty acids:** Prescription icosapentaenoic acid (EPA, Vascepa) 4 g/day; reduce TG 20–30%; REDUCE-IT trial: icosapentaenoic acid 4 g/day reduced CV events in statin-treated patients with TG 150–499 and elevated CV risk
- **Niacin (nicotinic acid):** Extended-release 1–2 g at bedtime; reduces TG 20–40%; raises HDL 15–35%; fell out of favor after AIM-HIGH and HPS2-THRIVE trials showed no added CV benefit over statins; side effects include flushing (mitigated by aspirin 325 mg 30 minutes before), hepatotoxicity, hyperglycemia, hyperuricemia

---

## Common Acute Conditions

### Upper Respiratory Tract Infection (URI / Viral URTI)

**Characteristics:** Rhinorrhea (clear or colored), nasal congestion, sore throat, cough, low-grade fever, myalgias; typically self-limited 7–10 days

**Viral Etiology:** Rhinovirus (most common), coronavirus, adenovirus, parainfluenza, RSV

**Management:**
- Symptomatic relief only: saline nasal irrigation, decongestants (pseudoephedrine, oxymetazoline — limit 3 days), antihistamines, zinc lozenges within 24 hours may reduce duration slightly, honey for cough in adults
- Antibiotics are NOT indicated for viral URI
- Colored nasal discharge does NOT indicate bacterial superinfection
- Return precautions: symptoms worsening after day 7, high fever, signs of lower respiratory involvement, facial pain suggesting sinusitis

> Clinical Pearl: Studies consistently show that patients expect antibiotics but are satisfied with explanations when clinicians discuss why they are unnecessary. The "delayed prescription" strategy (prescription given with instruction to fill only if symptoms worsen) reduces antibiotic use without reducing patient satisfaction.

---

### Streptococcal Pharyngitis

**Centor / McIsaac Scoring:**

| Criterion | Points |
|-----------|--------|
| Tonsillar exudate | +1 |
| Tender anterior cervical lymphadenopathy | +1 |
| Fever (history of or temp > 38°C) | +1 |
| Absence of cough | +1 |
| Age 3–14 years | +1 |
| Age 15–44 years | 0 |
| Age >= 45 years | -1 |

**Score Interpretation:**
- 0–1: No testing, no antibiotics
- 2–3: Rapid antigen detection test (RADT); treat if positive
- 4–5: Empiric treatment or RADT; backup throat culture if RADT negative in children

**Treatment of Confirmed Strep A:**
- Penicillin V 500 mg PO BID-TID x 10 days (first-line)
- Amoxicillin 500 mg PO BID x 10 days (preferred over penicillin V by many due to better compliance)
- PCN allergy (non-anaphylactic): cephalexin 500 mg BID x 10 days
- PCN allergy (anaphylactic): azithromycin 500 mg day 1, then 250 mg days 2–5; or clindamycin 300 mg TID x 10 days

**Goal of Treatment:** Prevention of acute rheumatic fever (treatment must begin within 9 days of onset), reduce symptom duration by 1–2 days, reduce transmission

---

### Acute Bacterial Sinusitis

**Distinguishing Viral from Bacterial (CARS criteria — any of the following):**
- Symptoms persisting > 10 days without improvement
- Severe symptoms (fever > 39°C, purulent discharge, facial pain) for 3–4 consecutive days
- Worsening after initial improvement ("double-sickening")

**Watchful Waiting (no antibiotics):**
- Mild-to-moderate symptoms < 10 days
- Saline irrigation, intranasal corticosteroids, decongestants, analgesics
- Follow up in 7 days if no improvement

**Antibiotic Therapy (if criteria met):**
- First-line: Amoxicillin-clavulanate 875/125 mg PO BID x 5–7 days (adults)
- PCN allergy: Doxycycline 100 mg BID x 5–7 days; or levofloxacin 500 mg daily x 5 days
- High-dose for high-risk regions (resistant S. pneumoniae): Amoxicillin-clavulanate 2000/125 mg BID x 5–7 days

---

### Acute Otitis Media (AOM) vs Otitis Media with Effusion (OME)

**AOM Diagnosis (all three required):**
1. Acute onset (rapid onset < 48 hours)
2. Middle ear effusion (bulging tympanic membrane, reduced mobility, air-fluid level)
3. Signs/symptoms of middle ear inflammation (erythema, otalgia, hearing loss, fever)

**OME (Glue Ear):** Effusion without acute inflammation signs; watchful waiting, no antibiotics

**Watchful Waiting for AOM (acceptable in adults and children > 2 years with mild-moderate disease, unilateral):**
- Analgesics (acetaminophen, NSAIDs, topical benzocaine drops)
- Follow up in 48–72 hours; start antibiotics if no improvement

**Antibiotic Treatment:**
- First-line: Amoxicillin 500 mg TID or 875 mg BID x 5–7 days (adults); 80–90 mg/kg/day divided BID in children
- PCN allergy: Cefdinir, cefuroxime, azithromycin
- Treatment failure (48–72 hours no improvement): Amoxicillin-clavulanate 875/125 mg BID x 5–7 days

---

### Uncomplicated Urinary Tract Infection (Women)

**Uncomplicated UTI Definition:** Premenopausal, non-pregnant women without structural abnormalities, diabetes, immunosuppression, or recent instrumentation

**Symptoms:** Dysuria, frequency, urgency; absence of fever, flank pain, costovertebral angle tenderness

**Diagnosis:** Clinical diagnosis if classic symptoms; urine dipstick (leukocyte esterase + nitrites); culture if diagnosis uncertain

**Treatment Options (Uncomplicated Cystitis):**

| Drug | Dose | Duration |
|------|------|---------|
| Nitrofurantoin macrocrystal (Macrobid) | 100 mg BID | 5 days |
| TMP-SMX DS | 1 tablet (160/800 mg) BID | 3 days |
| Fosfomycin trometamol | 3 g single dose | Single dose |
| Pivmecillinam (not available in US) | 400 mg BID | 3–7 days |

- Fluoroquinolones (ciprofloxacin, levofloxacin) are NOT first-line for uncomplicated UTI (reserve for complicated UTI, pyelonephritis, prostatitis)
- Avoid TMP-SMX if local resistance > 20%

**Recurrent UTI (>= 2 in 6 months or >= 3 in 12 months):**
- Identify and modify risk factors (post-coital voiding, spermicide use, topical estrogen in postmenopausal women)
- Prophylactic strategies: post-coital single dose, continuous low-dose prophylaxis, or self-start therapy

**Complicated UTI Criteria:**
- Male sex, pregnancy, renal transplant, urinary tract abnormality, catheter-associated, recent instrumentation, functional or anatomic abnormality, immunosuppression, hospital-acquired
- Treatment: fluoroquinolone or cephalosporin based on culture; 7–14 days

---

### Community-Acquired Pneumonia (CAP) — Outpatient

**Risk Stratification — PSI/PORT or CURB-65:**

CURB-65 (1 point each):
- Confusion
- Urea > 7 mmol/L (BUN > 19.6 mg/dL)
- Respiratory rate >= 30/min
- Blood pressure SBP < 90 or DBP <= 60 mmHg
- Age >= 65

Score 0–1: Outpatient treatment; Score 2: Consider hospital; Score >= 3: Hospitalize

**Outpatient CAP — Treatment Regimens:**

| Patient Type | Regimen |
|-------------|---------|
| No comorbidities, no recent antibiotics | Amoxicillin 1 g PO TID x 5 days OR doxycycline 100 mg BID x 5 days |
| Comorbidities (COPD, diabetes, heart/liver/renal disease, alcoholism, immunosuppression) | Amoxicillin-clavulanate 875/125 mg BID x 5 days + azithromycin 500 mg day 1, 250 mg days 2–5 |
| Penicillin allergy or recent beta-lactam use | Respiratory fluoroquinolone: levofloxacin 750 mg daily x 5 days OR moxifloxacin 400 mg daily x 5 days |
| Suspected atypical (Mycoplasma, Chlamydophila) | Azithromycin 500 mg day 1, 250 mg days 2–5 OR doxycycline 100 mg BID x 5 days |

> Clinical Pearl: Azithromycin monotherapy is no longer recommended as first-line in many regions due to rising S. pneumoniae macrolide resistance (> 25%). Levofloxacin is appropriate in penicillin-allergic patients but overuse risks Clostridioides difficile.

---

## GERD and Peptic Ulcer Disease

### Gastroesophageal Reflux Disease (GERD)

**Diagnosis:** Clinical; typical symptoms (heartburn, regurgitation) are sufficient to diagnose and start empiric therapy; testing reserved for atypical symptoms or alarm features

**Alarm Symptoms Requiring Endoscopy:**
- Dysphagia (difficulty swallowing)
- Odynophagia (painful swallowing)
- Unintentional weight loss > 10 pounds
- Iron deficiency anemia
- Gastrointestinal bleeding (hematemesis, melena, hematochezia)
- Recurrent vomiting
- Early satiety
- Age >= 60 with new-onset symptoms
- Family history of gastric or esophageal cancer

**Step-Up Therapy:**
1. Lifestyle modifications: elevate head of bed 6–8 inches, avoid meals 2–3 hours before lying down, weight loss, avoid triggers (fatty foods, chocolate, caffeine, alcohol, citrus, spicy foods, peppermint)
2. Antacids (PRN) or H2 receptor antagonists (famotidine 20 mg BID)
3. Proton pump inhibitors (PPIs) once daily, 30–60 minutes before the largest meal, for 8 weeks

**PPI Selection and Dosing:**

| PPI | Dose | Notes |
|-----|------|-------|
| Omeprazole | 20–40 mg daily | OTC available; generic inexpensive |
| Esomeprazole | 20–40 mg daily | S-isomer of omeprazole; marginal efficacy advantage |
| Pantoprazole | 40 mg daily | Good option; IV form available |
| Lansoprazole | 15–30 mg daily | OTC available |
| Rabeprazole | 20 mg daily | Less CYP2C19 metabolism; less drug interaction concern |
| Dexlansoprazole | 30–60 mg daily | Dual delayed-release; can take without food timing |

**PPI Long-Term Concerns:** Hypomagnesemia, B12 deficiency, C. difficile risk, community-acquired pneumonia (modest), hip fractures (debated), CKD (observational, uncertain causality) — use lowest effective dose; attempt PPI taper/wean after symptom control

---

### Helicobacter pylori Infection

**Indications for Testing:**
- Peptic ulcer disease (active or prior)
- Low-grade gastric MALT lymphoma
- After endoscopic resection of early gastric cancer
- Dyspepsia with endoscopy (test and treat strategy)
- Test-and-treat strategy acceptable in young patients with uninvestigated dyspepsia and no alarm features

**Testing Methods:**
- **Urea breath test (UBT):** High sensitivity/specificity (> 95%); non-invasive; test of choice for active infection; hold PPIs 2 weeks before test, hold antibiotics 4 weeks before
- **Stool antigen test (H. pylori Ag):** Sensitivity/specificity ~94%; non-invasive; hold PPIs 2 weeks before; preferred to confirm eradication 4 weeks after treatment
- **Serology (IgG antibody):** Low specificity; cannot distinguish active from past infection; not recommended for diagnosis or confirmation of eradication
- **Endoscopic biopsy (CLO test or histology):** Most accurate; hold PPIs 2 weeks before; used when endoscopy performed for other indications

**Treatment Regimens (ACG Guidelines):**

| Regimen | Drugs | Duration | Eradication Rate |
|---------|-------|---------|-----------------|
| Clarithromycin triple (declining efficacy) | PPI + clarithromycin 500 mg + amoxicillin 1 g (or metronidazole 500 mg if PCN allergy) all BID | 14 days | 70–85% (local resistance dependent) |
| Bismuth quadruple | PPI BID + bismuth subsalicylate 525 mg QID + metronidazole 250–500 mg QID + tetracycline 500 mg QID | 10–14 days | 85–90% |
| Concomitant therapy | PPI + clarithromycin 500 mg + amoxicillin 1 g + metronidazole 500 mg all BID | 14 days | ~90% |
| Vonoprazan-based (newer, FDA-approved 2022) | Vonoprazan 20 mg + amoxicillin 1 g + clarithromycin 500 mg all BID | 14 days | ~85–90% |

**Post-treatment:** Confirm eradication with stool antigen or UBT at least 4 weeks after completing therapy (and 2 weeks after stopping PPIs)

> Clinical Pearl: Clarithromycin-based triple therapy should not be used if local clarithromycin resistance exceeds 15% or if the patient has had prior exposure to clarithromycin. Bismuth quadruple therapy is preferred in such settings and is generally considered the most robust regimen.

---

## Irritable Bowel Syndrome and Functional GI

### Rome IV Criteria for IBS

**Diagnosis (required):** Recurrent abdominal pain, at least 1 day per week on average, for the last 3 months, associated with 2 or more of the following:
1. Related to defecation (onset, relief, or no change with defecation)
2. Associated with a change in stool frequency
3. Associated with a change in stool form (appearance)

Criteria must be fulfilled for the last 3 months with symptom onset >= 6 months ago.

**Subtypes (based on Bristol Stool Scale):**
- IBS-C (constipation-predominant): > 25% hard/lumpy stools (BSS 1–2), < 25% loose/watery
- IBS-D (diarrhea-predominant): > 25% loose/watery (BSS 6–7), < 25% hard/lumpy
- IBS-M (mixed): > 25% hard AND > 25% loose/watery
- IBS-U (unclassified): insufficient abnormality

### IBS Diagnostic Work-Up

- CBC, CMP, TSH (exclude thyroid disease)
- Celiac serology (tTG-IgA) — prevalence of celiac in IBS-D is 4x higher than controls
- Fecal calprotectin or lactoferrin (if IBD a concern, especially IBS-D)
- Colonoscopy if alarm features: rectal bleeding, weight loss, family history of IBD or colorectal cancer, age > 45, nocturnal symptoms

**Alarm Features That Exclude Functional Diagnosis:**
- Rectal bleeding not attributable to hemorrhoids
- Weight loss >= 5% body weight
- Nocturnal diarrhea awakening patient
- Fever
- Anemia
- Family history of colorectal cancer, IBD, or celiac

### IBS Treatment Algorithms

**All IBS Subtypes — First-Line:**
- Patient education and reassurance (Rome Foundation patient resources)
- Low-FODMAP diet (fermentable oligosaccharides, disaccharides, monosaccharides, polyols): 50–80% symptom reduction; requires dietitian guidance; 6–8 week elimination then structured reintroduction
- Stress reduction, CBT (highly effective for global IBS symptoms), gut-directed hypnotherapy
- Regular physical activity

**IBS-C:**
- Soluble fiber (psyllium): 10–25 g/day; avoid insoluble fiber (worsens symptoms)
- Polyethylene glycol (MiraLax): 17 g daily (treats constipation but not pain)
- Linaclotide (Linzess): 290 mcg daily on empty stomach — guanylate cyclase-C agonist; reduces pain and improves stool consistency; first-line FDA-approved
- Lubiprostone (Amitiza): 8 mcg BID with food — chloride channel activator
- Plecanatide (Trulance): 3 mg daily
- Low-dose TCAs (e.g., amitriptyline 10–25 mg at bedtime): for global symptom relief

**IBS-D:**
- Loperamide 2 mg PRN (up to 4 doses/day): reduces stool frequency, urgency; does NOT improve pain
- Rifaximin (Xifaxan): 550 mg TID x 14 days; non-absorbable antibiotic; reduces bloating and diarrhea; can repeat up to 2 courses
- Eluxadoline (Viberzi): 75–100 mg BID with food — mixed opioid agonist/antagonist; contraindicated in patients without gallbladder or with pancreatitis history
- Low-dose TCAs; SSRIs (paroxetine, fluoxetine) may modestly help diarrhea
- Bile acid sequestrants (cholestyramine) if bile acid malabsorption suspected (post-cholecystectomy, Crohn's disease with ileal involvement)

**IBS-M:**
- Combination of above strategies tailored to predominant symptom at any given time
- Antispasmodics: dicyclomine 10–20 mg QID; hyoscyamine 0.125–0.25 mg QID (anticholinergic; avoid in elderly, glaucoma, BPH)
- Peppermint oil enteric-coated capsules: 0.2–0.4 mL TID, 30 minutes before meals — reduces smooth muscle spasm

---

## Mental Health in Primary Care

### PHQ-9 Scoring and Action Thresholds

| Score | Severity | Recommended Action |
|-------|---------|-------------------|
| 0–4 | None to minimal | Monitor; validate if recent stressor |
| 5–9 | Mild | Watchful waiting; supportive counseling; lifestyle interventions; repeat PHQ-9 in 4–6 weeks |
| 10–14 | Moderate | Consider antidepressant or psychotherapy; safety assessment; follow-up in 2–4 weeks |
| 15–19 | Moderately severe | Antidepressant + psychotherapy; close follow-up; consider psychiatry referral |
| 20–27 | Severe | Antidepressant + urgent psychiatry referral; assess safety; hospitalization if imminent risk |

**PHQ-9 Item 9 (Suicidality):** Any score > 0 on "thoughts that you would be better off dead or hurting yourself" requires direct assessment of suicidal ideation, plan, intent, and means.

**PHQ-2 (Screener):** Two items: "Little interest or pleasure in doing things" and "Feeling down, depressed, or hopeless." Score >= 3 triggers full PHQ-9.

---

### GAD-7 Scoring

| Score | Severity | Recommended Action |
|-------|---------|-------------------|
| 0–4 | Minimal anxiety | — |
| 5–9 | Mild | Monitor; lifestyle counseling; reassess in 6–8 weeks |
| 10–14 | Moderate | Consider treatment; CBT or medication |
| 15–21 | Severe | Active treatment recommended; medication + therapy; consider psychiatry referral |

---

### Depression Treatment

**First-Line SSRIs:**

| Drug | Starting Dose | Target Dose | Notes |
|------|--------------|------------|-------|
| Sertraline (Zoloft) | 25–50 mg daily | 100–200 mg daily | Best-studied; favorable side effect profile; broad indications (MDD, GAD, OCD, PTSD, panic) |
| Escitalopram (Lexapro) | 5–10 mg daily | 10–20 mg daily | Most selective SSRI; minimal drug interactions; well tolerated |
| Fluoxetine (Prozac) | 10–20 mg daily | 20–60 mg daily | Long half-life (good for non-adherence, bad if switching to MAOI); more activating; useful for comorbid bulimia |
| Paroxetine (Paxil) | 10–20 mg daily | 20–50 mg daily | Most anticholinergic SSRI; more sedating; significant discontinuation syndrome; CYP2D6 inhibitor |
| Citalopram (Celexa) | 10–20 mg daily | 20–40 mg daily | QTc prolongation at higher doses; max 20 mg/day in adults > 60 or with liver disease |

**First-Line SNRIs:**
- Venlafaxine XR: 37.5–75 mg to start; target 150–225 mg daily; also for GAD, panic, social anxiety
- Duloxetine: 30–60 mg daily; also FDA-approved for GAD, diabetic neuropathy, fibromyalgia, musculoskeletal pain
- Desvenlafaxine: 50 mg daily (fixed therapeutic dose)

**Adjuncts and Second-Line:**
- Bupropion SR/XL: 150 mg daily to start, titrate to 300–450 mg/day; no sexual dysfunction; avoid in eating disorders or seizure history; also for smoking cessation
- Mirtazapine: 15–45 mg at bedtime; promotes sleep and appetite; useful in underweight patients with insomnia; minimal sexual dysfunction
- Atypical antipsychotics as augmentation (quetiapine, aripiprazole, brexpiprazole): when partial response to antidepressant at 4–8 weeks

**Response Monitoring:** Full therapeutic trial = adequate dose for >= 4–6 weeks; full response evaluation at 8–12 weeks; if < 50% improvement, change or augment

---

### Anxiety Treatment in Primary Care

**Generalized Anxiety Disorder (GAD) First-Line:**
- SSRIs (sertraline, escitalopram, paroxetine): same agents as depression; 4–8 weeks to full effect
- SNRIs (venlafaxine XR, duloxetine): excellent evidence for GAD
- Buspirone: 5 mg TID initially; titrate to 15–30 mg/day in divided doses; onset 2–4 weeks; no dependence, no sedation; useful if benzodiazepine avoidance desired

**Short-Term Benzodiazepines:**
- Agents: lorazepam 0.5–2 mg, alprazolam 0.25–0.5 mg, clonazepam 0.25–0.5 mg
- Use: Bridge therapy while awaiting SSRI/SNRI onset; acute situational anxiety; procedural sedation
- Duration: Limit to 2–4 weeks when possible; avoid in patients with substance use disorders, respiratory depression, myasthenia gravis
- Risks: Sedation, cognitive impairment, falls (elderly), dependence, withdrawal seizures if abruptly stopped
- Tapering: Reduce dose by 10–25% every 1–2 weeks; switch to long-acting agent (clonazepam or diazepam) if tapering from short-acting benzodiazepine

**Panic Disorder:** SSRIs (paroxetine, sertraline, fluoxetine); SNRIs; avoid benzodiazepines as primary therapy; CBT with exposure

---

### Suicidality Assessment and Safety Planning

**Columbia Suicide Severity Rating Scale (C-SSRS) — Key Questions:**
1. Passive ideation: "I wish I were dead"
2. Active ideation without intent or plan
3. Ideation with intent but no plan
4. Ideation with plan but no intent to act
5. Ideation with plan and intent to act

**Risk Factor Assessment:**
- Prior suicide attempt (strongest predictor)
- Current depressive episode, hopelessness
- Substance use disorder
- Access to lethal means (firearms, medications)
- Social isolation, recent loss
- Chronic pain, terminal illness
- Male sex, older age, veteran status

**Safety Planning Protocol (Stanley-Brown Safety Planning Intervention):**
1. Warning signs that a crisis is developing
2. Internal coping strategies (distraction, self-soothing)
3. Social contacts for distraction (not crisis-focused)
4. People to reach out to for help
5. Professional contacts and crisis lines (988 Suicide and Crisis Lifeline)
6. Making the environment safe: lethal means counseling (firearms removal, medication lock-box)

**Mandatory Evaluation/Hospitalization:** Active suicidal ideation with plan, intent, and/or access to means; psychosis with command hallucinations; inability to maintain safety contract; no social support; failed outpatient treatment

---

## Dermatology

### Cellulitis and Skin/Soft Tissue Infections (SSTI)

**Classification (IDSA):**
- Non-purulent cellulitis: warm, erythematous, swollen, tender skin without abscess or purulence
- Purulent SSTI: abscess, furuncle, carbuncle, infected wound with purulence

**Likely Organisms:**
- Non-purulent cellulitis: Streptococcus pyogenes (Group A Strep) most common; S. aureus less common
- Purulent SSTI: S. aureus (MRSA increasingly common, especially community-acquired)

**Severity Classification:**
- Mild: No systemic signs; mild local infection
- Moderate: Systemic signs (fever > 38°C, HR > 90, RR > 24, WBC > 12,000 or < 400)
- Severe: Systemic signs + hypotension, necrotizing infection, or immunocompromised

**Treatment:**

| Type | Severity | First-Line Drug | Dose | Duration |
|------|---------|----------------|------|---------|
| Non-purulent cellulitis | Mild | Cephalexin | 500 mg QID | 5 days (extend if no improvement) |
| Non-purulent cellulitis | Mild (PCN allergy) | Clindamycin | 300–450 mg TID | 5 days |
| Purulent SSTI (CA-MRSA coverage) | Mild | TMP-SMX DS | 1–2 tabs BID | 5–7 days |
| Purulent SSTI (CA-MRSA) | Mild | Doxycycline | 100 mg BID | 5–7 days |
| Non-purulent cellulitis | Moderate | Nafcillin or oxacillin IV | 1–2 g IV q4h | Per inpatient team |
| MRSA coverage (moderate) | Moderate | Vancomycin IV | Per pharmacist | Per inpatient team |

> Clinical Pearl: Demarcate the borders of cellulitis with a skin marker at first visit. If the border does not advance after 48–72 hours, treatment is working. Failure to improve or rapid progression should prompt consideration of necrotizing fasciitis, which requires urgent surgical consultation.

---

### Tinea Infections

| Type | Location | Common Organism | Treatment |
|------|---------|----------------|-----------|
| Tinea corporis (ringworm) | Body, trunk | T. rubrum, T. tonsurans | Topical terbinafine 1% cream BID x 1–4 weeks |
| Tinea pedis (athlete's foot) | Feet, interdigital | T. rubrum, E. floccosum | Topical terbinafine BID x 1–2 weeks; clotrimazole BID x 4 weeks |
| Tinea cruris (jock itch) | Groin | T. rubrum, E. floccosum | Topical terbinafine or clotrimazole BID x 2–4 weeks |
| Tinea unguium (onychomycosis) | Nails | T. rubrum | Oral terbinafine 250 mg daily x 6 weeks (fingernails) or 12 weeks (toenails); OR oral fluconazole 150 mg weekly x 6 months (toenails) |
| Tinea capitis | Scalp (children) | T. tonsurans, M. canis | Oral griseofulvin 20–25 mg/kg/day ultramicronized x 6–8 weeks; OR oral terbinafine x 4–6 weeks (for T. tonsurans) |
| Tinea versicolor | Trunk (hypopigmented patches) | Malassezia furfur | Topical selenium sulfide shampoo x 2 weeks; topical ketoconazole 2% shampoo; single dose oral fluconazole 300 mg |

**Topical vs Oral Guidance:** Topical preferred for localized, non-nail tinea. Oral required for tinea capitis (topical does not penetrate hair follicle), nail involvement, extensive body involvement, or immunocompromised patients.

---

### Acne Vulgaris

**Classification:**
- Comedonal: open (blackheads) and closed (whiteheads) comedones; no inflammation
- Mild-moderate inflammatory: < 20 inflammatory lesions (papules, pustules)
- Moderate-severe inflammatory: 20–50 inflammatory lesions
- Nodular/cystic: > 5 nodules/cysts or > 50 total lesions

**Treatment Step Therapy:**

| Severity | First-Line | Add/Escalate |
|---------|-----------|-------------|
| Comedonal | Topical retinoid (tretinoin 0.025–0.1% cream or gel, adapalene 0.1–0.3% gel) | — |
| Mild-moderate inflammatory | Topical retinoid + benzoyl peroxide 2.5–10% (BPO) | Add topical antibiotic (clindamycin 1% gel or solution) with BPO to prevent resistance |
| Moderate-severe | Oral antibiotic (doxycycline 50–100 mg BID or minocycline 50–100 mg BID) x 3 months maximum + topical retinoid + BPO | Limit antibiotic duration; use BPO concurrently |
| Severe nodular/cystic, treatment-resistant, scarring | Isotretinoin (Accutane) 0.5–1 mg/kg/day x 5–6 months | iPLEDGE program enrollment required; monthly pregnancy tests in women; teratogenic (X) |

**Topical Retinoid Guidance:** Apply pea-sized amount to entire face at night on dry skin; expect initial purging (increased breakouts) for 4–6 weeks; SPF required; avoid in pregnancy

**Hormonal Therapy for Women:** Combined OCPs (FDA-approved: Ortho Tri-Cyclen, Yaz, Estrostep); spironolactone 25–100 mg daily (off-label; reduces sebum production; avoid in pregnancy)

---

### Rosacea

**Subtypes and Treatment:**

| Subtype | Features | Treatment |
|---------|---------|-----------|
| ETR (Erythematotelangiectatic) | Flushing, persistent erythema, telangiectasias, no papules | Topical brimonidine (Mirvaso) 0.33% gel; topical oxymetazoline (Rhofade); laser/IPL for telangiectasias |
| PPR (Papulopustular) | Acne-like papules/pustules; no comedones | Topical metronidazole 0.75–1%; topical ivermectin (Soolantra) 1% cream daily; topical azelaic acid 15%; oral doxycycline 40 mg DR (Oracea) daily |
| Phymatous | Skin thickening, rhinophyma | Oral antibiotics; surgical/CO2 laser resection for rhinophyma |
| Ocular | Blepharitis, meibomian gland dysfunction, foreign body sensation | Lid hygiene; oral doxycycline 40–100 mg daily; topical cyclosporine eye drops |

**Triggers to Avoid:** Sun exposure (wear SPF 30+ daily), heat/hot beverages, alcohol, spicy food, wind/cold

---

## Musculoskeletal Conditions

### Acute Low Back Pain

**Red Flags (Require Immediate Imaging/Workup):**
- Age < 18 or > 50 with new-onset pain
- History of cancer (especially breast, prostate, lung, thyroid, kidney)
- Unexplained weight loss
- Fever
- Bladder or bowel dysfunction (cauda equina syndrome — emergent MRI)
- Saddle anesthesia
- Significant trauma or compression fracture risk (osteoporosis, chronic steroid use)
- Intravenous drug use
- Immunosuppression
- Neurologic deficits (progressive weakness, bilateral sciatica)

**Imaging Criteria:** None for uncomplicated acute LBP < 6 weeks without red flags; MRI for red flags or radiculopathy not improving after 4–6 weeks of conservative therapy

**Management — Acute (< 4 weeks):**
- Patient education: reassurance that most acute LBP resolves in 4–6 weeks; encourage activity as tolerated; avoid prolonged bed rest
- NSAIDs: naproxen 500 mg BID or ibuprofen 600 mg TID x 1–2 weeks (first-line for most patients)
- Acetaminophen: 500–1000 mg TID-QID (less effective than NSAIDs alone for LBP based on recent meta-analyses, but safe)
- Muscle relaxants (short-term use): cyclobenzaprine 5–10 mg TID; methocarbamol 750 mg QID; tizanidine 2–4 mg TID-QID (caution in elderly — sedation, falls)
- Heat (superficial) for muscle spasm
- Physical therapy referral if not improving in 2–4 weeks
- Avoid opioids as first-line; reserve for severe acute pain, short course, with close follow-up

**Chronic LBP (> 12 weeks):**
- Multi-disciplinary approach: exercise therapy, CBT, PT, pain management
- Duloxetine 30–60 mg daily (modest benefit for chronic LBP)
- Spinal manipulation, acupuncture: modest evidence, low risk — reasonable adjunct
- Epidural steroid injections: consider for radicular pain not responding to conservative care at 6–12 weeks

---

### Knee Osteoarthritis

**Diagnosis:** Clinical (pain with weight-bearing, crepitus, bony enlargement, decreased ROM, morning stiffness < 30 minutes); X-ray confirms (joint space narrowing, osteophytes, subchondral sclerosis)

**Step Therapy:**

1. **Lifestyle:** Weight loss (each pound lost reduces knee load by 4 pounds); 5–10% weight loss can significantly reduce pain; supervised exercise (water aerobics, cycling, walking)

2. **Physical Therapy:** Quadriceps strengthening; range-of-motion exercises; orthotics/bracing for valgus/varus malalignment

3. **Analgesia:**
   - Topical diclofenac (Voltaren Arthritis Pain 1% gel): 4 g per knee QID; excellent safety profile; preferred for isolated joint OA
   - Acetaminophen 500–1000 mg TID-QID: modest efficacy, safe for most patients; hepatotoxic in overdose
   - Oral NSAIDs: naproxen 500 mg BID, ibuprofen 600–800 mg TID, meloxicam 7.5–15 mg daily; add PPI if GI risk
   - Duloxetine 30–60 mg daily: modest benefit in OA pain

4. **Intra-articular Injections:**
   - Corticosteroid (triamcinolone acetonide 40 mg or methylprednisolone 40–80 mg): rapid pain relief for 2–8 weeks; limit to 3–4 injections per year per joint (cartilage concerns with frequent use)
   - Hyaluronic acid (viscosupplementation): controversial; ACR guidelines do not recommend; some patients report benefit; generally safe

5. **Surgical Referral:** Total knee arthroplasty when symptoms are severe and refractory to conservative therapy for >= 3–6 months, with functional limitation and radiographic evidence of moderate-to-severe OA; age and medical comorbidities factor into decision

---

### Gout

**Pathophysiology:** Monosodium urate crystal deposition in joints and soft tissues due to hyperuricemia (uric acid > 6.8 mg/dL)

**Acute Gout Attack Management (goal: resolve inflammation rapidly):**

| Agent | Dose | Duration | Notes |
|-------|------|---------|-------|
| Colchicine (first-line) | 1.2 mg at onset, then 0.6 mg 1 hour later; then 0.6 mg BID-TID until resolved | Up to 7–10 days | Most effective if started within 24 hours; reduce dose in renal impairment; CYP3A4/P-gp interactions (avoid with strong inhibitors) |
| NSAIDs (first-line) | Indomethacin 50 mg TID or naproxen 500 mg BID | 5–7 days | Avoid in CKD, peptic ulcer disease, heart failure |
| Corticosteroids (second-line or if NSAIDs/colchicine contraindicated) | Prednisone 40 mg daily x 5 days, then taper | 7–10 days total | Useful in polyarticular attacks, renal failure, elderly |
| Intra-articular triamcinolone | 20–40 mg into affected joint | Single injection | For monoarthritis when oral therapy not feasible |

> Clinical Pearl: Do NOT start or stop urate-lowering therapy (ULT) during an acute gout attack — mobilization of uric acid crystals during ULT initiation can prolong or trigger attacks. Wait 2–4 weeks after acute attack resolves before starting or adjusting allopurinol.

**Chronic Gout / Urate-Lowering Therapy (ULT) Indications:**
- >= 2 gout attacks per year
- Tophi
- Uric acid nephrolithiasis
- Gout with CKD (eGFR < 90)
- Radiographic joint damage

**ULT Target:** Uric acid < 6.0 mg/dL; < 5.0 mg/dL in tophaceous gout

| Drug | Starting Dose | Target Dose | Notes |
|------|--------------|------------|-------|
| Allopurinol (xanthine oxidase inhibitor) | 100 mg daily (50 mg in CKD) | Titrate by 100 mg q4 weeks to target UA level; max 800 mg/day | First-line; HLA-B*5801 testing before use in Asian patients (severe cutaneous adverse reactions — SJS/TEN); dose adjust for CKD |
| Febuxostat (Uloric) | 40 mg daily | 40–80 mg daily | Reserve for allopurinol-intolerant patients; FDA black box warning for CV mortality (CARES trial); avoid in CV disease |
| Probenecid (uricosuric) | 250 mg BID | 500–1000 mg BID | Second-line; avoid in urolithiasis, CrCl < 50; requires adequate hydration |
| Pegloticase (Krystexxa) | 8 mg IV q2 weeks | Fixed | For severe tophaceous gout refractory to oral ULT; monitor for infusion reactions; check G6PD deficiency |

**Prophylaxis During ULT Initiation:** Colchicine 0.6 mg daily (or BID if tolerated) for 3–6 months; or low-dose NSAID; reduces flare rate during ULT initiation

**Dietary Guidance:** Reduce purine-rich foods (organ meats, shellfish, red meat), limit alcohol (especially beer and spirits), avoid fructose-sweetened beverages, maintain adequate hydration; cherry extract may modestly reduce attacks

---

## Smoking Cessation

### The 5 A's Framework

1. **Ask** — Identify and document tobacco use status at every visit
2. **Advise** — Give clear, strong, personalized advice to quit: "As your doctor, the most important thing you can do for your health is to quit smoking. I strongly urge you to quit."
3. **Assess** — Assess willingness to quit: "Are you willing to set a quit date in the next 30 days?"
4. **Assist** — Assist with quit plan: set a quit date, discuss pharmacotherapy, provide self-help materials, arrange follow-up
5. **Arrange** — Arrange follow-up contact within 1 week of quit date; phone call or visit; 1800-QUIT-NOW referral

### Pharmacotherapy for Smoking Cessation

#### Varenicline (Chantix / Champix)
- **Mechanism:** Partial agonist at nicotinic alpha4beta2 acetylcholine receptor; reduces cravings and withdrawal; reduces reward from smoking
- **Dosing:**
  - Days 1–3: 0.5 mg once daily
  - Days 4–7: 0.5 mg BID
  - Week 2 onward: 1 mg BID
  - Start 1 week BEFORE the quit date; treat for 12 weeks; can extend another 12 weeks to reduce relapse
- **Evidence:** Most effective single agent; 44% continuous abstinence at 12 weeks vs 25% for bupropion, 18% for NRT
- **Side effects:** Nausea (take with food and full glass of water), vivid dreams, insomnia; FDA removed black box warning for neuropsychiatric effects in 2016 after EAGLES trial
- **Contraindications:** Severe renal impairment (reduce dose); caution if history of serious psychiatric illness (monitor, but not contraindicated)
- **Drug interaction:** Cleared by renal excretion; minimal hepatic metabolism

#### Bupropion SR (Zyban)
- **Mechanism:** Inhibits reuptake of dopamine and norepinephrine; weak antagonist at nicotinic receptors
- **Dosing:**
  - 150 mg once daily x 3 days, then 150 mg BID
  - Start 1–2 weeks BEFORE the quit date
  - Continue for 7–12 weeks; can extend up to 6 months
- **Side effects:** Insomnia (take second dose by mid-afternoon), dry mouth, headache, reduced seizure threshold
- **Contraindications:** Seizure disorder, history of eating disorder (bulimia, anorexia), MAOI use within 14 days, abrupt alcohol or benzodiazepine withdrawal
- **Also treats:** Depression, ADHD (synergistic benefit in comorbid depression + smoking)

#### Nicotine Replacement Therapy (NRT)

| Form | Dose | Notes |
|------|------|-------|
| Patch (24-hour) | 14–21 mg patch (21 mg if smoking >= 10 cigarettes/day); step down to 14 mg x 6 weeks, then 7 mg x 2 weeks | Apply to clean, dry, hairless skin; rotate sites; can cause local irritation or vivid dreams |
| Gum | 2 mg (< 25 cigarettes/day); 4 mg (>= 25 cigarettes/day) | "Chew and park" method; park in cheek when tingling; use 1 piece q1–2h for 6 weeks, then taper; max 24 pieces/day |
| Lozenge | 2 mg or 4 mg based on time to first cigarette | If first cigarette within 30 min of waking: use 4 mg; allow to dissolve in 20–30 min; no eating/drinking 15 min before |
| Nasal spray | 1–2 sprays per nostril hourly | Fastest peak delivery; high addiction potential |
| Oral inhaler | 6–16 cartridges/day | Mimics hand-to-mouth behavior; useful for behavioral component |

**Combination NRT:** Patch (sustained baseline) + short-acting NRT (gum or lozenge for breakthrough cravings) — superior to single NRT product

**Duration of NRT:** 8–12 weeks standard; tapering patch dose; extended use is safe if it prevents relapse

### Behavioral Counseling
- Brief counseling (< 3 minutes) increases cessation rates; intensive counseling (> 10 minutes, multiple sessions) doubles quit rates
- Refer to state quitline (1-800-QUIT-NOW) — free coaching and often free NRT
- Combination of pharmacotherapy + behavioral counseling is more effective than either alone

---

## Contraception Overview

### Contraceptive Efficacy Comparison

| Method | Typical Use Failure Rate (Pearl Index) | Perfect Use Failure Rate | Duration / Notes |
|--------|----------------------------------------|--------------------------|-----------------|
| No method | 85% | 85% | — |
| Copper IUD (Paragard) | 0.8% | 0.6% | Up to 10–12 years; also most effective EC |
| Levonorgestrel IUD (Mirena) | 0.1–0.2% | 0.1% | Up to 8 years |
| Levonorgestrel IUD (Kyleena) | 0.2% | 0.1% | Up to 5 years; lower hormone; lighter periods |
| Etonogestrel implant (Nexplanon) | 0.1% | 0.05% | Up to 3 years; most effective reversible method |
| DMPA injection (Depo-Provera) | 4% | 0.2% | Every 3 months; possible prolonged amenorrhea; bone density decrease (reversible) |
| Combined OCP | 7% | 0.3% | Daily; back-up x 7 days if missed |
| Progestin-only pill (minipill) | 7–9% | 0.3% | Must take within same 3-hour window daily |
| Vaginal ring (NuvaRing) | 7% | 0.3% | Monthly; self-inserted |
| Patch (Xulane) | 7% | 0.3% | Weekly x 3 weeks; less effective if > 198 lbs |
| Male condom | 13% | 2% | Only method protecting against STIs |
| Female condom | 21% | 5% | — |
| Diaphragm (with spermicide) | 17% | 6% | Requires fitting; placed before sex |
| Spermicide alone | 21% | 16% | — |
| Fertility awareness methods | 2–23% | variable | Requires training and consistency |
| Male sterilization (vasectomy) | 0.15% | 0.1% | Permanent |
| Female sterilization (tubal) | 0.5% | 0.5% | Permanent |

---

### Combined OCP Contraindications (US MEC Categories)

**US Medical Eligibility Criteria (US MEC):**
- Category 1: No restriction; always use
- Category 2: Advantages generally outweigh risks; use
- Category 3: Risks generally outweigh advantages; avoid if possible
- Category 4: Unacceptable health risk; do not use (absolute contraindication)

**Combined OCP — Category 4 (Absolute Contraindications):**
- Breastfeeding < 6 weeks postpartum
- Age >= 35 and smoking >= 15 cigarettes/day
- Multiple cardiovascular risk factors (hypertension, diabetes, smoking, obesity together)
- Hypertension (systolic >= 160 or diastolic >= 100)
- Current or history of VTE (DVT or PE) without anticoagulation
- Known thrombogenic mutations (Factor V Leiden, prothrombin gene mutation, protein C/S deficiency)
- Ischemic heart disease (current or history)
- Stroke (history of or risk factors for)
- Complicated valvular heart disease
- Migraine with aura (Category 4)
- Active breast cancer or history of breast cancer
- Severe cirrhosis, hepatocellular adenoma, or hepatocellular carcinoma
- Systemic lupus erythematosus with positive or unknown antiphospholipid antibodies
- Peripartum cardiomyopathy (< 6 months)
- Bariatric surgery — malabsorptive procedures (oral OCPs absorbed poorly)

**Category 3 (Relative Contraindications):**
- Migraine without aura (category 2 if < 35, category 3 if >= 35)
- Smoking < 15 cigarettes/day age >= 35
- Postpartum 6 weeks to 6 months (breastfeeding)
- History of gestational diabetes
- Adequately controlled hypertension (Category 3)
- Gall bladder disease (current or medically treated)
- Use of enzyme-inducing medications (rifampin, carbamazepine, phenytoin, phenobarbital, topiramate, efavirenz)

---

### IUD and Other Long-Acting Reversible Contraception (LARC)

**Levonorgestrel IUDs (Mirena, Kyleena, Liletta, Skyla):**
- Mechanism: Thickens cervical mucus, thins endometrium, partially suppresses ovulation
- Benefits: Reduced menstrual bleeding (Mirena: 50% chance of amenorrhea at 1 year), dysmenorrhea improvement
- Insertion: Can be placed in any menstrual phase; no cervical dilation required in most; local cervical block optional
- Contraindications (US MEC 4): Current PID or STI, unexplained vaginal bleeding, uterine cavity distortion, cervical or endometrial cancer
- Expulsion rate: 5% at 5 years

**Copper IUD (Paragard):**
- Mechanism: Copper ions spermicidal; inhibits fertilization
- Benefits: Hormone-free; most effective emergency contraception (if placed within 5 days of unprotected sex)
- Drawbacks: Heavier, more painful periods especially initially
- Duration: FDA-approved 10 years; evidence supports up to 12 years

**Etonogestrel Implant (Nexplanon):**
- Single 4 cm rod inserted in upper arm subdermally
- Mechanism: Progestin suppresses ovulation (primary mechanism)
- Duration: 3 years (FDA); evidence up to 5 years
- Amenorrhea in 20%; irregular unpredictable bleeding common (leading cause of discontinuation)
- Highly effective regardless of weight or medications (except enzyme inducers — rifampin, anticonvulsants)

**DMPA (Depo-Provera) Injectable:**
- Depot medroxyprogesterone acetate 150 mg IM (or 104 mg subcutaneous) every 12–13 weeks
- Fertility return delayed 6–10 months after last injection
- Bone mineral density decrease during use (reversible after discontinuation)
- FDA black box warning: do not use > 2 years unless other methods inadequate (bone density concern)

---

### Emergency Contraception

| Method | Timing | Mechanism | Efficacy |
|--------|--------|-----------|---------|
| Levonorgestrel (Plan B One-Step, others) | Within 72 hours; less effective up to 120 hours | Delays or inhibits ovulation; does not affect implantation | 89% if taken within 72 hours; less effective at higher BMI |
| Ulipristal acetate (ella) | Within 120 hours (5 days) | Selective progesterone receptor modulator; delays ovulation | 98%; more effective than levonorgestrel at 72–120 hours; maintains efficacy at higher BMI |
| Copper IUD (Paragard) | Within 120 hours (5 days) | Spermicidal + prevents implantation | > 99.9%; most effective EC; provides ongoing contraception |

> Clinical Pearl: ella requires a prescription; Plan B is OTC. ella should not be used simultaneously with progestin-containing products (they compete for progesterone receptor). Copper IUD is the most effective EC regardless of weight and is ideal for patients desiring ongoing contraception.

---

## Substance Use Screening

### AUDIT-C (Alcohol Use Disorders Identification Test — Consumption)

**Three Items (scored 0–4 each; maximum score 12):**

1. How often do you have a drink containing alcohol?
   - Never (0) / Monthly or less (1) / 2–4 times/month (2) / 2–3 times/week (3) / 4+ times/week (4)

2. How many drinks containing alcohol do you have on a typical day when you are drinking?
   - 1–2 (0) / 3–4 (1) / 5–6 (2) / 7–9 (3) / 10+ (4)

3. How often do you have 5 or more drinks on one occasion?
   - Never (0) / Less than monthly (1) / Monthly (2) / Weekly (3) / Daily or almost daily (4)

**Scoring Thresholds:**
- Men: AUDIT-C >= 4 = positive screen for hazardous/harmful alcohol use
- Women: AUDIT-C >= 3 = positive screen
- Score >= 8 on full AUDIT: likely alcohol use disorder

**Full AUDIT-10:** 10-item version; total score >= 8 = harmful/hazardous drinking; >= 15 = alcohol dependence likely

---

### DAST-10 (Drug Abuse Screening Test)

10 yes/no questions about drug use in past 12 months (excluding alcohol and tobacco):

| Score | Level | Action |
|-------|-------|--------|
| 0 | No problem | None |
| 1–2 | Low | Brief advice |
| 3–5 | Moderate | Further assessment; brief counseling |
| 6–8 | Substantial | Intensive assessment; treatment referral |
| 9–10 | Severe | Intensive assessment; immediate referral |

---

### Brief Intervention — FRAMES Model

- **F — Feedback:** Provide personalized, non-judgmental feedback on screening results ("Your AUDIT-C score suggests your drinking may be affecting your health.")
- **R — Responsibility:** Emphasize personal responsibility for change ("The decision to change is entirely yours.")
- **A — Advice:** Give clear, specific advice to reduce or stop use ("I strongly advise you to cut back to no more than 14 drinks per week for men.")
- **M — Menu:** Offer a menu of options (counseling, medications, self-help groups, quit plans)
- **E — Empathy:** Use empathic, reflective, non-confrontational communication
- **S — Self-efficacy:** Support and reinforce confidence that change is possible ("Many of my patients have successfully cut back. I believe you can too.")

**Duration:** Brief intervention can be effective in 5–15 minutes; multiple sessions increase efficacy

---

### Referral Thresholds

| Screening Result | Action |
|-----------------|--------|
| AUDIT-C positive; no AUD criteria | Brief motivational intervention; follow-up in 1–3 months |
| AUD moderate (4–5 DSM-5 criteria) | Brief intervention + pharmacotherapy discussion; refer to addiction medicine or structured outpatient program |
| AUD severe (>= 6 DSM-5 criteria) | Intensive outpatient program (IOP), residential treatment, or addiction medicine; pharmacotherapy (naltrexone, acamprosate, disulfiram) |
| Opioid use disorder (OUD) | Offer buprenorphine (can be prescribed in primary care with X waiver, now eliminated — standard DEA suffices); refer to MAT program; naloxone co-prescription |
| Any substance use disorder with safety concern | Urgent addiction medicine or behavioral health referral; safety planning |

**Motivational Interviewing Principles:** Open-ended questions, affirmations, reflective listening, summarizing (OARS); avoid confrontation; explore ambivalence; roll with resistance; support self-efficacy

---

## Quick Reference Drug Dosing Table

| Drug | Indication | Dose | Route | Frequency | Duration / Notes |
|------|-----------|------|-------|-----------|-----------------|
| Chlorthalidone | Hypertension | 12.5–25 mg | PO | Daily | First-line diuretic; monitor BMP |
| Hydrochlorothiazide | Hypertension | 12.5–50 mg | PO | Daily | Monitor electrolytes |
| Lisinopril | Hypertension, heart failure, CKD | 10–40 mg | PO | Daily | Avoid in pregnancy; monitor K, Cr |
| Enalapril | Hypertension | 5–40 mg | PO | Daily (BID if needed) | Same class as lisinopril |
| Losartan | Hypertension, CKD (if ACEi intolerant) | 50–100 mg | PO | Daily | First-line ARB |
| Valsartan | Hypertension, HFrEF | 80–320 mg | PO | Daily | Monitor K, Cr |
| Amlodipine | Hypertension, angina | 2.5–10 mg | PO | Daily | Peripheral edema common |
| Diltiazem ER | Hypertension, rate control (AF) | 120–540 mg | PO | Daily | Avoid in HFrEF |
| Atorvastatin | Hyperlipidemia (moderate-high intensity) | 10–80 mg | PO | Daily (evening or anytime) | Check CK if myalgias |
| Rosuvastatin | Hyperlipidemia (moderate-high intensity) | 5–40 mg | PO | Daily | Less CYP3A4; fewer drug interactions |
| Ezetimibe | Hyperlipidemia (add-on) | 10 mg | PO | Daily | LDL reduction ~20% |
| Evolocumab | Hyperlipidemia (PCSK9 inhibitor) | 140 mg | SC | Every 2 weeks | Or 420 mg monthly |
| Fenofibrate | Hypertriglyceridemia | 145 mg | PO | Daily | Avoid with gemfibrozil + statin |
| Icosapentaenoic acid (Vascepa) | Hypertriglyceridemia + high CV risk | 4 g (2 caps BID) | PO | BID with meals | REDUCE-IT; do not substitute OTC fish oil |
| Amoxicillin | Strep pharyngitis, AOM, sinusitis, CAP | 500 mg (pharyngitis) / 875 mg (AOM/sinusitis) / 1 g TID (CAP) | PO | BID-TID | Most indications 5–10 days |
| Amoxicillin-clavulanate | Sinusitis, AOM (failure), CAP with comorbidities | 875/125 mg | PO | BID | 5–7 days sinusitis; 5 days CAP |
| Penicillin V | Strep pharyngitis | 500 mg | PO | BID-TID | 10 days |
| Azithromycin | CAP (atypical), strep (PCN allergy) | 500 mg day 1, 250 mg days 2–5 | PO | Daily | 5-day Z-pack |
| Doxycycline | Sinusitis (PCN allergy), CAP, acne, gout (Lyme) | 100 mg | PO | BID | 5–14 days depending on indication |
| Levofloxacin | CAP (penicillin allergy or comorbidities) | 750 mg | PO | Daily | 5 days for CAP |
| Nitrofurantoin | Uncomplicated UTI | 100 mg (Macrobid) | PO | BID | 5 days; avoid if eGFR < 45 |
| TMP-SMX DS | Uncomplicated UTI, MRSA SSTI | 1 tablet (160/800 mg) | PO | BID | 3 days UTI; 5–7 days SSTI |
| Fosfomycin | Uncomplicated UTI | 3 g sachet | PO | Single dose | Dissolve in 4 oz water |
| Ciprofloxacin | Complicated UTI, pyelonephritis | 500 mg | PO | BID | 7–14 days |
| Cephalexin | Non-purulent cellulitis, strep (PCN allergy non-anaphylactic) | 500 mg | PO | QID | 5–7 days |
| Dicloxacillin | Non-purulent cellulitis | 500 mg | PO | QID | 5–7 days; take on empty stomach |
| Omeprazole | GERD, PUD | 20–40 mg | PO | Daily | 30–60 min before meal; 8 weeks |
| Pantoprazole | GERD, PUD, H. pylori regimen | 40 mg | PO | Daily-BID | 8 weeks; BID for H. pylori regimens |
| Famotidine | GERD (step-down), acid suppression | 20 mg | PO | BID | OTC 10 mg; maintenance after PPI taper |
| Clarithromycin | H. pylori triple therapy | 500 mg | PO | BID | 14 days with PPI + amoxicillin |
| Metronidazole | H. pylori quadruple therapy, BV, C. diff | 250–500 mg | PO | TID-QID | 10–14 days (H. pylori) |
| Tetracycline | H. pylori quadruple therapy | 500 mg | PO | QID | 14 days |
| Bismuth subsalicylate | H. pylori quadruple therapy | 525 mg | PO | QID | 14 days |
| Linaclotide | IBS-C | 290 mcg | PO | Daily (30 min before meal) | 12 weeks; 72 mcg for CIC |
| Rifaximin | IBS-D | 550 mg | PO | TID | 14 days; can repeat 2 courses |
| Loperamide | IBS-D, acute diarrhea | 2 mg | PO | After each loose stool; max 16 mg/day | PRN; not for infectious diarrhea |
| Lubiprostone | IBS-C, CIC | 8–24 mcg | PO | BID with food | 8 mcg for IBS-C; 24 mcg for CIC |
| Sertraline | Depression, anxiety | 25–50 mg start; 100–200 mg target | PO | Daily | 4–8 weeks to assess response |
| Escitalopram | Depression, GAD | 5–10 mg start; 10–20 mg target | PO | Daily | Minimal drug interactions |
| Fluoxetine | Depression | 10–20 mg start; 20–60 mg target | PO | Morning | Long half-life; activating |
| Venlafaxine XR | Depression, GAD, panic | 37.5–75 mg start; 150–225 mg target | PO | Daily | Taper slowly to avoid discontinuation |
| Duloxetine | Depression, GAD, diabetic neuropathy, OA | 30–60 mg | PO | Daily | Useful for pain comorbidities |
| Bupropion SR | Depression, smoking cessation | 150 mg daily x 3 days, then 150 mg BID | PO | Daily-BID | Max 450 mg/day; no sexual dysfunction |
| Buspirone | GAD (adjunct) | 5 mg TID; titrate to 15–30 mg/day | PO | TID | 2–4 weeks to onset; no dependence |
| Lorazepam | Acute anxiety, seizures | 0.5–2 mg | PO/IM/IV | Q4–8h PRN | Short-term only; dependence risk |
| Varenicline | Smoking cessation | 0.5 mg daily x 3 days, 0.5 mg BID days 4–7, 1 mg BID thereafter | PO | Daily-BID | 12 weeks; start 1 week before quit date |
| Nicotine patch | Smoking cessation | 21 mg/14 mg/7 mg (step-down) | Transdermal | Daily | 8–12 weeks; combine with short-acting NRT |
| Nicotine gum | Smoking cessation | 2 mg (< 25 cig/day) or 4 mg (>= 25 cig/day) | PO | q1–2h x 6 weeks, taper | Max 24 pieces/day; chew-and-park |
| Terbinafine | Onychomycosis, tinea | 250 mg (systemic) | PO | Daily | 6 wks fingernails; 12 wks toenails |
| Fluconazole | Tinea versicolor, onychomycosis, candidiasis | 150–300 mg | PO | Weekly (onychomycosis) or single dose | Duration per indication |
| Tretinoin | Acne (comedonal/inflammatory) | 0.025–0.1% | Topical | Nightly | Purging at 4–6 weeks; SPF required |
| Doxycycline (acne) | Moderate-severe acne | 50–100 mg | PO | BID | Max 3 months; use with BPO |
| Colchicine | Acute gout | 1.2 mg, then 0.6 mg 1h later; maintenance 0.6 mg BID-TID | PO | Per protocol | Reduce dose in CKD; watch CYP3A4 drugs |
| Allopurinol | Chronic gout (ULT) | Start 100 mg daily; titrate to target UA < 6 mg/dL | PO | Daily | HLA-B*5801 in Asian patients |
| Febuxostat | Chronic gout (ULT, allopurinol-intolerant) | 40–80 mg | PO | Daily | CV mortality warning; avoid if CV disease |
| Prednisone | Acute gout (if NSAIDs/colchicine contraindicated); acute back pain (short course) | 40 mg x 5 days, then taper | PO | Daily | Short course; taper if > 5 days |
| Naproxen | Acute/chronic pain, gout, OA, LBP | 500 mg | PO | BID | Add PPI if GI risk; avoid in CKD |
| Ibuprofen | Acute/chronic pain, fever | 400–800 mg | PO | TID-QID | With food; avoid in CKD, peptic ulcer |
| Cyclobenzaprine | Acute LBP (muscle spasm) | 5–10 mg | PO | TID | Short-term (< 2 weeks); sedating; avoid in elderly |
| Levonorgestrel (Plan B) | Emergency contraception | 1.5 mg | PO | Single dose | Within 72 hours; less effective > 75 kg |
| Ulipristal (ella) | Emergency contraception | 30 mg | PO | Single dose | Within 120 hours; Rx required |
| Metronidazole | H. pylori, BV, C. diff, trichomoniasis | 250–500 mg | PO | BID-QID | Avoid alcohol (disulfiram-like reaction) |
| Naltrexone | Alcohol use disorder, OUD | 50 mg daily (AUD); 380 mg IM monthly (Vivitrol for AUD/OUD) | PO or IM | Daily or monthly | Contraindicated if current opioid dependence |
| Buprenorphine/naloxone (Suboxone) | Opioid use disorder (MAT) | Individualized; typically 8/2 mg to 24/6 mg daily | SL | Daily | Standard DEA registration now sufficient |

---

## Clinical Pearls — Summary

- USPSTF recommends colorectal cancer screening starting at age 45 (downgraded from 50) — counsel all patients 45–75.
- Cervical cancer screening in women who have had total hysterectomy for benign disease does NOT require continued Pap smears.
- Stage 1 hypertension by ACC/AHA (130–139/80–89) warrants lifestyle modification for 3 months before initiating pharmacotherapy in low-risk patients; high-risk patients start immediately.
- Chlorthalidone is preferred over HCTZ for hypertension control — better 24-hour coverage and stronger evidence for CV outcomes.
- In diabetic patients and CKD with proteinuria, ACEi or ARB is first-line regardless of BP — these agents have renoprotective benefit beyond BP control.
- Never combine ACEi + ARB — increased adverse events without additional benefit (ONTARGET).
- Do not use fibrates with statins routinely — exception is fenofibrate, which has lower interaction risk with statins compared to gemfibrozil.
- Stool antigen or urea breath test is preferred for confirming H. pylori eradication — serology cannot confirm cure.
- For IBS-D, rifaximin 550 mg TID x 14 days can be repeated if symptoms recur (up to 2 courses per year).
- PHQ-9 item 9 (suicidality) > 0 always requires direct inquiry regardless of total score.
- Varenicline (Chantix) remains the single most effective pharmacotherapy for smoking cessation; start 1 week before quit date.
- Copper IUD is the most effective emergency contraceptive (> 99%) and can be used in patients for whom levonorgestrel EC is less effective due to body weight.
- Rosacea subtypes require different treatments; topical brimonidine reduces erythema but does not treat papulopustular lesions.
- Combined OCPs are category 4 (absolute contraindication) in migraine with aura — switch to progestin-only method or non-hormonal method.
- AUDIT-C threshold differs by sex: >= 3 for women, >= 4 for men.
- Do not start allopurinol during an acute gout attack; wait 2–4 weeks. Likewise, do not stop established allopurinol during an attack.
- HLA-B*5801 testing is recommended in patients of Han Chinese, Thai, or Korean ancestry before starting allopurinol due to significantly elevated risk of severe cutaneous adverse reactions (SJS/TEN).
- For uncomplicated UTI, fluoroquinolones are no longer first-line — reserve for complicated infections and pyelonephritis to preserve efficacy and avoid C. diff risk.
- Isotretinoin is only prescribed through the FDA iPLEDGE program; two forms of contraception and monthly negative pregnancy tests required for women of reproductive potential.

---

*End of primary_care.md knowledge base — all content intended for RAG-assisted clinical decision support, not as a substitute for clinical judgment or formal guidelines.*
