# Renal Disease: Comprehensive Clinical Knowledge Base

**Domain:** Nephrology — Clinical Reference  
**Scope:** CKD, AKI, Electrolytes, Acid-Base, GN, RRT, Drug Dosing, Nephrolithiasis, PKD, RAS  
**RAG Settings:** Chunk size 1500, overlap 200, Top K 5  

---

## Table of Contents

1. CKD Staging and Management
2. Acute Kidney Injury
3. Electrolyte Disorders
4. Acid-Base Disorders
5. Glomerulonephritis
6. Renal Replacement Therapy
7. Drug Dosing in Renal Impairment
8. Nephrolithiasis
9. Polycystic Kidney Disease
10. Renal Artery Stenosis

---

## CKD Staging and Management

### Definition

Chronic kidney disease (CKD) is defined as abnormalities of kidney structure or function present for more than 3 months, with implications for health. CKD is classified by cause, GFR category (G1-G5), and albuminuria category (A1-A3) per KDIGO 2012 guidelines.

### KDIGO CKD Classification: GFR Categories

| GFR Category | GFR (mL/min/1.73m2) | Description |
|---|---|---|
| G1 | >=90 | Normal or high |
| G2 | 60-89 | Mildly decreased |
| G3a | 45-59 | Mildly to moderately decreased |
| G3b | 30-44 | Moderately to severely decreased |
| G4 | 15-29 | Severely decreased |
| G5 | <15 | Kidney failure (or dialysis) |

### KDIGO CKD Classification: Albuminuria Categories

| Albuminuria Category | AER (mg/24h) | ACR (mg/mmol) | ACR (mg/g) | Description |
|---|---|---|---|---|
| A1 | <30 | <3 | <30 | Normal to mildly increased |
| A2 | 30-300 | 3-30 | 30-300 | Moderately increased |
| A3 | >300 | >30 | >300 | Severely increased (includes nephrotic range) |

### CKD Risk Stratification Heat Map

Risk of CKD progression and adverse outcomes is assessed by combining GFR and albuminuria categories:

| | A1 (<30 mg/g) | A2 (30-300 mg/g) | A3 (>300 mg/g) |
|---|---|---|---|
| G1 (>=90) | Low | Moderately increased | High |
| G2 (60-89) | Low | Moderately increased | High |
| G3a (45-59) | Moderately increased | High | Very high |
| G3b (30-44) | High | Very high | Very high |
| G4 (15-29) | Very high | Very high | Very high |
| G5 (<15) | Very high | Very high | Very high |

- Low risk: no CKD if no other markers
- Moderately increased, High, Very high: refer to nephrology based on trajectory and comorbidities

### CKD-EPI Equation (2021)

The CKD-EPI creatinine equation (2021 version, race-free) is the preferred method for estimating GFR in adults:

**eGFR = 142 x min(Scr/kappa, 1)^alpha x max(Scr/kappa, 1)^(-1.200) x 0.9938^Age x (1.012 if female)**

Where:
- Scr = serum creatinine in mg/dL
- kappa = 0.7 for females, 0.9 for males
- alpha = -0.241 for females, -0.302 for males
- Age in years

**Key interpretation points:**
- eGFR <60 for 3+ months = CKD, regardless of other markers
- eGFR should NOT be used to adjust drug doses when Scr is unstable (use Cockcroft-Gault)
- CKD-EPI 2021 removes race coefficient; previously Black race was a multiplier of 1.159
- Cystatin C-based eGFR (CKD-EPI 2012 CysC) may be more accurate in certain populations (muscle wasting, obesity, amputation)

### Cockcroft-Gault Equation (Drug Dosing)

**CrCl (mL/min) = [(140 - Age) x Weight (kg)] / [72 x Scr (mg/dL)]**  
Multiply by 0.85 for females.

**Clinical use notes:**
- Use ideal body weight (IBW) for obese patients unless actual < IBW
- IBW (male) = 50 kg + 2.3 kg per inch over 5 feet
- IBW (female) = 45.5 kg + 2.3 kg per inch over 5 feet
- Use adjusted body weight (ABW) = IBW + 0.4(actual - IBW) in morbidly obese if actual > 130% of IBW
- Cockcroft-Gault is used for FDA drug labeling and pharmacy dosing decisions; CKD-EPI is used for CKD staging and risk assessment

### CKD Progression: Slowing Strategies

#### RAAS Blockade

**ACE inhibitors (ACEi) and angiotensin receptor blockers (ARBs)** are the cornerstone of renoprotection in CKD with proteinuria:

- Indicated when ACR >300 mg/g (or >30 mg/g in diabetic CKD)
- Reduce intraglomerular pressure by dilating the efferent arteriole
- Trials: REIN (ramipril), IDNT (irbesartan in T2DM), RENAAL (losartan in T2DM), AASK (ramipril in hypertensive CKD)
- **Do NOT combine ACEi + ARB:** ONTARGET trial showed no added renoprotective benefit and increased risk of hyperkalemia, AKI, and hypotension
- Do not use aliskiren (direct renin inhibitor) in combination with ACEi/ARB
- Monitor potassium and creatinine within 1-2 weeks of initiation or dose change
- An initial rise in Scr up to 30% is acceptable and expected (reflects hemodynamic effect, not worsening CKD)
- Hold or reduce dose if hyperkalemia (K >5.5 mEq/L) or Scr rises >30% above baseline

#### SGLT2 Inhibitors (Renal Outcome Trials)

SGLT2 inhibitors have become first-line renoprotective agents independent of diabetes status:

**Dapagliflozin (Farxiga):**
- DAPA-CKD trial (2020): dapagliflozin 10 mg/day in CKD (eGFR 25-75, ACR >200 mg/g) reduced sustained 50% decline in eGFR, ESKD, or renal/CV death by 39% (HR 0.61, p<0.001)
- Benefit seen regardless of T2DM status
- FDA approved for CKD (non-diabetic and diabetic) to reduce CKD progression and CV death
- Do not initiate if eGFR <25 mL/min; can continue if already on it when eGFR drops further

**Empagliflozin (Jardiance):**
- EMPA-KIDNEY trial (2022): empagliflozin 10 mg/day in CKD (eGFR 20-90 with ACR >200, or eGFR 20-45 regardless of ACR) reduced kidney disease progression or CV death by 28% (HR 0.72)
- Benefit in broad CKD population including non-diabetic and lower eGFR range
- EMPEROR-Reduced: renal protection in HFrEF population

**Mechanism of renoprotection:**
- Reduces glomerular hyperfiltration via tubuloglomerular feedback (afferent arteriole constriction)
- Lowers intraglomerular pressure (complementary to, not duplicate of, RAAS blockade)
- Anti-inflammatory and antifibrotic effects
- Metabolic effects: reduced uric acid, weight, blood pressure

**Safety in CKD:**
- Glycemic-lowering effect diminishes as eGFR declines
- Risk of euglycemic DKA: hold perioperatively, with prolonged fasting, or in sick day protocol
- Genital mycotic infections: common side effect
- UTI risk: moderate; avoid in recurrent UTI
- Volume depletion: monitor especially when combined with diuretics

#### Blood Pressure Target

- Target BP <130/80 mmHg per AHA/ACC 2017 and KDIGO 2021 guidelines
- SPRINT trial (non-diabetic, non-stroke): intensive SBP target <120 mmHg reduced CV events but higher AKI rate
- ACCORD (diabetic): intensive BP target did not reduce CV events
- Preferred agents in CKD with proteinuria: ACEi or ARB first-line
- Second-line: dihydropyridine calcium channel blockers (amlodipine), thiazide or thiazide-like diuretics (chlorthalidone preferred over HCTZ)
- Loop diuretics if GFR <30 or volume overload
- Avoid non-dihydropyridine CCBs (verapamil, diltiazem) as first-line

### CKD Complications Management

#### Anemia of CKD

**Definition:** Hemoglobin <13 g/dL in males, <12 g/dL in females, due primarily to reduced EPO production

**Workup before treating:**
- Confirm iron stores: serum ferritin, transferrin saturation (TSAT)
- Functional iron deficiency: TSAT <20%, ferritin <100 ng/mL (non-dialysis) or <200 ng/mL (dialysis)
- Absolute iron deficiency: ferritin <30 ng/mL
- Exclude other causes: B12, folate deficiency, occult blood loss, hemolysis

**Iron Supplementation:**
- Non-dialysis CKD: oral iron preferred first (ferrous sulfate 325 mg TID); IV iron if intolerant, non-adherent, or inadequate response
- Dialysis patients: IV iron preferred due to poor oral absorption with uremia and dialysis losses
- IV iron formulations: ferric gluconate (Ferrlecit), iron sucrose (Venofer), ferumoxytol (Feraheme), ferric carboxymaltose (Injectafer)
- Target: TSAT 20-50%, ferritin 100-500 ng/mL (non-dialysis), ferritin 200-500 ng/mL (dialysis)
- Avoid IV iron if active bacterial infection

**Erythropoiesis Stimulating Agents (ESAs):**

| Agent | Route | Frequency | Half-life |
|---|---|---|---|
| Epoetin alfa (Epogen, Procrit) | SC or IV | 3x/week or weekly | 4-13 hours (SC), 8.5 hours (IV) |
| Darbepoetin alfa (Aranesp) | SC or IV | Every 1-2 weeks | 25 hours (SC), 21 hours (IV) |
| Methoxy polyethylene glycol-epoetin beta (Mircera) | SC or IV | Monthly | 134 hours |

- Initiate ESA when Hgb <10 g/dL after iron replete
- Target Hgb 10-11.5 g/dL; do NOT target >13 g/dL (increased stroke, thromboembolic risk — TREAT, CHOIR trials)
- Black box warning: increased mortality, MI, stroke, thromboembolism at Hgb >13 g/dL
- Starting dose epoetin alfa: 50-100 units/kg SC 3x/week
- Starting dose darbepoetin: 0.45 mcg/kg SC every 4 weeks (non-dialysis)
- ESA resistance: assess iron stores, inflammation, hyperparathyroidism, aluminum toxicity, hemoglobinopathy

#### Metabolic Acidosis in CKD

**Definition:** Serum bicarbonate <22 mEq/L in CKD context

**Pathophysiology:**
- Reduced ammoniagenesis and acid excretion
- Acid accumulation promotes protein catabolism, bone dissolution, muscle wasting, accelerated GFR decline, and hyperkalemia

**Treatment:**
- Target serum bicarbonate >22 mEq/L (KDIGO recommends 22-26 mEq/L)
- Sodium bicarbonate tablets: 650 mg (7.7 mEq HCO3) or 325 mg; typical dose 1-3 tabs TID
- Sodium citrate/citric acid (Shohl solution, Bicitra): 1 mEq HCO3 equivalent per mL
- Veverimer (Tiopronin derivative — experimental, Phase 3 trials): oral hydrochloric acid scavenger
- Monitor sodium load in hypertensive or volume-overloaded patients
- GFR effect: NKF-KDOQI and multiple RCTs suggest bicarb supplementation slows CKD progression (SRC trial, BICAR-ICU for AKI)

#### Secondary Hyperparathyroidism (SHPT) and CKD-Mineral Bone Disease

**Pathophysiology cascade:**
1. Reduced GFR → phosphate retention → decreased calcitriol (1,25-OH2-D3) synthesis
2. Low calcitriol → decreased calcium absorption → hypocalcemia
3. Hypocalcemia + hyperphosphatemia + low calcitriol → PTH secretion increases
4. Chronic stimulation leads to parathyroid gland hyperplasia
5. FGF-23 rises early (before PTH) to promote phosphaturia; eventually ineffective

**CKD-MBD complications:**
- Renal osteodystrophy (osteitis fibrosa cystica, adynamic bone disease, osteomalacia)
- Vascular and soft tissue calcification (coronary, valvular)
- Fractures, bone pain

**Monitoring (KDIGO guidelines):**

| Parameter | CKD G3a-G3b | CKD G4 | CKD G5/Dialysis |
|---|---|---|---|
| Calcium | Every 6-12 months | Every 3-6 months | Every 1-3 months |
| Phosphate | Every 6-12 months | Every 3-6 months | Every 1-3 months |
| PTH | Based on baseline/CKD stage | Every 6-12 months | Every 3-6 months |
| ALP | Annually | Every 6-12 months | Every 12 months |
| 25-OH Vitamin D | Once, then based on results | | |

**Phosphate Control:**
- Dietary phosphate restriction: limit to 800-1000 mg/day
- Phosphate binders (with meals):
  - Calcium-based (first-line if hypocalcemic): calcium carbonate (Tums), calcium acetate (PhosLo)
  - Avoid excess calcium: do not exceed 1500 mg/day elemental calcium from binders
  - Non-calcium binders (preferred if hypercalcemia, vascular calcification, PTH suppressed):
    - Sevelamer carbonate (Renvela): also reduces LDL, uric acid
    - Lanthanum carbonate (Fosrenol): chew with meals
    - Sucroferric oxyhydroxide (Velphoro): iron-based, low systemic absorption
    - Ferric citrate (Auryxia): also treats iron deficiency anemia

**Vitamin D:**
- Nutritional vitamin D (ergocalciferol/cholecalciferol): replete 25-OH-D level if <30 ng/mL
- Active vitamin D analogs (calcitriol, paricalcitol, doxercalciferol): suppress PTH; use when PTH elevated despite nutritional D repletion and phosphate control
  - Calcitriol (Rocaltrol): 0.25-0.5 mcg/day
  - Paricalcitol (Zemplar): reduced hypercalcemia risk vs calcitriol
  - Doxercalciferol (Hectorol): prodrug, converted to calcitriol

**Cinacalcet (Sensipar) — Calcimimetic:**
- Activates calcium-sensing receptor (CaSR) on parathyroid cells → reduced PTH secretion
- Indicated for dialysis patients with elevated PTH (SHPT); also used for primary hyperparathyroidism
- Starting dose: 30 mg daily with food, titrate to 180 mg/day maximum
- Monitor: calcium (can cause hypocalcemia), phosphate, PTH
- EVOLVE trial: did not reduce mortality in dialysis patients, but reduced fractures and parathyroidectomy rates
- Etelcalcetide (Parsabiv): IV calcimimetic administered at dialysis sessions, more convenient for HD patients

**Parathyroidectomy:**
- Indicated for severe refractory SHPT (PTH >1000 pg/mL) not responding to medical therapy
- Also indicated if calciphylaxis present
- Subtotal vs total parathyroidectomy with autotransplantation (forearm)
- Post-op "hungry bone syndrome": severe hypocalcemia requiring aggressive IV calcium replacement

---

## Acute Kidney Injury

### Definition and Staging

AKI is defined by any of the following (KDIGO 2012):
- Rise in serum creatinine >=0.3 mg/dL within 48 hours
- Rise in serum creatinine to >=1.5x baseline within 7 days
- Urine output <0.5 mL/kg/hr for >=6 hours

### KDIGO AKI Staging

| Stage | Serum Creatinine Criteria | Urine Output Criteria |
|---|---|---|
| 1 | Rise >=0.3 mg/dL OR 1.5-1.9x baseline | <0.5 mL/kg/hr for 6-12 hours |
| 2 | 2.0-2.9x baseline | <0.5 mL/kg/hr for >=12 hours |
| 3 | >=3.0x baseline OR >=4.0 mg/dL with acute rise >=0.5 mg/dL OR initiation of RRT OR eGFR <35 in patients <18 years | <0.3 mL/kg/hr for >=24 hours OR anuria for >=12 hours |

### Classification: Prerenal vs Intrinsic vs Postrenal

| Parameter | Prerenal | Intrinsic (ATN) | Postrenal |
|---|---|---|---|
| BUN:Cr ratio | >20:1 | <10-15:1 | Variable |
| FeNa | <1% | >2% | Variable |
| Urine osmolality | >500 mOsm/kg | <350 mOsm/kg | Variable |
| Urine sodium | <20 mEq/L | >40 mEq/L | Variable |
| Urine sediment | Normal or hyaline casts | Muddy brown granular casts, renal tubular epithelial cells | Normal or RBCs if stone/tumor |
| Response to fluids | Improves | Minimal improvement | Improves after decompression |

**FeNa (Fractional Excretion of Sodium):**

FeNa (%) = [(Urine Na x Plasma Cr) / (Plasma Na x Urine Cr)] x 100

- <1%: Prerenal (kidney conserving sodium — intact tubular function)
- >2%: Intrinsic renal damage (ATN — tubular injury impairs sodium reabsorption)
- 1-2%: Indeterminate; consider FEUrea if patient on diuretics

**FEUrea:**

FEUrea (%) = [(Urine Urea x Plasma Cr) / (Plasma Urea x Urine Cr)] x 100

- <35%: Prerenal (more useful when patient is on loop diuretics)
- >50%: ATN

**BUN:Creatinine ratio:**
- >20:1: Prerenal (or upper GI bleed, hypercatabolism, high protein intake, corticosteroids)
- <10:1: Intrinsic renal, liver disease, malnutrition

### Prerenal AKI Management

- Volume depletion: isotonic crystalloid resuscitation (normal saline or lactated Ringer; LR preferred to avoid hyperchloremic acidosis in large volumes)
- Cardiac output reduction (cardiorenal syndrome): diuresis and/or inotropes; avoid fluid overload
- Distributive shock (sepsis): vasopressors (norepinephrine first-line) + fluid resuscitation
- Hepatorenal syndrome: terlipressin (or norepinephrine), albumin 1g/kg/day; avoid nephrotoxins
- Hold ACEi/ARB, NSAIDs, diuretics during AKI until volume status optimized

### Intrinsic AKI: Acute Tubular Necrosis (ATN)

**Ischemic ATN:**
- Most common intrinsic AKI in hospitalized patients
- Follows prolonged prerenal state, sepsis, major surgery, cardiogenic/distributive shock
- Muddy brown granular casts on urinalysis ("dirty brown casts")
- Course: oliguric phase (1-2 weeks) → diuretic phase (polyuria as tubules recover) → recovery phase
- Management: supportive; optimize hemodynamics, avoid additional nephrotoxins, adjust drug doses, nutrition

**Nephrotoxic ATN:**

| Nephrotoxin | Mechanism | Prevention/Management |
|---|---|---|
| Aminoglycosides | Proximal tubule toxicity (accumulation) | Once-daily dosing, monitor levels, avoid prolonged use |
| Vancomycin | Oxidative tubular injury; AUC-based toxicity | AUC/MIC-guided dosing (target AUC 400-600), avoid nephrotoxin combos |
| Cisplatin | Direct tubular toxicity | Aggressive pre/post hydration, amifostine (limited evidence) |
| Amphotericin B | Vasoconstriction + direct toxicity | Liposomal formulation (AmBisome) preferred; saline loading |
| NSAIDs | Inhibit prostaglandin-mediated afferent dilation | Avoid in volume depletion, CKD, heart failure |
| Contrast agents | See contrast nephropathy section | |
| Myoglobin | See rhabdomyolysis section | |

### Intrinsic AKI: Acute Interstitial Nephritis (AIN)

**Pathophysiology:** Immune-mediated inflammatory infiltrate in the renal interstitium; tubular injury secondary

**Classic triad (present in <10% of cases):** fever, rash, eosinophilia

**Common drug causes:**

| Drug Class | Examples |
|---|---|
| Proton pump inhibitors (most common drug cause) | Omeprazole, pantoprazole, esomeprazole |
| NSAIDs | Ibuprofen, naproxen, ketorolac |
| Beta-lactam antibiotics | Penicillin, ampicillin, methicillin, cephalosporins |
| Sulfonamides | TMP-SMX |
| Quinolones | Ciprofloxacin, levofloxacin |
| Rifampin | Rifampin |
| Allopurinol | Allopurinol |
| Immune checkpoint inhibitors | Nivolumab, pembrolizumab |

**Urinalysis findings:**
- Sterile pyuria (WBCs without bacteria)
- WBC casts (highly specific for AIN or pyelonephritis)
- Eosinophiluria (Hansel stain): low sensitivity (30%), but when present suggests AIN
- Mild proteinuria (<2 g/day)

**Diagnosis:** Renal biopsy (gold standard); clinical diagnosis often used when biopsy not feasible

**Management:**
- Discontinue offending agent (most important step)
- Corticosteroids if no improvement within 1-2 weeks after drug removal: prednisone 1 mg/kg/day (max 60 mg) for 4-6 weeks, then taper
- Early steroid initiation associated with better renal recovery
- Monitor creatinine and urine findings

### Intrinsic AKI: ANCA Vasculitis

- Pauci-immune rapidly progressive glomerulonephritis (RPGN)
- MPO-ANCA (anti-myeloperoxidase): associated with microscopic polyangiitis (MPA), eosinophilic GPA (EGPA)
- PR3-ANCA (anti-proteinase 3): associated with granulomatosis with polyangiitis (GPA, Wegener)
- Presentation: hematuria, RBC casts, rapidly rising creatinine, systemic vasculitis features
- Biopsy: necrotizing crescentic GN, pauci-immune (no/minimal immune deposits)
- Treatment: cyclophosphamide (IV or oral) + high-dose glucocorticoids (IV methylprednisolone 500-1000 mg x3 pulses, then oral prednisone 1 mg/kg)
- Rituximab: non-inferior to cyclophosphamide for induction (RAVE, RITUXVAS trials); preferred for relapsing disease and fertility concerns
- Plasma exchange: PEXIVAS trial showed no mortality benefit over standard immunosuppression
- Maintenance: azathioprine or rituximab; taper steroids

### Intrinsic AKI: Anti-GBM Disease (Goodpasture Syndrome)

- Autoantibodies against alpha-3 chain of type IV collagen (GBM and alveolar basement membrane)
- Presentation: rapidly progressive GN + pulmonary hemorrhage (classic Goodpasture); renal-limited anti-GBM disease also occurs
- Biopsy: linear IgG deposits on immunofluorescence (pathognomonic)
- Treatment: plasmapheresis (daily for 2-3 weeks, removes anti-GBM antibodies) + cyclophosphamide + high-dose steroids
- Prognosis: if Scr >6 mg/dL at presentation or dialysis dependent, renal recovery unlikely; lung hemorrhage responds well to treatment

### Intrinsic AKI: TTP and HUS

**Thrombotic Thrombocytopenic Purpura (TTP):**
- Pentad (not all required): microangiopathic hemolytic anemia (MAHA), thrombocytopenia, neurological symptoms, fever, renal impairment
- ADAMTS13 deficiency (activity <10%): immune (antibody against ADAMTS13) or congenital (Upshaw-Schulman syndrome)
- Treatment: emergency plasma exchange (PEX) + steroids + rituximab (caplacizumab for acute episodes — anti-VWF nanobody)
- Do NOT transfuse platelets (worsens thrombosis) unless life-threatening bleeding

**Hemolytic Uremic Syndrome (HUS):**
- Classic (typical): Shiga toxin-producing E. coli O157:H7 (STEC-HUS); children most affected; diarrhea prodrome
  - Supportive care; avoid antibiotics (may worsen Shiga toxin release)
- Atypical HUS (aHUS): complement dysregulation (mutations in factor H, I, C3, MCP/CD46, or antibodies)
  - Treatment: eculizumab (anti-C5 complement inhibitor) — dramatic improvement; meningococcal vaccination mandatory before eculizumab

### Contrast-Induced Nephropathy (CIN) / Contrast-Associated AKI

**Definition:** Rise in Scr >=0.3 mg/dL or >=25% within 48-72 hours of iodinated contrast administration

**Risk factors:**
- CKD (eGFR <60, especially <30)
- Diabetes mellitus
- Volume depletion
- Heart failure
- Large contrast volumes
- Intra-arterial contrast (higher risk than IV)
- NSAIDs, concurrent nephrotoxins
- Hemodynamic instability

**Prevention strategies:**
- IV hydration: isotonic saline (1-1.5 mL/kg/hr for 3-12 hours before and after) is the most evidence-based intervention
- Use minimum effective contrast volume
- Use iso-osmolar or low-osmolar contrast (rather than high-osmolar)
- N-acetylcysteine (NAC, Mucomyst): 1200 mg PO BID x2 days; evidence is weak and conflicting (ACT trial negative); still widely used due to safety profile
- Sodium bicarbonate: not superior to saline (PRESERVE trial negative)
- Metformin: hold 48 hours before and after contrast in patients with eGFR <60 (or at time of procedure if emergent); risk of lactic acidosis in AKI
- Statins: rosuvastatin or atorvastatin peri-procedure may reduce CIN (PRATO-ACS, STATIN-AKI trials)
- Avoid NSAIDS and nephrotoxins peri-procedure

**Important note:** The term "contrast-associated AKI" is preferred over "contrast-induced" as causality is often confounded by the underlying condition requiring contrast imaging.

### Postrenal AKI (Obstructive Nephropathy)

**Causes:**
- Bladder outlet obstruction: benign prostatic hyperplasia (BPH), prostate cancer, urethral stricture, neurogenic bladder
- Ureteral obstruction: nephrolithiasis, malignancy (cervical, colorectal, lymphoma), retroperitoneal fibrosis, surgical ligation
- Intrarenal obstruction: crystals (uric acid, acyclovir, methotrexate, indinavir), cast nephropathy (multiple myeloma)

**Diagnosis:**
- Bladder ultrasound (bedside): immediate assessment for bladder distension
- Renal ultrasound: hydronephrosis (may be absent early or with retroperitoneal fibrosis)
- Foley catheter placement: diagnose and treat bladder outlet obstruction simultaneously
- CT urogram: stone localization, ureteral anatomy

**Management:**
- Bladder outlet obstruction: Foley catheter; urology consult for definitive management
- Ureteral obstruction: urology consult for ureteral stent or percutaneous nephrostomy tube
- Post-obstructive diuresis: monitor urine output; replace 50-75% of output with 0.45% NaCl to prevent severe electrolyte derangements and volume depletion

### Indications for Urgent Dialysis: AEIOU Mnemonic

| Letter | Indication | Details |
|---|---|---|
| A | Acidosis | pH <7.1-7.2, refractory to medical management |
| E | Electrolytes | Hyperkalemia >6.5 mEq/L refractory to treatment, hyponatremia/hypernatremia refractory |
| I | Ingestions/Intoxications | Lithium, methanol, ethylene glycol, salicylates, theophylline (dialyzable toxins) |
| O | Overload (fluid) | Pulmonary edema, fluid overload refractory to diuretics |
| U | Uremia | Encephalopathy, pericarditis, bleeding (platelet dysfunction), nausea/vomiting |

### Rhabdomyolysis

**Definition:** Breakdown of skeletal muscle with release of myoglobin and intracellular contents into circulation

**Causes:** Trauma, prolonged immobilization, extreme exercise, seizure, hypo/hyperthermia, alcohol, drugs (statins, cocaine, heroin), electrolyte disorders (hypokalemia, hypophosphatemia), inflammatory myopathies, infections

**Diagnosis:**
- Elevated CPK: typically >1000 U/L; AKI risk significantly increases at >5000 U/L; severe cases >100,000 U/L
- Brown/cola-colored urine (myoglobinuria): dipstick positive for blood but no RBCs on microscopy
- Elevated BUN, creatinine (disproportionately elevated Cr due to creatine release from muscle)
- Hyperkalemia, hyperphosphatemia, hypocalcemia (early), hypercalcemia (late recovery)
- Elevated LDH, AST, ALT (hepatocyte marker but also released from muscle)

**Management:**
- Aggressive IV fluid resuscitation: isotonic saline (0.9% NaCl); target urine output 200-300 mL/hr
- Large fluid volumes often required: initial bolus 1-2 L, then 200-1000 mL/hr
- Monitor urine output closely; place Foley catheter only if oliguric (to distinguish from AUO)
- Urinary alkalinization (sodium bicarbonate infusion to urine pH >6.5): theoretical benefit — prevents myoglobin cast formation; clinical evidence limited but widely practiced
- Mannitol: osmotic diuretic; used in compartment syndrome and severe cases (evidence limited)
- Treat hyperkalemia aggressively
- Dialysis: if AKI with refractory electrolyte disturbances or fluid overload
- Treat underlying cause; fasciotomy if compartment syndrome

---

## Electrolyte Disorders

### Hyponatremia

**Definition:** Serum sodium <135 mEq/L

**Classification by tonicity:**
- Hypotonic hyponatremia (true hyponatremia): serum osmolality <275 mOsm/kg (most clinically significant)
- Isotonic hyponatremia (pseudohyponatremia): extreme hyperlipidemia or hyperproteinemia (lab artifact; true osmolality normal)
- Hypertonic hyponatremia: hyperglycemia, mannitol (osmotic shift of water out of cells)
  - Correct for glucose: Na rises 1.6 mEq/L (or 2.4 mEq/L per some sources) for each 100 mg/dL rise in glucose above 100

**Classification by volume status:**

| Type | Presentation | Urine Na | Urine Osm | Cause |
|---|---|---|---|---|
| Hypovolemic | Dry mucous membranes, decreased skin turgor, orthostasis | <20 mEq/L | >500 mOsm/kg | GI losses, sweating, adrenal insufficiency |
| Hypovolemic with renal losses | Same + renal wasting | >20 mEq/L | Variable | Diuretics, RTA, cerebral/renal salt wasting |
| Euvolemic (SIADH most common) | Mild edema or no edema | >40 mEq/L | >100 mOsm/kg (inappropriately concentrated) | SIADH, hypothyroidism, adrenal insufficiency |
| Hypervolemic | Edema, ascites, JVD | <20 mEq/L | >500 mOsm/kg | CHF, cirrhosis, nephrotic syndrome |
| Hypervolemic with renal failure | Same + uremia | >20 mEq/L | Variable | ESRD, AKI |

#### SIADH Diagnostic Criteria

All of the following must be met:
1. Hypotonic hyponatremia (serum Na <135, serum Osm <275)
2. Urine osmolality >100 mOsm/kg (inappropriately concentrated)
3. Urine sodium >40 mEq/L on normal salt/fluid intake (kidney not conserving sodium)
4. Clinically euvolemic (no edema, no dehydration)
5. Normal adrenal, renal, and thyroid function
6. Not on diuretics

**Common causes of SIADH:**

| Category | Examples |
|---|---|
| CNS disorders | Meningitis, encephalitis, SAH, stroke, head trauma, brain tumor |
| Pulmonary disorders | Pneumonia, lung abscess, COPD, positive pressure ventilation, TB |
| Malignancy | Small cell lung cancer (ectopic ADH), pancreatic, duodenal, brain tumors |
| Drugs | SSRIs, SNRIs, TCAs, carbamazepine, oxcarbazepine, antipsychotics, opioids, NSAIDs, PPIs, cyclophosphamide, MDMA ("Ecstasy") |
| Postoperative | Especially in elderly after major surgery |
| Pain, nausea | Strong ADH stimulants |

#### Hyponatremia Treatment

**Symptomatic (severe): seizures, coma, respiratory arrest**
- 3% NaCl (hypertonic saline): 100-150 mL IV bolus over 10-20 minutes; can repeat x2 (total up to 300 mL boluses)
- Alternatively: continuous infusion; calculate sodium deficit and run to correct by 1-2 mEq/L/hr until symptoms resolve
- Goal: raise sodium by 4-6 mEq/L in first 2 hours (symptoms should improve)

**Correction rate limits (prevent osmotic demyelination syndrome, ODS):**
- Maximum 8-10 mEq/L per 24 hours in patients at risk for ODS
- Risk factors for ODS: severe hyponatremia (<120 mEq/L), chronic hyponatremia (>48 hours), alcoholism, malnutrition, hypokalemia, liver disease
- If overcorrected: give desmopressin (DDAVP) 2-4 mcg IV + D5W infusion to lower sodium back down
- Monitor sodium every 2-4 hours during active correction

**Asymptomatic hyponatremia:**
- Hypovolemic: IV isotonic saline; correct underlying cause
- Euvolemic (SIADH): fluid restriction (800-1000 mL/day first-line)
- Hypervolemic: fluid restriction + treat underlying cause; loop diuretics for volume overload

**Chronic SIADH management:**
- Fluid restriction: first-line (800-1000 mL/day); difficult for patient compliance
- Oral urea: 15-30 g/day in water; promotes osmotic diuresis; cheap, effective
- Salt tablets: NaCl 1-3 g TID with liberal fluid intake
- Tolvaptan (Samsca): V2 receptor antagonist (vaptans); causes aquaresis (free water excretion without sodium loss); 15 mg/day PO, titrate to 60 mg
  - Do NOT use in liver disease (hepatotoxicity) or initiate in hospital setting (rapid overcorrection risk)
  - SALT trials demonstrated efficacy
- Demeclocycline: induces nephrogenic DI; rarely used due to nephrotoxicity risk

---

### Hypernatremia

**Definition:** Serum sodium >145 mEq/L; always associated with hyperosmolality; always represents a relative water deficit

**Causes:**

| Category | Causes |
|---|---|
| Pure water loss (insensible) | Fever, burns, hyperventilation, diarrhea in infants |
| Hypotonic fluid loss | Profuse sweating, osmotic diarrhea |
| Central diabetes insipidus (CDI) | Pituitary/hypothalamic injury, surgery, trauma, tumor, ischemia |
| Nephrogenic diabetes insipidus (NDI) | Lithium (most common drug cause), demeclocycline, hypercalcemia, hypokalemia, genetic (V2 receptor or aquaporin-2 mutation) |
| Sodium overload | Hypertonic saline, sodium bicarbonate, TPN, primary hyperaldosteronism |

**Distinguishing CDI vs NDI:**

| Test | CDI | NDI |
|---|---|---|
| Urine osmolality after water deprivation | Low (<300 mOsm/kg) | Low (<300 mOsm/kg) |
| Response to desmopressin (DDAVP) | Urine Osm increases >50% | Minimal increase (<50%) |
| Plasma ADH level | Low | High |

**Free Water Deficit Calculation:**

Free Water Deficit (liters) = TBW x [(serum Na / 140) - 1]

Where TBW = 0.6 x weight (kg) in males; 0.5 x weight (kg) in females; 0.45 in elderly females

**Correction rate and fluids:**
- Maximum correction rate: 10-12 mEq/L per 24 hours (risk of cerebral edema if corrected too rapidly)
- In acute hypernatremia (<48 hours): can correct faster
- Enteral free water: preferred if tolerable (NG tube or PO)
- D5W IV infusion: delivers free water; calculate infusion rate to correct deficit over 48-72 hours
- 0.45% NaCl (half-normal saline): partially corrects free water deficit; used when some sodium replacement needed
- Central DI: desmopressin (DDAVP) intranasal, subcutaneous, or IV; 1-2 mcg SC/IV BID or 10-20 mcg intranasal BID
- Nephrogenic DI: treat underlying cause; low-sodium diet + thiazide diuretics (paradoxically reduce urine output via volume depletion); amiloride for lithium-induced NDI (blocks lithium uptake in collecting duct)
- Monitor serum sodium every 4-6 hours during active correction

**Example calculation:**
- 70 kg male, Na = 165 mEq/L
- TBW = 0.6 x 70 = 42 L
- Deficit = 42 x (165/140 - 1) = 42 x 0.179 = 7.5 L
- Infuse over 48 hours = 7500 mL / 48 = 156 mL/hr D5W (rough estimate; also account for ongoing losses)

---

### Hypokalemia

**Definition:** Serum potassium <3.5 mEq/L

**ECG Changes:**
- Early: flattened/inverted T waves, prominent U waves (after T wave in V2-V3)
- Moderate: ST depression, prolonged QT interval
- Severe: wide QRS, arrhythmias (PVCs, VT, VF)
- U wave > T wave amplitude in any precordial lead is highly suggestive

**Causes:**

| Category | Examples |
|---|---|
| GI losses | Vomiting (metabolic alkalosis, urinary K wasting), diarrhea (direct K loss), NG suction |
| Renal losses | Loop diuretics, thiazide diuretics, hyperaldosteronism, RTA type 1 and 2, Gitelman/Bartter syndrome |
| Transcellular shift (into cells) | Insulin, beta-agonists, alkalosis, hypokalemic periodic paralysis |
| Inadequate intake | Rare; severe malnutrition, eating disorders |
| Refeeding syndrome | Phosphate, potassium, magnesium shift intracellularly with insulin surge |

**Assessing renal vs extrarenal losses:**
- Urine K <20 mEq/day (or urine K:Cr <1.5): extrarenal loss (GI, poor intake)
- Urine K >20 mEq/day: renal wasting (diuretics, hyperaldosteronism, RTA)
- Urine K:Cr ratio and TTKG (transtubular potassium gradient) also used

**Treatment:**

| K Level | Symptoms | Route | Dose |
|---|---|---|---|
| 3.0-3.5 mEq/L | Usually none | Oral | KCl 20-40 mEq 2-3x/day |
| 2.5-3.0 mEq/L | Mild/moderate | Oral or IV | Oral KCl; or IV 10-20 mEq/hr via peripheral IV |
| <2.5 mEq/L | Significant cardiac/neuro | IV (central preferred) | IV KCl up to 20 mEq/hr peripheral, >20 mEq/hr requires central line |

- Maximum IV rate: 10-20 mEq/hr via peripheral; up to 40 mEq/hr via central with cardiac monitoring
- Do not exceed 40 mEq/L concentration via peripheral IV
- IV fluids: do not use dextrose-containing solutions (insulin release shifts K further intracellularly)
- Oral: KCl elixir or slow-release tablets (Klor-Con); typical doses 20-80 mEq/day in divided doses

**Refractory hypokalemia — must correct hypomagnesemia first:**
- Magnesium deficiency impairs Na/K-ATPase, causing obligate renal potassium wasting
- If serum Mg <1.5 mEq/L or symptoms of hypomagnesemia, replace magnesium first
- MgSO4 2 g IV over 1 hour, then oral magnesium oxide 400-800 mg/day

---

### Hyperkalemia

**Definition:** Serum potassium >5.0 mEq/L; critical >6.5 mEq/L

**Pseudohyperkalemia:** Hemolysis during venipuncture, leukocytosis (WBC >100,000), thrombocytosis (Plt >1,000,000); repeat test with rapid processing

**ECG Changes (Progressive with rising K):**

| K Level | ECG Finding |
|---|---|
| 5.5-6.0 mEq/L | Peaked (tall, narrow, symmetric) T waves — earliest sign |
| 6.0-6.5 mEq/L | Prolonged PR interval, flat P waves |
| 6.5-7.0 mEq/L | Widened QRS, bundle branch patterns |
| 7.0-8.0 mEq/L | Sinusoidal ("sine wave") pattern |
| >8.0 mEq/L | VF, asystole |

**Treatment Sequence:**

**Step 1 — Membrane Stabilization (immediate effect):**
- Calcium gluconate 1 g (10 mL of 10% solution) IV over 2-3 minutes
- Onset: 1-3 minutes; duration: 30-60 minutes
- Does NOT lower potassium — protects cardiac membrane
- Repeat if ECG changes persist after 5 minutes
- Calcium chloride 1 g IV (3x more elemental calcium than gluconate) — use via central line (more caustic)
- Use if: peaked T waves, widened QRS, or any ECG change

**Step 2 — Transcellular Shift (onset 15-30 min, temporary):**
- Regular insulin 10 units IV + Dextrose 50% (D50) 25-50 g IV (one amp D50W = 25 g dextrose)
- Lowers K by 0.5-1.5 mEq/L; duration 4-6 hours
- Monitor for hypoglycemia at 1 hour (and 2-3 hours); give additional dextrose if glucose <70 mg/dL
- If glucose already >250 mg/dL, give insulin without dextrose
- Sodium bicarbonate 50-100 mEq IV: shifts K into cells if metabolic acidosis present; less effective in chronic CKD without acidosis; each 0.1 unit rise in pH decreases K by ~0.6 mEq/L
- Albuterol 10-20 mg nebulized (high dose): beta-2 agonism shifts K into cells; lowers K by 0.5-1.5 mEq/L; onset 30-60 min; additive with insulin/dextrose

**Step 3 — Total Body K Removal:**
- Kayexalate (sodium polystyrene sulfonate, SPS): cation exchange resin; poorly supported by evidence; risk of intestinal necrosis especially with sorbitol; 15-30 g PO or PR; onset hours
- Patiromer (Veltassa): potassium binder; well-tolerated; not for acute use (onset 7-24 hours); 8.4 g PO daily, titrate; binds drugs (administer 3+ hours apart)
- Sodium zirconium cyclosilicate (Lokelma): highly selective; fast onset (within 1 hour); 10 g PO TID for acute, then 5-10 g daily for maintenance; can be used in acute setting
- Loop diuretics: furosemide IV (40-80 mg) to increase renal K excretion if oliguric (only effective if renal function present)
- Fludrocortisone: increases tubular K excretion; used in chronic management

**Step 4 — Dialysis (definitive):**
- K >6.5 mEq/L with ECG changes or refractory to above measures
- Anuric/oliguric AKI or ESRD with symptomatic hyperkalemia
- Hemodialysis most efficient; CRRT if hemodynamically unstable

---

### Magnesium Disorders

#### Hypomagnesemia

**Definition:** Serum Mg <1.7 mg/dL (0.7 mmol/L)

**Causes:**
- Increased renal losses: loop and thiazide diuretics (most common drug cause), proton pump inhibitors (PPI-induced hypomagnesemia with chronic use), alcohol, amphotericin B, cisplatin, tacrolimus, cyclosporine, Bartter/Gitelman syndrome
- GI losses: diarrhea, malabsorption, short bowel syndrome, prolonged NG drainage
- Transcellular shift: refeeding syndrome, insulin therapy, hungry bone syndrome post-parathyroidectomy
- Inadequate intake: malnutrition, TPN without Mg supplementation, alcoholism

**Clinical manifestations:**
- Neuromuscular: tremor, tetany, Chvostek/Trousseau signs, hyperreflexia, seizures
- Cardiac: ECG changes (prolonged QT, torsades de pointes), refractory arrhythmias
- Electrolyte effects: refractory hypokalemia (Mg deficiency causes renal K wasting), hypocalcemia (impairs PTH secretion and end-organ PTH response)

**Treatment:**
- Severe or symptomatic (Mg <1.2 or tetany/seizures): MgSO4 2 g IV over 15-60 minutes, then 5-10 g over 24 hours; monitor DTRs (loss of deep tendon reflexes = early toxicity)
- Moderate: MgSO4 1-2 g IV/IM, or oral replacement
- Mild/maintenance: oral magnesium oxide 400-800 mg/day; magnesium glycinate better tolerated (less diarrhea); magnesium citrate
- Note: 50-70% of IV magnesium is excreted by kidney before cellular repletion; multiple doses often needed

#### Hypermagnesemia

**Definition:** Serum Mg >2.5 mg/dL; clinically significant at >4 mg/dL

**Causes:** Renal failure with Mg-containing antacids/laxatives; excessive IV Mg (obstetric protocols); adrenal insufficiency; hypothyroidism

**Clinical manifestations by level:**

| Mg Level (mg/dL) | Manifestations |
|---|---|
| 4-6 | Nausea, flushing, headache, lethargy, hyporeflexia |
| 6-10 | Loss of deep tendon reflexes (DTRs), hypotension, bradycardia |
| 10-15 | Respiratory paralysis, complete heart block |
| >15 | Cardiac arrest |

**Treatment:**
- Calcium gluconate 1 g IV (10 mL of 10% solution): antagonizes Mg at cell membrane; temporary — use for cardiac toxicity or loss of DTRs
- IV fluids + loop diuretics (furosemide): enhance Mg excretion if renal function present
- Hemodialysis: definitive treatment for severe hypermagnesemia or renal failure
- Magnesium-containing agents: discontinue all

---

### Calcium Disorders

#### Hypocalcemia

**Definition:** Corrected calcium <8.5 mg/dL; ionized calcium <1.12 mmol/L

**Corrected calcium formula:**
Corrected Ca = Measured Ca + 0.8 x (4 - albumin)
(For each 1 g/dL decrease in albumin below 4, add 0.8 mg/dL to measured calcium)
Note: ionized calcium measurement preferred in acid-base disturbances (acidosis increases ionized Ca; alkalosis decreases it)

**Causes:**
- Hypoparathyroidism: post-thyroidectomy/parathyroidectomy, autoimmune, DiGeorge syndrome, hungry bone syndrome
- Hypomagnesemia: impairs PTH secretion
- Vitamin D deficiency: malabsorption, CKD, inadequate sun exposure
- Hyperphosphatemia: precipitation of calcium
- Pseudohypoparathyroidism: PTH resistance
- Medications: bisphosphonates, denosumab, cinacalcet, foscarnet, loop diuretics
- Acute pancreatitis: calcium saponification
- Sepsis/critical illness

**Clinical manifestations (Chvostek and Trousseau signs):**
- Chvostek sign: facial nerve twitching when tapping anterior to tragus (ipsilateral facial contraction)
- Trousseau sign: carpal spasm when blood pressure cuff inflated above systolic for 3 minutes (carpopedal spasm)
- Numbness/tingling (perioral, fingertips)
- Muscle cramps, tetany, seizures
- Prolonged QT interval (cardiac arrhythmias)

**Treatment:**
- Severe/symptomatic (tetany, seizures, QTc prolongation): calcium gluconate 1-2 g IV over 10-20 minutes; can infuse as 11 g in 1L D5W at 50-100 mL/hr
- Calcium chloride IV: higher elemental calcium content (3x), caustic — central line preferred
- Maintenance: oral calcium carbonate or calcium citrate (citrate better absorbed on empty stomach and with acid-suppressing medications)
- Vitamin D: calcitriol 0.25-0.5 mcg/day; ergocalciferol/cholecalciferol for nutritional deficiency
- Correct hypomagnesemia first
- PTH replacement (recombinant PTH teriparatide or abaloparatide): used in chronic hypoparathyroidism

#### Hypercalcemia

**Definition:** Total serum calcium >10.5 mg/dL; severe >14 mg/dL

**CHIMPANZEES mnemonic for causes:**
- **C** — Calcium supplementation (milk-alkali syndrome)
- **H** — Hyperparathyroidism (primary — most common outpatient cause)
- **I** — Immobilization (especially Paget disease, metastatic bone disease)
- **M** — Malignancy (PTHrP, lytic metastases, ectopic 1,25-D production — most common inpatient cause)
- **P** — Paget disease of bone
- **A** — Addison disease (adrenal insufficiency)
- **N** — Neoplasm (same as malignancy, lymphoma producing 1,25-D)
- **Z** — Zollinger-Ellison (not directly; MEN1 association with hyperparathyroidism)
- **E** — Excess vitamin D
- **E** — Endocrine (hyperthyroidism, acromegaly, pheochromocytoma)
- **S** — Sarcoidosis/granulomatous disease (1-alpha hydroxylase in granulomas produces excess 1,25-D)

**Clinical manifestations:**
- "Stones, Bones, Groans, Psychic Moans": kidney stones, bone pain/fractures, GI (nausea, constipation, pancreatitis), neuropsychiatric (confusion, depression, coma)
- Cardiac: shortened QT interval, bradycardia, heart block
- Polyuria/polydipsia: nephrogenic DI (Ca inhibits ADH action)

**Treatment by severity:**

| Severity | Ca Level | Treatment |
|---|---|---|
| Mild | 10.5-12 mg/dL | Hydration, treat underlying cause |
| Moderate | 12-14 mg/dL | IV fluids + address cause; consider bisphosphonate |
| Severe/Hypercalcemic crisis | >14 mg/dL | Aggressive IV fluids + furosemide + bisphosphonate + calcitonin |

**Specific treatments:**
- IV normal saline: 200-500 mL/hr to expand volume and increase calciuresis; most important initial step
- Furosemide: only after volume replete; 40-80 mg IV; increases renal calcium excretion
- Bisphosphonates: inhibit osteoclast-mediated bone resorption; onset 2-4 days
  - Zoledronic acid (Zometa) 4 mg IV over 15 minutes: most potent, preferred for malignancy-associated
  - Pamidronate (Aredia) 60-90 mg IV over 2-4 hours: second choice
  - Contraindicated in severe renal failure (GFR <30-35 for zoledronic acid; <30 for pamidronate)
- Calcitonin (salmon): 4-8 IU/kg SC or IM every 6-12 hours; rapid onset (within hours); tachyphylaxis after 48-72 hours; use as bridge while awaiting bisphosphonate effect
- Glucocorticoids: prednisone 40-60 mg/day for granulomatous disease (sarcoidosis, lymphoma) and vitamin D toxicity; decreases calcitriol production
- Denosumab (Xgeva/Prolia): monoclonal antibody against RANKL; used when bisphosphonates contraindicated (renal failure) for malignancy-associated hypercalcemia
- Hemodialysis: for severe/refractory hypercalcemia, especially with renal failure

---

## Acid-Base Disorders

### Approach to Acid-Base Analysis

Systematic approach:
1. pH: <7.35 acidemia, >7.45 alkalemia
2. Primary disorder: HCO3 for metabolic, PaCO2 for respiratory
3. Expected compensation (use formulas — see table)
4. Anion gap calculation
5. Delta-delta ratio if elevated AG
6. Check electrolytes for concurrent disorders

### Expected Compensation Formulas

| Primary Disorder | Expected Compensation | Formula |
|---|---|---|
| Metabolic acidosis | Respiratory (Kussmaul breathing) | PaCO2 = 1.5 x HCO3 + 8 ± 2 (Winter's formula) |
| Metabolic alkalosis | Respiratory (hypoventilation) | PaCO2 = 0.7 x HCO3 + 21 ± 2 |
| Acute respiratory acidosis | Metabolic (immediate) | HCO3 increases 1 mEq/L per 10 mmHg rise in PaCO2 |
| Chronic respiratory acidosis (>3 days) | Metabolic (renal) | HCO3 increases 3.5 mEq/L per 10 mmHg rise in PaCO2 |
| Acute respiratory alkalosis | Metabolic (immediate) | HCO3 decreases 2 mEq/L per 10 mmHg fall in PaCO2 |
| Chronic respiratory alkalosis | Metabolic (renal) | HCO3 decreases 5 mEq/L per 10 mmHg fall in PaCO2 |

If measured compensation does not match expected: mixed disorder present

### Metabolic Acidosis

#### Anion Gap Calculation

**AG = Na - (Cl + HCO3)**

- Normal range: 8-12 mEq/L (using 12 as upper normal)
- Historical normal was 12-16 (older labs with higher normal chloride measurements)

**Albumin correction:**
- Normal AG assumes albumin of 4 g/dL
- For each 1 g/dL decrease in albumin below 4: add 2.5 mEq/L to calculated AG
- Corrected AG = Measured AG + 2.5 x (4 - albumin)
- Critical in critically ill patients with hypoalbuminemia who may have masked high-AG acidosis

#### High Anion Gap Metabolic Acidosis: MUDPILES Mnemonic

| Letter | Cause | Key Features |
|---|---|---|
| M | Methanol | Anion gap + osmol gap; optic nerve toxicity, blindness; treat with fomepizole or ethanol |
| U | Uremia (renal failure) | Organic acid accumulation; treat with dialysis |
| D | Diabetic ketoacidosis (DKA) | Beta-hydroxybutyrate, acetoacetate; serum ketones; insulin + fluids |
| P | Propylene glycol | Found in IV lorazepam, diazepam, acyclovir; osmol gap present |
| I | Isoniazid / Iron overdose | Isoniazid: B6 depletion, seizures; treat with pyridoxine. Iron: direct toxicity |
| L | Lactic acidosis | Most common high-AG cause in ICU; Type A (hypoperfusion) vs Type B (drugs) |
| E | Ethylene glycol | Osmol gap early; calcium oxalate crystals in urine; renal failure; fomepizole |
| S | Salicylates | Respiratory alkalosis + metabolic acidosis; serum salicylate level; alkaline urine |

**Osmol gap:**
Osmol Gap = Measured Osm - Calculated Osm
Calculated Osm = 2(Na) + (glucose/18) + (BUN/2.8)
- Normal: <10-15 mOsm/kg
- Elevated: suggests unmeasured osmoles — alcohols (methanol, ethanol, ethylene glycol, isopropanol), mannitol

#### Normal Anion Gap (Hyperchloremic) Metabolic Acidosis: HARDUPS Mnemonic

| Letter | Cause |
|---|---|
| H | Hyperalimentation (TPN) |
| A | Addison disease (adrenal insufficiency) |
| R | Renal tubular acidosis (RTA) |
| D | Diarrhea (GI bicarbonate loss) |
| U | Ureteral diversion (ileal conduit) |
| P | Pancreatic fistula or drain |
| S | Saline infusion (hyperchloremic from excess NS) |

**Renal Tubular Acidosis (RTA) subtypes:**

| Type | Location | Defect | Urine pH | Serum K | Cause |
|---|---|---|---|---|---|
| Type 1 (distal) | Distal tubule | Impaired H+ secretion | >5.5 | Low | SLE, Sjogren, amphotericin, hereditary |
| Type 2 (proximal) | Proximal tubule | Impaired HCO3 reabsorption | <5.5 (variable) | Low | Fanconi syndrome, myeloma, heavy metals, acetazolamide |
| Type 4 (hypoaldosteronism) | Distal tubule/collecting duct | Low aldosterone or resistance | <5.5 | High | CKD, ACEi/ARB, heparin, T4 diabetes |

Type 3 (combined 1+2) is rare and no longer included in most classifications.

#### Delta-Delta Ratio (Delta Ratio)

Purpose: In high-AG metabolic acidosis, determine if there is a concurrent normal-AG acidosis or metabolic alkalosis

**Delta-Delta = (AG - 12) / (24 - HCO3)**

| Delta-Delta Value | Interpretation |
|---|---|
| <0.4 | Normal-AG acidosis alone (no high-AG component) |
| 0.4-1.0 | Mixed high-AG and normal-AG acidosis |
| 1.0-2.0 | Pure high-AG metabolic acidosis (expected) |
| >2.0 | High-AG acidosis + concurrent metabolic alkalosis |

Note: use actual patient normal AG (corrected for albumin) rather than always using 12

#### Lactic Acidosis

**Type A (Hypoperfusion-related):**
- Septic shock, cardiogenic shock, ischemia
- Decreased oxygen delivery → anaerobic metabolism → lactic acid production
- Treatment: restore perfusion (fluids, vasopressors, treat infection)

**Type B (Normal perfusion — drug/toxin/metabolic):**
- Metformin: inhibits complex I of electron transport chain; more common with renal insufficiency or contrast
- Nucleoside reverse transcriptase inhibitors (NRTIs): stavudine, zidovudine — mitochondrial toxicity
- Linezolid: prolonged use; mitochondrial toxicity
- Propofol infusion syndrome (PRIS): prolonged high-dose infusions in ICU
- Thiamine deficiency: cofactor for pyruvate dehydrogenase; give IV thiamine empirically in suspected cases
- Liver failure: decreased lactate clearance

**Sodium Bicarbonate in Metabolic Acidosis:**
- Controversial; generally avoid unless pH <7.1-7.2 or refractory severe acidosis
- BICAR-ICU trial: sodium bicarbonate in severe metabolic acidosis (pH <7.2) with AKI stage 2-3 did not improve overall survival but reduced AKIN stage progression and mortality in AKI subgroup
- Risks: paradoxical intracellular acidosis, hypernatremia, fluid overload, metabolic alkalosis overshoot
- DKA: do NOT use bicarbonate (adequate insulin + fluids will correct acidosis)
- Cardiac arrest: bicarbonate 1-2 mEq/kg IV push; limited but reasonable in prolonged arrest

### Respiratory Acidosis

**Causes:** Hypoventilation — COPD, asthma, severe obesity hypoventilation, opioids, NMB, chest wall deformity, severe pneumonia, ARDS

- Acute: pH falls 0.08 per 10 mmHg rise in PaCO2
- Chronic: compensated by renal HCO3 retention
- Treatment: address underlying cause; bronchodilators, non-invasive ventilation (BiPAP), mechanical ventilation if needed

### Respiratory Alkalosis

**Causes:** Hyperventilation — anxiety, pain, hypoxia, pregnancy, liver failure (ammonia stimulation), salicylates (early), PE, sepsis (early), mechanical ventilation with excessive rate

- Acute: pH rises 0.08 per 10 mmHg fall in PaCO2
- Chronic: compensated by renal HCO3 excretion
- Treatment: treat underlying cause; rebreathing (paper bag) for anxiety only if not hypoxic

---

## Glomerulonephritis

### Nephrotic vs Nephritic Syndrome

| Feature | Nephrotic Syndrome | Nephritic Syndrome |
|---|---|---|
| Proteinuria | >3.5 g/24h (massive) | <3.5 g/24h (mild-moderate) |
| Hematuria | Absent or mild | Yes — dysmorphic RBCs, RBC casts |
| Hypertension | May be present | Common, often prominent |
| Edema | Severe (periorbital, pitting) | Mild to moderate |
| Serum albumin | Low (hypoalbuminemia) | Normal or mildly low |
| Lipids | Hyperlipidemia, lipiduria | Normal |
| Primary pathology | Podocyte/GBM permeability | Inflammatory GN, proliferation |

### Nephrotic Syndrome

#### Minimal Change Disease (MCD)

- Most common nephrotic syndrome in children; second most common in adults after FSGS
- Normal light microscopy; effacement of podocyte foot processes on electron microscopy; negative immunofluorescence
- Cause: idiopathic (most common), NSAIDs, lithium, lymphoma (Hodgkin — T-cell cytokine release)
- Treatment: prednisone 1 mg/kg/day (max 80 mg) for 8-16 weeks; 80-90% remission in children; adults slower to respond
- Relapsing/steroid-dependent: cyclophosphamide, cyclosporine, tacrolimus, rituximab, mycophenolate mofetil (MMF)
- Generally favorable prognosis; does not progress to ESRD

#### Focal Segmental Glomerulosclerosis (FSGS)

- Most common cause of nephrotic syndrome in adults (especially Black patients)
- Types: idiopathic/primary (immune-mediated, circulating permeability factor), secondary (obesity, reflux nephropathy, HIV, heroin, sickle cell, drug-induced), genetic (podocin, alpha-actinin-4, TRPC6 mutations)
- Columbia classification: NOS, tip lesion (best prognosis), cellular, perihilar (secondary FSGS), collapsing (worst — HIV nephropathy)
- Treatment (primary): corticosteroids 1 mg/kg/day for 4-6 months; CNI (cyclosporine or tacrolimus) for steroid-resistant or steroid-dependent; rituximab for refractory
- RAAS blockade for proteinuria reduction regardless of immunosuppression
- Secondary FSGS: treat underlying cause; generally do NOT use steroids

#### Membranous Nephropathy (MN)

- Most common nephrotic syndrome in white adults middle-aged and older
- "Spike and dome" appearance on electron microscopy (subepithelial immune deposits)
- Primary MN: anti-PLA2R antibody (phospholipase A2 receptor) — positive in ~70%; anti-THSD7A in ~5%
- Secondary MN: hepatitis B, SLE (class V lupus nephritis), solid tumor malignancies (colorectal, lung), drugs (gold, penicillamine, NSAIDs, mercury)
- Workup: PLA2R antibody titer, hepatitis B and C, ANA/anti-dsDNA, complement, cancer screening
- Treatment (primary): RAAS blockade + supportive (25-30% spontaneous remission); immunosuppression for high-risk (anti-PLA2R titer >150, worsening renal function, nephrotic complications)
  - Rituximab: first-line for immunosuppression (MENTOR trial); depletes B cells, reduces PLA2R antibody
  - Cyclophosphamide + steroids (Ponticelli regimen): alternating months x 6 months; older gold standard
  - Calcineurin inhibitors: cyclosporine or tacrolimus; effective but relapse common on discontinuation

### Nephritic Syndrome

#### IgA Nephropathy (Berger Disease)

- Most common primary GN worldwide
- Mesangial IgA deposits (IgA1); triggered by mucosal infections
- Presentation: episodic gross hematuria coinciding with upper respiratory or GI infection ("synpharyngitic hematuria"), or asymptomatic microscopic hematuria ± proteinuria
- Prognosis: Oxford MEST-C score guides risk stratification; 20-30% reach ESRD over 20 years
- Triggers: IgA vasculitis (Henoch-Schonlein Purpura) — systemic variant with skin, joints, GI involvement
- Treatment: RAAS blockade (ACEi/ARB) for proteinuria >1 g/day; SGLT2i increasingly used; fish oil (omega-3) — evidence limited
- Immunosuppression (steroids): for rapidly progressive IgA nephropathy or persistent proteinuria >1-3.5 g/day despite RAAS blockade; STOP-IgAN and TESTING trials
- Sparsentan: dual endothelin/angiotensin receptor blocker; FDA approved for IgA nephropathy (PROTECT trial — reduced proteinuria)
- Budesonide (Nefecon/Tarpeyo): targeted-release oral budesonide for Peyer's patch; FDA approved; reduces galactose-deficient IgA1

#### ANCA Vasculitis (see Intrinsic AKI section above)

#### Anti-GBM Disease (see Intrinsic AKI section above)

#### Post-Streptococcal Glomerulonephritis (PSGN)

- Follows Group A streptococcal pharyngitis (2-3 weeks) or impetigo (4-6 weeks)
- Immune complex (IgG + complement) deposition in mesangium and subepithelium
- "Lumpy-bumpy" (granular) immunofluorescence; subepithelial "humps" on EM
- Low complement (C3, CH50); elevated ASO titer or anti-DNase B
- Presentation: hematuria, hypertension, edema, oliguria in children
- Self-limiting in children; worse prognosis in adults and elderly
- Treatment: supportive — antihypertensives, diuretics; antibiotics to treat active strep; no immunosuppression

#### Lupus Nephritis

- Occurs in 40-60% of SLE patients; most common serious organ manifestation
- ISN/RPS classification:

| Class | Description | Treatment |
|---|---|---|
| I | Minimal mesangial | None (unless other indications) |
| II | Mesangial proliferative | Steroids if symptomatic |
| III | Focal proliferative (<50% glomeruli) | MMF + steroids |
| IV | Diffuse proliferative (>=50% glomeruli) | MMF + steroids (most severe) |
| V | Membranous LN | RAAS blockade; MMF if nephrotic; add Class III/IV treatment if combined |
| VI | Advanced sclerosing (>90% sclerosis) | Supportive; prepare for RRT |

- Induction: MMF 2-3 g/day + prednisone 0.5-1 mg/kg/day (taper over 6-12 months) — preferred for Class III/IV
- Alternative induction: low-dose IV cyclophosphamide (NIH or Euro-Lupus protocol)
- Voclosporin (Lupkynis): calcineurin inhibitor approved as add-on for active LN; reduces proteinuria
- Belimumab (Benlysta): anti-BLyS monoclonal antibody; FDA approved for active LN as add-on
- Maintenance: MMF 1-2 g/day + low-dose prednisone; azathioprine alternative (preferred in pregnancy)
- Monitor: anti-dsDNA antibody, complement (C3/C4), UA, proteinuria

---

## Renal Replacement Therapy

### Hemodialysis (HD)

**Principles:**
- Diffusion across semipermeable membrane; blood and dialysate run countercurrent
- Clears uremic solutes, excess fluid, electrolytes
- Standard: 3 sessions/week, 3-4 hours per session; home HD (5-6x/week or nocturnal) offers superior outcomes

**Access (in order of preference):**
1. Arteriovenous fistula (AVF): native vessel anastomosis; highest patency, lowest infection rate; takes 6-12 weeks to mature
2. Arteriovenous graft (AVG): synthetic (PTFE) bridge; higher infection and thrombosis vs AVF; usable in 2-4 weeks
3. Tunneled cuffed catheter (TCC): temporary or bridge access; highest infection and mortality risk; immediate use

**Indications for HD initiation:**
- GFR <10 mL/min with symptoms, or GFR <6-8 (asymptomatic)
- Urgent: AEIOU criteria (see AKI section)
- IDEAL trial: no benefit to early (eGFR 10-14) vs later (eGFR 5-7) initiation in asymptomatic patients

**HD adequacy:** Kt/V >=1.4 per session (single-pool), URR (urea reduction ratio) >65%

**HD complications:**
- Intradialytic hypotension (most common): volume removal too rapid; prone to ischemic events
- Dialysis disequilibrium syndrome: cerebral edema from rapid urea removal (first session); nausea, headache, seizures; prevent by slow, short first sessions
- Access thrombosis, infections, stenosis
- Muscle cramps: hypertonic saline, glucose, reduce UFR
- Air embolism: rare; position left lateral decubitus, head down

### Peritoneal Dialysis (PD)

**Principles:**
- Peritoneum as natural semipermeable membrane; dialysate instilled intraperitoneally
- Diffusion + osmosis (glucose gradient drives ultrafiltration)

**Modalities:**
- CAPD (Continuous Ambulatory PD): 4-5 exchanges/day manually; 2 L each; no machine
- CCPD (Continuous Cycler-Assisted PD): machine performs exchanges overnight (4-6 cycles); patient free during day
- APD (Automated PD): broader term for machine-based PD

**PD Peritonitis:**
- Presentation: cloudy effluent, abdominal pain, fever
- Diagnosis: PD effluent cell count >100 WBC/mL with >50% PMNs
- Treatment: intraperitoneal (IP) antibiotics — vancomycin or first-generation cephalosporin (gram-positive coverage) + third-generation cephalosporin or aminoglycoside (gram-negative); tailor to culture
- Duration: 2-3 weeks IP antibiotics; catheter removal if refractory, fungal, or relapsing
- Most common organisms: Staphylococcus epidermidis, Staphylococcus aureus
- Fungal peritonitis: catheter must be removed; fluconazole or micafungin

**PD advantages:** Preserves residual renal function longer; cardiovascular stability; home modality; continuous clearance

**PD contraindications:** Prior major abdominal surgery with adhesions, active peritonitis, diaphragmatic defect, severe protein-calorie malnutrition, inability to perform exchanges

### Continuous Renal Replacement Therapy (CRRT)

**Indication:** AKI in hemodynamically unstable ICU patients (vs intermittent HD which causes hemodynamic fluctuation)

**Modalities:**

| Mode | Full Name | Mechanism | Best For |
|---|---|---|---|
| CVVHD | Continuous venovenous hemodialysis | Diffusion | Small molecule clearance |
| CVVHF | Continuous venovenous hemofiltration | Convection | Middle molecule clearance |
| CVVHDF | Continuous venovenous hemodiafiltration | Both | Combined (most common ICU modality) |
| SCUF | Slow continuous ultrafiltration | Ultrafiltration only | Pure fluid removal, minimal solute |

**Anticoagulation:** regional citrate preferred (KDIGO); systemic heparin if citrate contraindicated; no anticoagulation if high bleeding risk

**Dose:** Effluent volume 20-25 mL/kg/hr minimum; 25-30 mL/kg/hr prescribed to achieve delivered dose of 20-25 mL/kg/hr

**CRRT vs HD:** No survival advantage demonstrated; CRRT preferred for:
- Mean arterial pressure <65 mmHg or vasopressor-dependent
- Severe acute brain injury (avoids ICP changes)
- Acute liver failure
- Aggressive fluid removal needed without hemodynamic compromise

### Dialysis Initiation (Chronic CKD)

**GFR thresholds:**
- Symptomatic (uremic symptoms, fluid overload, K/acid refractory): initiate regardless of GFR
- Asymptomatic: GFR 5-10 mL/min (most guidelines recommend initiation before GFR <10)
- Diabetics may have symptoms at higher GFR
- IDEAL trial: early (10-14) vs late (5-7) initiation showed no difference in survival

**Pre-ESRD planning:**
- Refer to nephrology at eGFR <30 (CKD G4) for education, access planning
- Fistula placed ideally 6-12 months before anticipated HD start
- Hepatitis B vaccination series early (response decreases as GFR declines)
- Transplant evaluation early: wait list time averages 3-5 years; preemptive transplant (before dialysis) has best outcomes

---

## Drug Dosing in Renal Impairment

All adjustments based on Cockcroft-Gault CrCl. Consult pharmacy for real-time recommendations.

### Comprehensive Drug Dosing Table

| Drug | Normal Dose | CrCl 30-60 mL/min | CrCl 15-30 mL/min | CrCl <15 / HD |
|---|---|---|---|---|
| Metformin | 500-2000 mg/day | Use with caution; reduce dose; monitor | Avoid (CrCl <30-45 per FDA) | Contraindicated |
| Gabapentin | 300-1200 mg TID | 200-700 mg TID (CrCl 30-60) | 200-700 mg BID (CrCl 15-30) | 100-300 mg once daily; supplement 125-350 mg after HD |
| Vancomycin | 15-20 mg/kg q8-12h | Extend interval; AUC/MIC guided | Significantly extend interval; load q48-72h; monitor AUC | Intermittent dosing post-HD; redose based on level |
| Piperacillin-tazobactam | 3.375 g q6h or 4.5 g q8h | No change | 2.25-3.375 g q8h | 2.25 g q8h; supplement after HD |
| Meropenem | 1-2 g q8h | 1 g q12h (CrCl 25-50) | 0.5 g q12h (CrCl 10-25) | 0.5 g q24h; supplement after HD |
| Ciprofloxacin | 400 mg IV q12h / 500 mg PO q12h | 250-500 mg q12h PO | 250-500 mg q18-24h | 250-500 mg q24h |
| Levofloxacin | 500-750 mg daily | 250-500 mg daily (CrCl 20-50) | 250 mg daily (CrCl 10-19) | 250 mg q48h |
| Nitrofurantoin | 100 mg BID x 5 days | Avoid if CrCl <45 (inadequate urinary levels) | Contraindicated | Contraindicated |
| Apixaban | 5 mg BID | Use with caution; dose reduce per criteria | Use with caution (limited data) | Avoid; not removed by HD |
| Rivaroxaban | 20 mg daily (AF) | CrCl 15-50: 15 mg daily (AF) | 15 mg daily (AF) — use with caution | Avoid if CrCl <15 |
| Dabigatran | 150 mg BID | CrCl 15-30: 75 mg BID; avoid if <15 | Avoid (contraindicated) | Contraindicated |
| Digoxin | 0.125-0.25 mg daily | Reduce dose by 25-50%; monitor levels | Reduce dose significantly; 0.0625 mg daily | Avoid; HD does not remove |
| Enoxaparin (LMWH) | 1 mg/kg SC q12h | No change if CrCl >30 | 1 mg/kg SC q24h (CrCl <30) | Use UFH; LMWH not recommended |
| Allopurinol | 300 mg daily | 200 mg daily (CrCl 20-60) | 100 mg daily (CrCl <20) | 100 mg 3x/week; dose after HD |
| Colchicine | 1.2 mg, then 0.6 mg 1h later | Reduce dose; CrCl 30-60: no specific adjustment but use with caution | Reduce dose; avoid prolonged use | Avoid; dialysis does not remove |
| NSAIDs | Varies | Avoid if possible; increased AKI risk | Avoid | Contraindicated |
| Lithium | 150-300 mg TID | Reduce dose 50%; monitor levels frequently | Extreme caution; 25% dose | Avoid; removed by HD (can use in intoxication) |
| Trimethoprim-sulfamethoxazole | 1 DS tablet BID | CrCl 15-30: use with caution; half dose | CrCl <15: avoid | Avoid |
| Acyclovir | 5-10 mg/kg q8h IV | 5-10 mg/kg q12-24h | 5 mg/kg q24h | 2.5 mg/kg q24h; supplement after HD |

### Key Drug Dosing Principles in CKD/ESRD

- **Avoid:** NSAIDs (renal vasoconstriction, fluid retention, hyperkalemia), nitrofurantoin (inadequate urinary levels + peripheral neuropathy risk), metformin (lactic acidosis risk if GFR <30-45)
- **Renally cleared drugs requiring dose adjustment:** aminoglycosides, vancomycin, beta-lactams, fluoroquinolones, antivirals, LMWH, novel oral anticoagulants, digoxin
- **Dialyzability:** Dialyzable drugs (removed by HD) require supplemental dosing post-HD: gabapentin, valacyclovir, acyclovir, aminoglycosides, lithium, some beta-lactams
- **Protein-bound drugs:** not removed by HD (warfarin, PPIs, most CCBs)
- **Volume of distribution:** drugs with large Vd (chloroquine, digoxin at toxic levels) not effectively removed by HD
- **TDM (Therapeutic Drug Monitoring):** critical for vancomycin, aminoglycosides, digoxin, lithium, tacrolimus/cyclosporine

---

## Nephrolithiasis

### Stone Types and Characteristics

| Stone Type | Frequency | Radiodensity | Urine pH | Crystal Morphology | Key Associations |
|---|---|---|---|---|---|
| Calcium oxalate (CaOx) monohydrate | 35-40% of all stones | Radiopaque | Low | Dumbbell-shaped | Hyperoxaluria, hypercalciuria |
| Calcium oxalate dihydrate | 25-30% | Radiopaque | Low | Envelope/Maltese cross | Idiopathic hypercalciuria |
| Calcium phosphate (hydroxyapatite) | 5-10% | Very radiopaque | High (>7) | Amorphous | RTA type 1, hyperparathyroidism |
| Uric acid | 5-10% | Radiolucent (not seen on plain film) | Low (<5.5) | Rhomboid/rosette | Gout, metabolic syndrome, DM, high purine diet, acidic urine |
| Struvite (magnesium ammonium phosphate) | 10-15% | Moderately radiopaque | High (>7) | Coffin-lid | Urease-producing bacteria (Proteus, Klebsiella, Pseudomonas), staghorn calculi |
| Cystine | 1-2% | Radiopaque (faint) | Low (<7) | Hexagonal | Autosomal recessive cystinuria (SLC3A1, SLC7A9 mutations) |

### Diagnostic Workup

**Acute presentation:**
- Non-contrast CT abdomen/pelvis (NCCT): gold standard; detects all stone types except some uric acid (indinavir stones invisible); identifies location, size, hydronephrosis
- Renal ultrasound (US): no radiation; detects stones >5 mm; identifies hydronephrosis; preferred in pregnancy and children; misses ureteral stones
- KUB (plain film): detects radiopaque stones; limited sensitivity; used for monitoring known radiopaque stones
- Urinalysis: hematuria (>90% of cases), pH, crystals (may indicate stone type), UA to evaluate for infection
- BMP: creatinine, BUN, electrolytes, calcium, uric acid
- CBC: leukocytosis suggests concurrent infection (urological emergency)

**Metabolic workup (recurrent stone formers or first stone with risk factors):**
- 24-hour urine collection x2 (different days): volume, creatinine (adequacy check), calcium, oxalate, uric acid, citrate, phosphate, sodium, pH
- Serum: calcium, phosphate, uric acid, PTH (if hypercalcemia)
- Stone analysis (if stone captured): definitive stone composition

### Acute Nephrolithiasis Management

**Pain control:**
- IV ketorolac (Toradol) 15-30 mg IV: NSAID — reduces ureteral spasm and prostaglandin-mediated pain; avoid if AKI, GFR concern, or NSAID contraindication
- IV morphine or hydromorphone: for severe pain or if NSAIDs contraindicated
- IV hydration: facilitates stone passage; isotonic saline 1-2 L

**Medical expulsive therapy (MET):**
- Tamsulosin (Flomax) 0.4 mg daily: alpha-1 blocker; relaxes ureteral smooth muscle; increases stone passage rate for stones 5-10 mm; most evidence for distal ureter stones
- May also use nifedipine; tamsulosin generally preferred
- Meta-analyses show modest benefit; most guidelines support use for distal ureteral stones 5-10 mm

**Urology consultation indications:**
- Obstruction with concurrent infection (urological emergency — urgent drainage)
- Stone >10 mm (unlikely to pass spontaneously)
- Solitary kidney
- Bilateral obstruction
- Refractory pain or vomiting
- Complete obstruction
- Failed medical expulsion after 4-6 weeks

**Interventional options:**
- ESWL (extracorporeal shock wave lithotripsy): for stones <15-20 mm, no lower pole kidney stones >1 cm (poor clearance), good renal function
- Ureteroscopy (URS) with laser lithotripsy: flexible URS for upper ureter/renal stones; rigid URS for distal ureter; high stone-free rates
- Percutaneous nephrolithotomy (PCNL): large stones >20 mm, staghorn calculi, ESWL failure
- Medical dissolution: uric acid stones only — alkalinize urine with potassium citrate (target urine pH 6.5-7.0)

### Stone Prevention Strategies

**General measures for all stone types:**
- High fluid intake: target urine output >2.5 L/day; drink to produce pale urine
- Avoid dehydration

**Calcium oxalate stones:**
- Moderate dietary calcium (1000-1200 mg/day from food, NOT supplements — dietary calcium binds intestinal oxalate)
- Limit dietary sodium (<2300 mg/day) — reduces urinary calcium excretion
- Limit dietary oxalate (spinach, nuts, chocolate, rhubarb, tea)
- Thiazide diuretics (HCTZ, chlorthalidone): reduce urinary calcium excretion; for hypercalciuria
- Potassium citrate: inhibits calcium oxalate crystallization; treats hypocitraturia
- Pyridoxine (B6): reduces oxalate production; for enteric hyperoxaluria

**Uric acid stones:**
- Urine alkalinization: potassium citrate 20-40 mEq BID-TID; target urine pH 6.5-7.0
- Reduce dietary purine (red meat, organ meats, shellfish, alcohol)
- Allopurinol: if hyperuricosuria or hyperuricemia; 300 mg daily (dose reduce in renal impairment)
- Hydration: uric acid solubility increases with pH and hydration

**Struvite stones:**
- Eliminate infection: surgical removal of all stone material (infection sanctuary)
- Treat with culture-directed antibiotics
- Acetohydroxamic acid (AHA): urease inhibitor; adjunct to antibiotics; frequent side effects (DVT, headache, hemolytic anemia)
- Staghorn calculi: typically require PCNL

**Cystine stones:**
- Aggressive hydration: urine output >3 L/day
- Urine alkalinization: target pH >7.0-7.5 (potassium citrate, sodium bicarbonate)
- D-penicillamine or tiopronin (alpha-MPG): chelate cystine → more soluble mixed disulfides; significant side effects
- Captopril: forms captopril-cysteine disulfide (SH group); limited evidence
- Dietary methionine restriction (cystine precursor)

---

## Polycystic Kidney Disease

### Autosomal Dominant PKD (ADPKD)

**Genetics:**
- PKD1 mutation (chromosome 16): encodes polycystin-1; 85% of cases; more severe phenotype
- PKD2 mutation (chromosome 4): encodes polycystin-2; 15%; later onset ESRD (median 70 vs 54 years for PKD1)
- "Two-hit" hypothesis: germline mutation + somatic second hit triggers individual cyst formation
- De novo mutations: ~5% of cases; negative family history does not exclude

**Clinical features:**
- Renal: progressive bilateral cyst enlargement, declining GFR, hematuria (cyst hemorrhage), flank pain, hypertension, urinary tract infections, kidney stones (uric acid)
- Extrarenal: hepatic cysts (most common extrarenal manifestation; liver-specific PKD2), intracranial aneurysms (ICA) in 8-12% (vs 2% general population), mitral valve prolapse, aortic root dilation, seminal vesicle cysts, pancreatic cysts
- Intracranial aneurysms: screen if family history of ICA or subarachnoid hemorrhage; baseline MRA then periodic screening

**Diagnosis:**
- Ultrasound criteria (Ravine criteria, unified Poltronieri criteria):
  - Age 15-39: >=3 total cysts (combined both kidneys)
  - Age 40-59: >=2 cysts in each kidney
  - Age >=60: >=4 cysts in each kidney
- MRI or CT for equivocal US or when US inadequate
- Genetic testing: when diagnosis uncertain, atypical presentation, young donors for living-related transplant evaluation

**Prognostic tool — Total Kidney Volume (TKV):**
- Height-adjusted TKV (htTKV) measured by MRI
- Mayo Clinic Imaging Classification (Class 1A-1E): predicts GFR decline and ESRD
  - Class 1C-1E: rapid progression; most likely to benefit from tolvaptan
- PROPKD score (PKD1/PKD2 mutation + hypertension/hematuria/UTI age ≤35): predicts age at ESRD

**Management:**

Blood pressure:
- Target <110/75 mmHg in young patients (HALT-PKD trial): RAAS blockade slows kidney growth (TKV) and may slow GFR decline
- ACEi or ARB preferred; dual RAAS blockade showed no added benefit in HALT-PKD

Tolvaptan (Jynarque/Samsca):
- V2 receptor antagonist; reduces cAMP-mediated cyst growth
- TEMPO 3:4 trial: 50% reduction in TKV growth rate; 26% reduction in eGFR decline over 3 years
- REPRISE trial: slowed eGFR decline in patients with declining GFR (eGFR 25-65)
- FDA approved for adults with ADPKD at risk of rapid progression (typically Mayo Class 1C-1E or htTKV >600 mL/m)
- Dosing: split-dose (e.g., 45/15 mg); liver function monitoring required (potentially fatal hepatotoxicity, 0.1% DILI)
- REMS program required; contraindicated in dehydration, liver disease
- Copeptin biomarker: high levels predict rapid progression; may identify responders

Pain management:
- Cyst hemorrhage: conservative (hydration, analgesia); usually self-limited
- Chronic pain: tricyclics, gabapentin, celecoxib (note renal effects); nerve block, surgical cyst decortication for refractory
- Triptans (sumatriptan): for headache associated with intracranial cysts or ICA; also used for migraine (which is more common in ADPKD)

UTI in ADPKD:
- Cyst infections: difficult to treat; organisms reach cysts poorly
- Fluoroquinolones (ciprofloxacin, levofloxacin): preferred — penetrate cysts best (lipophilic)
- TMP-SMX: also adequate cyst penetration
- Duration: 4-6 weeks; may require drainage for large infected cysts

**Autosomal Recessive PKD (ARPKD):**
- PKHD1 gene (fibrocystin/polyductin); presents in perinatal period/infancy
- Potter sequence (oligohydramnios sequence), pulmonary hypoplasia, hepatic fibrosis (congenital)
- Severity varies: severe forms fatal at birth; milder forms survive to adulthood with renal and hepatic disease
- No approved disease-modifying therapy; supportive care, dialysis, transplant

---

## Renal Artery Stenosis

### Definition and Types

Renal artery stenosis (RAS) is narrowing of one or both renal arteries causing renovascular hypertension and/or ischemic nephropathy.

| Feature | Atherosclerotic RAS | Fibromuscular Dysplasia (FMD) |
|---|---|---|
| Age | Older (>55 years) | Young (20-50 years) |
| Sex | Male predominance | Female predominance (90%) |
| Location | Ostial/proximal renal artery | Mid/distal renal artery, branching |
| Angiographic appearance | Concentric plaque at ostium | "String of beads" (medial fibroplasia) |
| Bilateral | Common | Less common; may be bilateral |
| Systemic atherosclerosis | Yes | No |
| Progression | Common | Variable |
| Treatment | Medical therapy preferred; stenting limited role | Percutaneous transluminal angioplasty (PTA) |

### Pathophysiology: Renin-Angiotensin System Activation

- Stenosis → reduced renal perfusion pressure → juxtaglomerular cells release renin
- Renin → converts angiotensinogen to angiotensin I → ACE converts to Ang II
- Ang II → systemic vasoconstriction (hypertension), sodium retention (aldosterone), efferent arteriole constriction
- Unilateral RAS (1.5 kidney model): contralateral kidney excretes excess sodium; hypertension driven by RAAS
- Bilateral RAS (Goldblatt 2-kidney 2-clip): both kidneys ischemic; sodium retention dominant; more volume-dependent HTN

### Clinical Presentation

- Hypertension: resistant or rapidly worsening; onset at extremes of age; sudden onset in young woman
- Flash pulmonary edema: bilateral RAS with recurrent pulmonary edema despite EF preserved; classic presentation
- AKI with ACEi/ARB initiation: loss of angiotensin II-mediated efferent tone → GFR falls in stenotic kidney; if bilateral or solitary kidney, can cause severe AKI
- Hypokalemia: secondary aldosteronism from bilateral RAS
- Incidental finding: >50% stenosis on imaging for other indication
- Abdominal bruit: epigastric or flank bruit (50% sensitivity, not diagnostic)

### Diagnosis

- Renal Doppler ultrasound: first-line screening; measures resistive index and peak systolic velocity; dependent on operator skill; limited for ostial lesions
- CT angiography (CTA): excellent sensitivity/specificity; radiation + contrast; preferred anatomic detail
- MR angiography (MRA): no radiation; gadolinium risk in severe CKD (nephrogenic systemic fibrosis); non-contrast MRA options
- Captopril renography (captopril scintigraphy): nuclear medicine scan; functional test showing differential renal function after ACEi; less commonly used
- Digital subtraction angiography (DSA): gold standard; invasive; reserved for when diagnosis uncertain or proceeding to intervention

### ACEi/ARB Use in RAS

- Bilateral RAS or unilateral RAS in solitary kidney: ACEi/ARB are relatively contraindicated; loss of angiotensin II effects on efferent arteriole → GFR drops precipitously
- Clinical implication: if starting ACEi/ARB, monitor Scr and potassium closely at 1 week; Scr rise >30% warrants evaluation for RAS
- Unilateral RAS with normal contralateral kidney: ACEi/ARB may still be beneficial for hypertension; risk of AKI lower but contralateral kidney GFR may compensate

### Management

**Atherosclerotic RAS — Medical Therapy Preferred:**
- Blood pressure control: ACEi or ARB (with close creatinine monitoring), CCB, chlorthalidone
- Statins: pleiotropic benefits, stabilize plaque
- Antiplatelet therapy (aspirin or clopidogrel)
- Smoking cessation
- ASTRAL trial (2009): renal artery stenting + medical therapy vs medical therapy alone in atherosclerotic RAS — no significant difference in BP, renal function, CV events, or survival
- CORAL trial (2014): stenting + medical vs medical alone — stenting did not significantly reduce CV events or rate of renal function decline
- Conclusion: revascularization for atherosclerotic RAS not routinely recommended; reserve for specific indications (flash pulmonary edema, rapidly progressive renal insufficiency, resistant hypertension refractory to 3+ agents)

**Fibromuscular Dysplasia — Revascularization Preferred:**
- Percutaneous transluminal angioplasty (PTA): balloon angioplasty without stenting; cure or significant improvement in hypertension in 40-60%; primary treatment for medial fibroplasia
- Stenting reserved for dissection or failed PTA
- Surgical revascularization: for complex anatomy or failed PTA; less commonly needed with modern endovascular techniques
- RAAS blockade effective for BP control while awaiting procedure or as adjunctive therapy

**Indications for Revascularization (Atherosclerotic RAS):**
- Recurrent "flash" pulmonary edema with preserved EF
- Rapidly progressive loss of renal function with bilateral RAS or solitary kidney
- Hypertension truly resistant to 3+ maximally dosed agents including diuretic
- Hemodynamically significant stenosis (>80%) with threatened renal viability

---

## Quick Reference Tables

### Urinalysis Findings Summary

| Finding | Significance |
|---|---|
| Muddy brown granular casts | ATN |
| RBC casts | Glomerulonephritis (nephritic) |
| WBC casts | AIN, pyelonephritis |
| Oval fat bodies, fatty casts, lipiduria | Nephrotic syndrome |
| Waxy casts, broad casts | Advanced CKD, ESRD |
| Hyaline casts | Normal, concentrated urine, prerenal |
| Eosinophiluria (Hansel stain) | AIN (low sensitivity) |

### Key Formulas Summary

| Formula | Equation |
|---|---|
| Anion Gap | Na - (Cl + HCO3); normal 8-12 |
| Corrected AG (for albumin) | AG + 2.5 x (4 - albumin) |
| Delta-delta ratio | (AG - 12) / (24 - HCO3) |
| Corrected calcium | Measured Ca + 0.8 x (4 - albumin) |
| Free water deficit | TBW x (Na/140 - 1) |
| FeNa | (UNa x PCr) / (PNa x UCr) x 100 |
| Osmol gap | Measured Osm - [2(Na) + glucose/18 + BUN/2.8] |
| Cockcroft-Gault CrCl | [(140-Age) x Weight] / (72 x Scr) x 0.85 (female) |
| Winter's formula | PaCO2 = 1.5 x HCO3 + 8 ± 2 |

### AEIOU Dialysis Indications

| A | Acidosis — pH <7.1-7.2 refractory to treatment |
| E | Electrolytes — K >6.5 with symptoms, refractory |
| I | Ingestions — lithium, methanol, ethylene glycol, salicylates, theophylline |
| O | Overload — fluid/pulmonary edema refractory to diuretics |
| U | Uremia — encephalopathy, pericarditis, bleeding |

---

*End of Renal Disease Knowledge Base*  
*Version 1.0 — Zia Venture Group Medical KB — For RAG/clinical reference use*
