# Critical Care and ICU Medicine

## Overview

Critical care medicine encompasses the management of life-threatening illness and injury across organ systems. The ICU environment combines continuous monitoring, advanced hemodynamic support, mechanical ventilation, renal replacement therapy, and multispecialty coordination. This knowledge base covers the core clinical syndromes, physiologic principles, monitoring modalities, pharmacology, and evidence-based protocols that define modern critical care practice.

---

## Mechanical Ventilation

### Indications for Intubation

- Airway protection: altered mental status (GCS <8), airway edema, massive hemoptysis, angioedema
- Ventilatory failure: rising PaCO2 with acidosis, respiratory muscle fatigue, NIF < -20 to -25 cmH2O
- Oxygenation failure: PaO2/FiO2 < 200 despite high-flow oxygen, SpO2 <88% on 15L NRB
- Anticipated deterioration: burns with inhalation injury, cervical spine injury with ascending edema
- Peri-procedural: hemorrhage control in unstable trauma, cardioversion in obtunded patients

### Rapid Sequence Intubation (RSI)

| Step | Action | Notes |
|------|--------|-------|
| Preparation | IV access, cardiac monitor, suction, video laryngoscopy ready | Two IVs preferred |
| Preoxygenation | NRB 15L x 3-5 min or BVM with PEEP valve | SpO2 >95% before induction |
| Pretreatment | Consider lidocaine 1.5mg/kg IV for bronchospasm or elevated ICP | Optional step |
| Induction | Ketamine 1-2mg/kg IV (hemodynamically unstable) or etomidate 0.3mg/kg IV (stable) | Propofol 1-2mg/kg if BP permits |
| Paralysis | Succinylcholine 1.5mg/kg IV or rocuronium 1.2mg/kg IV | Succinylcholine CI: hyperkalemia, crush injury >72h, denervation, myopathies |
| Intubate | Laryngoscopy with cuff inflation and ETCO2 confirmation | Waveform capnography preferred over colorimetric |
| Post-intubation | Secure ETT, order CXR, initiate vent settings, start sedation | Verify bilateral breath sounds |

**Difficult airway predictors (LEMON):** Look (facies, beard, obese neck), Evaluate 3-3-2 rule (3 finger mouth opening, 3 finger hyoid to chin, 2 finger thyroid to floor of mouth), Mallampati (III/IV), Obstruction (abscess, epiglottitis, mass), Neck mobility.

### Ventilator Modes

#### Volume-Controlled (VC-AC)
- Set parameters: tidal volume, respiratory rate, FiO2, PEEP, flow rate, I:E ratio
- Pressure varies with lung compliance and resistance — monitor peak and plateau pressures
- Every triggered breath receives full tidal volume support
- Most common initial mode; simplifies initial management
- Risk: patient-ventilator dyssynchrony if respiratory drive is high; flow starvation if set flow too low

#### Volume-Controlled SIMV
- Synchronized Intermittent Mandatory Ventilation: delivers set mandatory breaths, patient breathes spontaneously between
- Spontaneous breaths unsupported (increased WOB) unless pressure support added
- Rarely used for weaning; has been superseded by SBT protocols
- Historical use: gradual weaning by decreasing mandatory rate

#### Pressure-Controlled (PC-AC)
- Set parameters: inspiratory pressure (above PEEP), respiratory rate, FiO2, PEEP, I:E ratio
- Tidal volume varies with compliance — monitor VT delivery closely
- Decelerating flow waveform — better gas distribution in heterogeneous lungs
- Preferred in severe ARDS, poor compliance, high airway pressure with VC ventilation
- Risk: volume delivery drops if compliance worsens acutely (mucus plug, pneumothorax, ET tube occlusion)

#### Pressure Support Ventilation (PSV)
- Spontaneous-only mode: no mandatory backup rate
- Set: pressure support level (above PEEP) + PEEP + FiO2
- Patient controls rate, timing, and flow
- PS 5-8 cmH2O + PEEP 5 = standard SBT condition
- Used during weaning; total inspiratory pressure = PEEP + PS level
- Requires adequate respiratory drive — apnea alarm critical

#### APRV (Airway Pressure Release Ventilation)
- High CPAP (Phigh, 20-30 cmH2O) held for long time (Thigh, 4-6 seconds)
- Brief release to low pressure (Plow, 0-5 cmH2O) for short time (Tlow, 0.5-0.8 seconds)
- Inverse I:E ratio; spontaneous breathing throughout cycle
- Proposed benefits: alveolar recruitment, reduced peak pressure, preserved spontaneous breathing
- Controversial — PROSEVA trial did not include APRV; no high-quality RCT data vs prone + conventional lung-protective ventilation
- Complicated titration; requires experienced respiratory therapy team

#### HFOV (High-Frequency Oscillatory Ventilation)
- Very small tidal volumes (1-3 mL/kg), frequency 3-15 Hz
- Oscillatory pressure above mean airway pressure; ventilation by diffusion
- OSCAR (2013) and OSCILLATE (2013) trials: HFOV increased mortality vs conventional ventilation in moderate-severe ARDS
- Currently largely abandoned for ARDS
- Possible niche: neonatal ARDS, air leak syndromes

### Initial Ventilator Settings — Standard Adult

| Parameter | Starting Value | Notes |
|-----------|---------------|-------|
| Mode | VC-AC | Most common initial mode |
| Tidal volume | 6-8 mL/kg IBW | 6 mL/kg IBW for ARDS |
| Respiratory rate | 14-18/min | Adjust to pH/PaCO2 target |
| FiO2 | 1.0 | Wean to maintain SpO2 92-96% |
| PEEP | 5 cmH2O | Titrate per ARDSNET table in ARDS |
| I:E ratio | 1:2 | Extend to 1:3 or 1:4 in obstructive disease |
| Peak pressure alarm | Pplat + 10-15 cmH2O | Typically 35-40 cmH2O |
| Low minute ventilation alarm | 70-80% of set MV | Apnea protection |

**IBW formula:** Male = 50 + 2.3 x (height in inches - 60); Female = 45.5 + 2.3 x (height in inches - 60)

### Key Ventilator Mechanics

#### Plateau Pressure (Pplat)
- Measured with end-inspiratory hold (0.5-2 seconds) — reflects static compliance (alveolar pressure)
- Target: ≤30 cmH2O (lung-protective threshold — ARDSNET)
- Elevated Pplat + elevated Peak P: decreased compliance (pneumonia, ARDS, pulmonary edema, pneumothorax, abdominal hypertension)
- Normal Pplat + elevated Peak P: increased airway resistance (bronchospasm, secretions, kinked or biting ET tube)

#### Driving Pressure
- Driving pressure = Pplat - PEEP
- Reflects stress on the aerated lung parenchyma
- Target: ≤15 cmH2O (Amato 2015 observational analysis — driving pressure independently associated with mortality in ARDS)
- Reduce by decreasing VT or increasing PEEP (if compliance improves with PEEP)

#### Auto-PEEP (Intrinsic PEEP, PEEPi)
- Air trapping from incomplete exhalation before next breath
- Causes: obstructive lung disease, high RR, prolonged I-time, secretions
- Detection: end-expiratory hold; expiratory flow still above zero on flow-time waveform
- Consequences: breath stacking, hemodynamic compromise (decreased venous return), pneumothorax, patient-ventilator dyssynchrony
- Management: decrease RR, increase expiratory time (1:3 or 1:4 I:E), bronchodilators, suction, sedation/paralysis if needed

#### Static vs Dynamic Compliance

| Measurement | Formula | Normal Values |
|-------------|---------|--------------|
| Static compliance | VT / (Pplat - PEEP) | 60-100 mL/cmH2O |
| Dynamic compliance | VT / (Peak P - PEEP) | 50-80 mL/cmH2O |

---

## ARDS — Acute Respiratory Distress Syndrome

### Berlin Definition (2012)

| Criterion | Requirement |
|-----------|------------|
| Timing | Acute onset within 7 days of known insult or new/worsening respiratory symptoms |
| Chest imaging | Bilateral opacities on CXR or CT — not fully explained by effusions, atelectasis, or nodules |
| Origin of edema | Not fully explained by cardiac failure or fluid overload (echo to exclude if no risk factor) |
| Oxygenation | PaO2/FiO2 <300 mmHg with PEEP or CPAP ≥5 cmH2O |

### ARDS Severity Classification

| Severity | PaO2/FiO2 Ratio | Approximate Mortality |
|----------|-----------------|----------------------|
| Mild | 201-300 | ~27% |
| Moderate | 101-200 | ~32% |
| Severe | ≤100 | ~45% |

### Common Causes of ARDS

**Direct (pulmonary):**
- Pneumonia (most common) — bacterial, viral, fungal, aspiration
- Aspiration of gastric contents
- Inhalation injury — smoke, toxic gases, chlorine
- Pulmonary contusion
- Near-drowning

**Indirect (extrapulmonary):**
- Sepsis (most common indirect cause)
- Major trauma, burns
- Pancreatitis
- Massive transfusion / TRALI
- Drug overdose (heroin, salicylates)
- Cardiopulmonary bypass

### ARDSNET Lung-Protective Ventilation Protocol

**Core targets:**
- Tidal volume: 6 mL/kg IBW (may decrease to 4 mL/kg if Pplat exceeds target)
- Plateau pressure: ≤30 cmH2O
- SpO2 target: 88-95% (accept lower SpO2 to limit FiO2 toxicity)
- pH target: 7.30-7.45 (accept pH 7.20-7.30 with permissive hypercapnia if RR maximized)
- Maximum RR: 35/min to correct acidosis

**ARDSNET Low-PEEP / FiO2 Table:**

| FiO2 | 0.3 | 0.4 | 0.4 | 0.5 | 0.5 | 0.6 | 0.7 | 0.7 | 0.7 | 0.8 | 0.9 | 0.9 | 0.9 | 1.0 |
|------|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|
| PEEP | 5 | 5 | 8 | 8 | 10 | 10 | 10 | 12 | 14 | 14 | 14 | 16 | 18 | 18-24 |

**ARDSNET High-PEEP / FiO2 Table (for moderate-severe ARDS):**

| FiO2 | 0.3 | 0.3 | 0.3 | 0.3 | 0.3 | 0.4 | 0.4 | 0.5 | 0.5 | 0.5-0.8 | 0.8 | 0.9 | 1.0 | 1.0 |
|------|-----|-----|-----|-----|-----|-----|-----|-----|-----|---------|-----|-----|-----|-----|
| PEEP | 5 | 8 | 10 | 12 | 14 | 14 | 16 | 16 | 18 | 20 | 22 | 22 | 22 | 24 |

### Adjunct Therapies for Moderate-Severe ARDS (PF <150)

#### Prone Positioning
- Indication: PF <150 despite optimized ventilation
- PROSEVA trial (2013): 16h prone/day vs supine — 28-day mortality 16% vs 32.8% (p<0.001); absolute risk reduction 16%; NNT 6
- Mechanism: recruits dorsal atelectatic lung, redistributes perfusion, reduces regional stress/strain
- Duration: minimum 16 hours per prone session; continue daily until PF >150 for 4h in supine
- Complications: pressure injuries (face, chest, ASIS, knees), inadvertent extubation/line dislodgement, hemodynamic instability during turns, abdominal hypertension, corneal injury
- Contraindications (relative): anterior wounds/burns, unstable spine, open abdomen, elevated ICP, pregnancy

#### Neuromuscular Blockade (NMB)
- Cisatracurium (Nimbex) infusion 37.5 mg/hr (approximately 0.48 mcg/kg/min); Hofmann elimination — no organ-based clearance
- ACURASYS trial (2010): 48h NMB improved 90-day mortality vs placebo in severe ARDS
- ROSE trial (2019): light sedation comparator — NMB did not improve outcomes vs light sedation without NMB
- Current practice: consider NMB if severe dyssynchrony (breath stacking, reverse triggering), very high drive efforts causing VILI, or to facilitate prone positioning
- Train-of-four monitoring not required for 48h infusion strategy; may use if prolonged NMB planned
- Risks: ICU-acquired weakness, pressure injuries, inability to assess neurologic status

#### Inhaled Vasodilators
- Inhaled nitric oxide (iNO): 5-40 ppm; selective pulmonary vasodilator; improves V/Q matching; transiently improves PaO2 in most patients; no mortality benefit in multiple RCTs; use as bridge to ECMO or transplant, or in severe refractory hypoxemia
- Inhaled epoprostenol (Flolan): similar mechanism to iNO; less expensive; easier administration; no clear outcome difference vs iNO
- Discontinue if no PaO2 response within 4-6h (avoid rebound pulmonary hypertension on abrupt discontinuation of iNO — wean gradually)

#### Conservative Fluid Strategy
- FACTT trial (ARDSNET): conservative fluid management after resuscitation complete — shorter duration of mechanical ventilation and ICU stay; no mortality difference at 60 days
- Targets: CVP 4-6 mmHg (post-resuscitation); daily fluid balance neutral to negative; furosemide or CRRT as needed
- Do not restrict fluids during active resuscitation for shock

#### Corticosteroids in ARDS
- Methylprednisolone: fiboproliferative ARDS (days 7-14, failure to improve, CT findings of organizing pneumonia) — some benefit; early ARDS (within 72h) — conflicting data
- COVID-19 ARDS: dexamethasone 6mg/day x10 days — RECOVERY trial; clear mortality benefit
- Do not use methylprednisolone after day 14 (higher mortality in LaSala trial)

#### VV-ECMO for Severe ARDS
- Criteria: PF <80 mmHg despite optimized management, or pH <7.20 with hypercapnia despite RR 35/min
- EOLIA trial (2018): 60-day mortality 35% VV-ECMO vs 46% conventional (p=0.07); 28% crossover in conventional arm to ECMO
- Best outcomes at high-volume ECMO centers (>20 cases/year)
- Components: drainage cannula (venous), return cannula (venous — to right atrium), centrifugal pump, oxygenator/heat exchanger
- Common cannula configurations: femoro-jugular; femoro-femoral (add second oxygenator for CO2 clearance)
- Anticoagulation: heparin infusion; target anti-Xa 0.3-0.5 or aPTT 60-80 sec
- Complications: circuit thrombosis, bleeding (intracranial hemorrhage most feared), ECMO-associated infection, limb ischemia (distal perfusion cannula), recirculation, North-South syndrome

---

## Ventilator Weaning and Extubation

### Daily Assessment Protocol (ABCDE Bundle)

- **A** — Awakening: daily sedation interruption (SAT) — stop continuous sedation, reassess in morning
- **B** — Breathing: daily SBT coordinated with SAT
- **C** — Coordination: SAT and SBT performed together (paired)
- **D** — Delirium: monitor CAM-ICU twice daily; mobilize early
- **E** — Early mobility: PT/OT at bedside; in-bed cycling, passive ROM, dangling, ambulation with ventilator

### SAT (Spontaneous Awakening Trial) Safety Screen
Stop sedation if ALL of the following:
- No active seizures
- No alcohol withdrawal/agitation requiring high-dose sedation
- No active neuromuscular blockade
- No FiO2 >0.5 or PEEP >8 (relative)
- No active vasopressor escalation within last hour

### SBT Safety Screen (Readiness Criteria)

| Criterion | Threshold |
|-----------|----------|
| FiO2 | ≤0.40 |
| PEEP | ≤5-8 cmH2O |
| SpO2 | >90% |
| RR | <35/min |
| Heart rate | 50-120 bpm |
| SBP | 80-180 mmHg |
| No vasopressor escalation | Past 2-4 hours |
| Alert/cooperative | RASS -1 to +1 |
| No neuromuscular blockade | TOF ratio >0.9 |

### SBT Methods
- **T-piece trial:** patient disconnected from ventilator; 30-120 minutes; measures true WOB but no backup
- **Low-pressure support:** PS 5-8 cmH2O + PEEP 5 x 30-120 minutes; CPAP/PS mode; most common
- Duration: 30 minutes sufficient; prolonged SBT (120 min) no advantage over 30 min

### SBT Failure Criteria (Abort Trial)
- SpO2 <90%, RR >35/min, HR >140 or change >20%, SBP >180 or <90 mmHg
- Anxiety, diaphoresis, use of accessory muscles, paradoxical abdominal movement
- Increasing FiO2 requirement, new arrhythmia

### Extubation Decision

**RSBI (Rapid Shallow Breathing Index):**
- RSBI = RR / Tidal Volume (liters)
- <105 predicts successful extubation (sensitivity 97%, specificity 64%)
- Best used with clinical gestalt, not in isolation

**Post-extubation stridor management:**
- Risk factors: female sex, intubation >6 days, ETT diameter relative to tracheal diameter
- Cuff leak test: deflate cuff; measure leak volume during VC breath; <110 mL or <12% of delivered VT = high risk for post-extubation stridor
- Prevention: methylprednisolone 40mg IV q6h x4 doses starting 12h before planned extubation (Francois 2007 trial)
- Treatment after extubation: heliox (70/30 mixture), racemic epinephrine nebulization, dexamethasone, HFNC, NIV; re-intubation if airway compromise

**Post-extubation support:**
- HFNC for high-risk extubation (cardiac disease, obesity, hypercapnia, age >65): reduces 72h re-intubation rate (Hernandez 2016)
- Prophylactic NIV in patients with chronic hypercapnia (COPD): reduces re-intubation and ICU mortality
- Not indicated for all extubated patients; use risk-stratified approach

### Prolonged Mechanical Ventilation and Tracheostomy

- Definition of prolonged MV: ≥21 days
- Tracheostomy indications: anticipated prolonged MV, failed extubation, airway protection failure, secretion management
- Timing: early (5-7 days) vs late (>10-14 days) — TracMan trial: no mortality benefit to early tracheostomy; clinical judgment guides timing
- Benefits of tracheostomy: reduced sedation requirement, improved mobility, oral feeding possible, patient communication, reduced airway resistance
- Percutaneous dilational tracheostomy (PDT): bedside procedure under bronchoscopic guidance; equivalent complication rate to surgical; faster, cheaper

---

## ICU Sedation and Analgesia

### Assessment Tools

#### CPOT — Critical-Care Pain Observation Tool
For non-verbal intubated patients. Score 0-8:

| Domain | Score 0 | Score 1 | Score 2 |
|--------|---------|---------|---------|
| Facial expression | Relaxed | Tense/grimacing | Distorted/furrowed brow |
| Body movements | No movements/normal | Protective/guarding | Pulling tubes/agitated |
| Muscle tension (passive flexion) | No resistance | Resistance | Strong resistance |
| Compliance (intubated) | Tolerating vent | Coughing but tolerating | Fighting vent |

Score >2 indicates significant pain; treat before reassessing.

#### RASS — Richmond Agitation-Sedation Scale

| Score | Term | Description |
|-------|------|-------------|
| +4 | Combative | Violent, danger to staff |
| +3 | Very agitated | Pulls/removes tubes/lines, aggressive |
| +2 | Agitated | Frequent nonpurposeful movement, fights vent |
| +1 | Restless | Anxious, movements not aggressive |
| 0 | Alert and calm | Spontaneously awake, calm |
| -1 | Drowsy | Not fully alert; eye opening/contact to voice >10 sec |
| -2 | Light sedation | Brief eye opening to voice, no eye contact |
| -3 | Moderate sedation | Movement/eye opening to voice, no eye contact |
| -4 | Deep sedation | No response to voice; movement/eye opening to physical stimulation |
| -5 | Unarousable | No response to voice or physical stimulation |

**Target:** RASS -1 to 0 for most ventilated ICU patients. Deep sedation (RASS -3 to -5) associated with longer MV, more delirium, higher mortality.

### Sedation Agents

#### Propofol
- Mechanism: GABA-A receptor agonist; lipid emulsion vehicle
- Onset: 30-60 seconds; offset: 5-15 minutes (context-sensitive half-life increases with prolonged infusion)
- Dose: 5-50 mcg/kg/min infusion; titrate to RASS target
- Advantages: rapid titration, anticonvulsant properties, bronchodilatory, amenable to daily awakenings
- Disadvantages:
  - Hypotension (cardiac depression + vasodilation) — common on initiation
  - Hypertriglyceridemia: check triglycerides q48-72h; hold if >400 mg/dL
  - Propofol Infusion Syndrome (PIS): rare but fatal; high dose (>70-80 mcg/kg/min) prolonged (>48-72h); features: severe lactic acidosis, rhabdomyolysis, acute cardiomyopathy, hyperkalemia, renal failure, lipemic plasma; treat with immediate cessation, aggressive supportive care, possible ECMO
  - Pain on peripheral IV injection
  - 1.1 kcal/mL from lipid vehicle — account in nutritional calculations
  - Contains egg lecithin — caution with egg allergy (not absolute CI)

#### Dexmedetomidine
- Mechanism: selective alpha-2 adrenergic agonist (central alpha-2A receptors in locus coeruleus)
- Produces cooperative, arousable sedation — patient responds to commands and verbal stimulation
- Does not cause respiratory depression — can be used in non-intubated patients
- Dose: 0.2-1.5 mcg/kg/hr continuous infusion; NO loading dose in ICU (loading dose causes transient hypertension)
- Advantages: reduces delirium vs benzodiazepines (MENDS, SEDCOM trials); reduces opioid and sedative requirements; cooperative sedation ideal for awake procedures, tracheostomy, NIV
- Disadvantages: bradycardia (can be significant — have atropine available), hypotension; expensive; does not reliably achieve deep sedation; not effective for ETOH/benzo withdrawal seizures
- MENDS2 trial: dexmedetomidine vs propofol in mechanically ventilated patients — similar outcomes

#### Midazolam
- Mechanism: GABA-A benzodiazepine receptor agonist
- Onset: 2-5 minutes IV; offset variable (active metabolite 1-hydroxymidazolam accumulates in hepatic/renal dysfunction)
- Dose: 0.02-0.1 mg/kg/hr infusion; 1-5 mg IV bolus for procedures
- Advantages: amnestic, anticonvulsant, anxiolytic, short initial effect
- Disadvantages: accumulation with prolonged infusion; delirium (increases delirium >2x vs dexmedetomidine/propofol); tolerance; withdrawal (requires slow taper); paradoxical agitation (especially elderly)
- Indications in ICU: ETOH withdrawal (CIWA-based protocol), seizure management, procedures, status epilepticus, short-duration procedural sedation

#### Lorazepam
- Longer-acting benzodiazepine; less lipophilic than midazolam
- Less accumulation than midazolam in renal failure
- IV infusion: propylene glycol vehicle — can cause elevated osmol gap and anion gap metabolic acidosis with high-dose prolonged infusion; monitor osmol gap; maximum infusion rate 2 mg/min
- Used for ETOH withdrawal, seizures; less common as primary ICU sedation infusion

#### Ketamine
- Mechanism: NMDA receptor antagonist; also opioid, muscarinic, nicotinic, sigma receptor activity
- Dissociative anesthetic at higher doses; subanesthetic at 0.1-0.5 mg/kg/hr infusion
- Advantages: hemodynamically stimulating (catecholamine release — useful in hypotensive patients); bronchodilator (smooth muscle relaxation — useful in severe bronchospasm/status asthmaticus); preserves airway reflexes and spontaneous breathing at subanesthetic doses; analgesic properties; opioid-sparing
- Disadvantages: emergence phenomena (hallucinations, dysphoria) at subanesthetic/anesthetic doses — attenuate with concurrent low-dose benzodiazepine or propofol; increases oral/airway secretions (glycopyrrolate pretreatment); raises ICP (controversial — avoid in isolated TBI; acceptable in multitrauma)
- Intubation induction: 1-2 mg/kg IV (hemodynamically unstable patient, bronchospasm)
- PSV sedation: 0.1-0.5 mg/kg/hr infusion (opioid-sparing protocol)

### Analgesic Agents

#### IV Opioids

| Agent | Dose | Onset | Notes |
|-------|------|-------|-------|
| Fentanyl | 25-100 mcg IV bolus; 25-200 mcg/hr infusion | 1-3 min | No histamine release; short context-sensitive half-life; metabolites inactive; preferred in hemodynamic instability, renal failure |
| Hydromorphone | 0.2-0.5 mg IV q2-3h PRN; 0.2-0.5 mg/hr infusion | 5-10 min | 5-7x more potent than morphine; active metabolite (hydromorphone-3-glucuronide) can accumulate in renal failure and cause neuroexcitatory effects |
| Morphine | 2-4 mg IV q3-4h PRN | 5-10 min | Histamine release (hypotension, bronchospasm); active metabolite morphine-6-glucuronide accumulates in renal failure; avoid in ESRD |
| Remifentanil | 0.05-0.3 mcg/kg/min infusion | <1 min | Ultra-short acting; ester hydrolysis by blood and tissue esterases — no organ clearance; ideal for neurological patients needing frequent assessments; tolerance develops rapidly; no bolus dosing |

#### Non-Opioid Analgesics
- **IV Acetaminophen:** 1g IV q6h (opioid-sparing 20-30%); safe in most ICU patients; avoid in hepatic failure (AST/ALT >3x normal)
- **Ketorolac:** 15-30 mg IV q6h (max 5 days); NSAID; effective for musculoskeletal/post-operative pain; avoid with AKI, GI bleeding risk, thrombocytopenia
- **Ketamine (subanesthetic):** 0.1-0.5 mg/kg/hr; see above
- **Lidocaine infusion:** 1-1.5 mg/kg/hr; opioid-sparing; evidence in post-operative settings; monitor for toxicity (cardiac arrhythmia, seizure)
- **Gabapentin/pregabalin:** neuropathic pain, opioid-sparing; sedation and dizziness; renal dose adjustment
- **Regional analgesia:** epidural, paravertebral, intercostal, fascial plane blocks — significant opioid-sparing; TEA (thoracic epidural analgesia) for rib fractures and thoracotomy

### ABCDEF Bundle

| Letter | Component | Key Actions |
|--------|-----------|-------------|
| A | Assess, prevent, manage pain | CPOT/NRS q4h; analgesia-first approach; multimodal analgesia |
| B | Both SAT and SBT | Coordinate daily awakening with breathing trial |
| C | Choice of analgesia/sedation | Target light sedation (RASS -1 to 0); minimize benzodiazepines |
| D | Delirium: assess, prevent, manage | CAM-ICU twice daily; non-pharm interventions; avoid precipitants |
| E | Early mobility and exercise | PT/OT consult day 1-2; in-bed exercise, ambulation with vent |
| F | Family engagement | Daily family meetings; include in care rounds; PICS-F prevention |

Implementation of ABCDEF bundle associated with reduced delirium, shorter MV, lower mortality (Pun 2019 — 15,000 patient ICU Liberation Collaborative).

---

## ICU Delirium

### Definition and Epidemiology
- Acute change in mental status characterized by fluctuating course, inattention, and either disorganized thinking or altered level of consciousness
- Prevalence: 60-80% in mechanically ventilated patients; 20-50% in non-mechanically ventilated ICU patients
- Associated with increased mortality, longer ICU/hospital stay, long-term cognitive impairment, increased costs

### CAM-ICU Assessment

**Feature 1:** Acute onset or fluctuating course in mental status (RASS changes or information from nurse/family)

**Feature 2:** Inattention — Auditory: "squeeze my hand when you hear the letter A" in the sequence SAVEAHAART (errors >2 = positive); Visual: picture recognition test

**Feature 3:** Altered level of consciousness — RASS other than 0 = positive

**Feature 4:** Disorganized thinking — 4 yes/no questions + follow 2 simple commands (hold up fingers, move toes); errors >1 = positive

**CAM-ICU positive:** Feature 1 AND Feature 2 AND (Feature 3 OR Feature 4)
- If RASS -4 or -5: cannot assess — mark as "unable to assess" (UTA)
- Reassess at RASS ≥ -3

### Delirium Subtypes

| Subtype | Characteristics | Frequency | Prognosis |
|---------|-----------------|-----------|-----------|
| Hyperactive | Agitation, pulling lines/tubes, combativeness | ~25% | Better recognized, treated early |
| Hypoactive | Quiet, withdrawn, decreased responsiveness | ~50% | Most common; frequently missed; worse outcomes |
| Mixed | Alternating between hyper- and hypoactive features | ~25% | Variable |

### Risk Factors for ICU Delirium

**Patient factors:**
- Advanced age (>65)
- Pre-existing cognitive impairment or dementia
- Prior history of delirium
- Severe illness, organ failure
- Visual/hearing impairment
- Alcohol use disorder

**ICU-related factors:**
- Sleep deprivation (fragmented, light-cycle disruption)
- Immobility
- Physical restraints
- Sensory deprivation (no glasses, no hearing aids)
- Pain (undertreated)
- Benzodiazepines (strongest modifiable risk factor)
- High-dose opioids
- Anticholinergic medications (diphenhydramine, promethazine, atropine)
- Steroids
- Polypharmacy

### Non-Pharmacological Prevention and Management
- Reorientation: frequent verbal reorientation to time/place/situation; whiteboard with date/location
- Sleep hygiene protocol: ear plugs + eye masks at night; cluster nursing care; melatonin 3-10 mg QHS; minimize overnight interruptions; dim lights at night, bright lights during day
- Hearing aids and glasses: restore as early as possible (day 1)
- Early mobility: ABCDE bundle (PT/OT); in-bed cycling; ambulation with ventilator
- Family involvement: familiar voices, photos; video calls; family presence at bedside
- Cognitive stimulation: TV/radio during day; simple games; music therapy
- Avoid restraints when possible; remove unnecessary catheters and lines

### Pharmacological Management of Delirium
- No agent is FDA-approved for ICU delirium
- **Haloperidol:** D2 antagonist; 0.5-2 mg IV/IM q4-8h PRN for hyperactive delirium; HOPE-ICU (2018) and MIND-USA (2018) trials — did not reduce delirium days or mortality; QTc prolongation risk (check baseline QTc); avoid if QTc >500ms; extrapyramidal side effects
- **Quetiapine:** 25-50 mg PO/NG BID, titrate to 200 mg BID; sedating; useful for hyperactive delirium with sleep disruption; fewer EPS than haloperidol; QTc monitoring required
- **Dexmedetomidine:** reduces delirium incidence vs benzodiazepines; can be used as both sedative and anti-delirium agent in agitated delirium; approved for non-intubated patients (AWAKEN trial evidence)
- **Avoid:** benzodiazepines worsen delirium (use only for ETOH/benzo withdrawal); antipsychotics do not prevent delirium — use only for symptom management; diphenhydramine contraindicated

---

## Hemodynamic Monitoring

### Basic Monitoring
- Continuous ECG: lead II for rhythm, lead V5 for ischemia; 5-lead monitoring in cardiac ICU
- Pulse oximetry: SpO2; limitations — poor perfusion states, motion artifact, carboxyhemoglobin/methemoglobin (overestimation of SpO2), skin pigmentation, nail polish
- ETCO2: end-tidal CO2; waveform capnography for intubation confirmation, CPR quality, ROSC detection; trending for changes in cardiac output and dead-space ventilation

### Arterial Line
- Indications: continuous BP monitoring, frequent ABG sampling, hemodynamic instability requiring vasopressors
- Sites: radial (most common — collateral circulation from ulnar artery); femoral (if radial unavailable, larger vessel — for IABP, ECMO cannulation); brachial (avoid — end artery); dorsalis pedis
- Allen's test: occlusion of radial + ulnar arteries; release ulnar; normal refill <6 sec indicates ulnar collaterals; controversial utility
- Complications: thrombosis (radial artery 5-25% occlusion, usually asymptomatic), infection (CLABSI equivalent — use sterile insertion technique), air embolism (purge air from all connections), pseudo-aneurysm, hematoma
- Arterial waveform interpretation: upstroke = ventricular ejection; dicrotic notch = aortic valve closure; area under curve correlates with stroke volume

### Central Venous Catheter (CVC)
- Indications: vasopressors, concentrated electrolyte infusions, central venous access for multiple drips, hemodynamic monitoring (CVP, ScvO2), inadequate peripheral access
- Sites: internal jugular (IJ) — right preferred (straight path to SVC); subclavian — lowest infection risk, highest pneumothorax risk; femoral — highest infection risk, DVT risk, use only when other sites unavailable; PICC for prolonged access needs

**CLABSI Prevention Bundle:**
1. Hand hygiene before insertion and manipulation
2. Maximal sterile barrier precautions (cap, mask, sterile gown, gloves, large drape)
3. Chlorhexidine skin antisepsis (>0.5% CHG in 70% alcohol — wait to dry)
4. Optimal site selection (avoid femoral when possible)
5. Daily necessity review — remove when no longer needed
6. Chlorhexidine-impregnated dressings and antimicrobial-coated catheters in high-risk patients

**Complications:**
- Pneumothorax (subclavian >IJ): CXR after insertion; needle decompression if tension physiology
- Arterial puncture: apply direct pressure; vascular surgery if large dilator/catheter placed arterially
- Air embolism: Trendelenburg + left lateral decubitus; aspirate through catheter; 100% O2; hyperbaric O2 if refractory
- CLABSI: fever/bacteremia with CVC; remove catheter if Staph aureus, Candida, or hemodynamic instability

### Pulmonary Artery Catheter (PAC / Swan-Ganz)

**Measured parameters:**
- Right atrial pressure (RAP) = CVP: normal 2-6 mmHg; elevated in right heart failure, tricuspid regurgitation, tamponade, constrictive pericarditis, PHTN
- Right ventricular pressure (RVP): systolic/diastolic; systolic = RVSP; elevated in PHTN, pulmonic stenosis
- Pulmonary artery pressure (PAP): systolic/diastolic/mean; MPAP >20 mmHg = pulmonary hypertension (updated 2022 criteria)
- Pulmonary artery wedge pressure (PAWP/PCWP): reflects left atrial pressure; normal 6-12 mmHg; elevated in left heart failure, mitral stenosis, mitral regurgitation; low in hypovolemia, septic shock

**Derived parameters:**

| Parameter | Formula | Normal |
|-----------|---------|--------|
| Cardiac output (thermodilution) | Measured directly | 4-8 L/min |
| Cardiac index | CO / BSA | 2.2-4.0 L/min/m2 |
| SVR | (MAP - CVP) / CO x 80 | 800-1200 dyn·sec/cm5 |
| PVR | (MPAP - PCWP) / CO x 80 | 20-120 dyn·sec/cm5 |
| SvO2 | Measured from PAC tip (PA blood) | 60-75% |

**Hemodynamic profiles:**

| Shock Type | CO/CI | SVR | PCWP | CVP | SvO2 |
|------------|-------|-----|------|-----|------|
| Septic (distributive) | High | Low | Low/normal | Low | High (early) |
| Cardiogenic | Low | High | High | High | Low |
| Hypovolemic | Low | High | Low | Low | Low |
| Obstructive (PE, tamponade) | Low | High | Low/High | High | Low |

**Complications:** arrhythmias during insertion (RBBB — 3%, complete heart block if pre-existing LBBB), pulmonary artery rupture (rare but fatal — balloon overinflation, elderly, PHTN), catheter knotting, infection, thrombosis, valve damage

**Limitations/Controversies:** PAC-Man trial and FACTT trial — no mortality benefit in ICU patients; PAC interpretation errors common (CV fellows — tricuspid level vs RA, respiratory variation); does not improve outcomes but provides physiologic data for targeted therapy

### Point-of-Care Echocardiography (POCUS)

**Indications:** unexplained hypotension, suspected tamponade, suspected PE, cardiac arrest (PEA evaluation), volume responsiveness assessment, LV/RV function evaluation

**Key views:**
- Parasternal long-axis (PLAX): LV size/function, pericardial effusion, aortic root, mitral valve
- Parasternal short-axis (PSAX): LV/RV size, septal motion, RWMA, mitral valve
- Apical 4-chamber: biventricular size/function, mitral/tricuspid valve
- Subcostal: pericardial effusion (best view for tamponade), IVC assessment, tricuspid/mitral

**IVC assessment for volume responsiveness:**
- IVC collapsibility index: (IVC max - IVC min) / IVC max x 100%
- >50% collapsibility in spontaneously breathing patients → volume responsive
- <18% change in mechanically ventilated patients (passive ventilation) → not volume responsive
- Limitations: PEEP, spontaneous breathing, arrhythmias reduce reliability

**Pulse pressure variation (PPV) and stroke volume variation (SVV):**
- In fully mechanically ventilated, no spontaneous breathing: PPV >13% or SVV >13% predicts volume responsiveness with good sensitivity/specificity
- Requires: regular rhythm, no spontaneous breaths, TV ≥8 mL/kg (PPV unreliable with lower TV)

---

## Vasopressors and Hemodynamic Support

### Vasopressor Pharmacology

#### Norepinephrine (Levophed)
- Mechanism: alpha-1 (strong) > beta-1 (moderate); vasopressor + mild inotrope
- First-line vasopressor in septic shock — CATS trial (de Backer 2010): lower 28-day mortality vs dopamine; fewer arrhythmias
- Dose: 0.01-3 mcg/kg/min; start at 0.05-0.1 mcg/kg/min; titrate to MAP ≥65
- Hemodynamic effects: increased MAP, SVR, and cardiac afterload; mild increase in HR and CO
- Requires central line (extravasation causes tissue necrosis — phentolamine antidote)
- Peripheral administration acceptable for short-term (<30-60 minutes) in emergencies while central access obtained

#### Vasopressin
- Mechanism: V1 receptor (vascular smooth muscle) → vasoconstriction; V2 receptor (renal collecting duct) → free water reabsorption
- Second-line in septic shock (add when norepinephrine dose escalating)
- Fixed dose: 0.03-0.04 units/min (no titration); higher doses associated with cardiac ischemia, mesenteric ischemia
- VASST trial: vasopressin + norepinephrine vs norepinephrine alone — similar mortality; vasopressin-sparing catecholamine effect; possible mortality benefit in less severe septic shock (NE <15 mcg/min)
- Useful when norepinephrine doses exceeding 0.25-0.5 mcg/kg/min

#### Phenylephrine
- Mechanism: pure alpha-1 agonist; vasoconstriction without direct cardiac stimulation
- Reduces cardiac output (reflex bradycardia + increased afterload) — avoid in cardiogenic shock or low CO states
- Indications: tachycardia-induced hemodynamic compromise (SVT with hypotension, LVOTO/HOCM), spinal shock, vasodilatory hypotension where tachycardia undesirable
- Dose: 50-200 mcg/min infusion; 100-200 mcg IV bolus for acute hypotension (procedural)
- Available as premixed infusion and bolus formulation

#### Dopamine
- Mechanism: dose-dependent — D1 (renal/splanchnic vasodilation, <5 mcg/kg/min); beta-1 inotrope/chronotrope (5-10 mcg/kg/min); alpha-1 vasoconstriction (>10 mcg/kg/min)
- Low-dose "renal dose" dopamine: DOES NOT protect kidneys — multiple RCTs negative; DO NOT USE for renal protection
- Higher arrhythmia rate than norepinephrine — CATS trial
- Use is largely obsolete in septic shock; may have role in cardiogenic shock (moderate doses)
- Dose: 2-20 mcg/kg/min

#### Epinephrine
- Mechanism: equal alpha + beta activity; high beta at low doses → lower doses more chronotropic/inotropic; at high doses → predominantly vasoconstrictive
- Indications: anaphylaxis (IM 0.3-0.5 mg 1:1000), cardiac arrest (1 mg IV q3-5 min), cardiogenic shock (second/third line), refractory septic shock
- ICU infusion dose: 0.01-0.5 mcg/kg/min
- Side effects: tachycardia, lactic acidosis (beta-2-mediated glycogenolysis + splanchnic vasoconstriction causing lactate release — not indicative of hypoperfusion), hypokalemia

#### Dobutamine
- Mechanism: beta-1 (strong) > beta-2; positive inotropy (increases contractility and HR) + mild vasodilation (beta-2)
- Primary indication: cardiogenic shock (add to norepinephrine to improve cardiac output)
- Dose: 2-20 mcg/kg/min; titrate to hemodynamic response
- Side effects: tachycardia, hypotension (vasodilation), arrhythmias; tachyphylaxis with >72h infusion (receptor downregulation)
- Avoid as sole agent in hypotension (vasodilatory effect may worsen MAP without adequate vasopressor)

#### Milrinone
- Mechanism: phosphodiesterase-3 (PDE3) inhibitor; reduces cAMP breakdown → positive inotrope + vasodilator (inodilator)
- Less tachycardia than dobutamine; more vasodilation
- Renally cleared — dose reduction required in CKD/AKI
- Preferred in right ventricular failure (reduces PVR), post-cardiac surgery low CO, decompensated HF
- Avoid in severe hypotension without adequate vasopressor support
- Dose: 0.125-0.75 mcg/kg/min; loading dose (50 mcg/kg) rarely used in ICU (profound hypotension)

### MAP Targets by Condition

| Condition | MAP Target | Evidence |
|-----------|-----------|---------|
| Septic shock | ≥65 mmHg | SEPSISPAM trial — 65 vs 85 mmHg: no outcome difference; less RRT needed in chronic hypertensives at MAP 85 |
| Post-cardiac arrest | ≥65-80 mmHg | Higher MAP (80-100) may benefit brain perfusion — some protocols; TTM trial did not specify MAP |
| TBI | ≥80-90 mmHg | CPP ≥60 mmHg; ICP-guided management; BTF guidelines |
| Hypertensive crisis | Reduce MAP 20-25% in first hour | Avoid rapid overcorrection (cerebral autoregulation) |
| Aortic dissection | SBP 100-120 mmHg | HR <60-80; beta-blockade first |
| Spinal cord injury | MAP 85-90 for 7 days | Improved perfusion of injured cord; vasopressor if needed |

---

## Shock Syndromes

### Classification of Shock

| Type | Mechanism | CO | SVR | Examples |
|------|-----------|-----|-----|---------|
| Distributive | Vasodilation, maldistribution of flow | High (early) | Low | Sepsis, anaphylaxis, neurogenic, adrenal crisis |
| Cardiogenic | Pump failure | Low | High | AMI, myocarditis, cardiomyopathy, arrhythmia |
| Hypovolemic | Volume depletion | Low | High | Hemorrhage, dehydration, third-spacing |
| Obstructive | Physical obstruction to flow | Low | High | Tension PTX, PE, tamponade |

### Septic Shock

**Definition (Sepsis-3, 2016):**
- Sepsis: life-threatening organ dysfunction from dysregulated host response to infection
- Septic shock: subset of sepsis with persisting hypotension (MAP <65 mmHg) requiring vasopressors + serum lactate >2 mmol/L after adequate fluid resuscitation
- qSOFA screen (non-ICU): RR ≥22, altered mentation, SBP ≤100 — 2 or more criteria = investigate for sepsis

**Hour-1 Bundle (Surviving Sepsis Campaign 2018):**
1. Measure lactate (repeat if initial >2)
2. Draw blood cultures x2 before antibiotics
3. Administer broad-spectrum antibiotics (within 1 hour of recognition)
4. Administer 30 mL/kg crystalloid IV for hypotension or lactate ≥4
5. Apply vasopressors for MAP <65 mmHg

**Resuscitation targets:**
- MAP ≥65 mmHg
- Normalize lactate (lactate-guided resuscitation — ANDROMEDA-SHOCK trial vs ScvO2 guidance)
- ScvO2 ≥70% (central venous oxygen saturation from CVC at SVC/RA junction)
- UO ≥0.5 mL/kg/hr
- Avoid fluid overload — liberal fluid strategy associated with worse outcomes (SMART trial, SPLIT trial)

**Antibiotics in septic shock:**
- Within 1 hour of recognition (each hour delay = increased mortality — Kumar 2006)
- Broad empiric coverage: gram-positive (MRSA if risk) + gram-negative (including Pseudomonas if risk) + consider anaerobic coverage (intraabdominal source)
- Common regimens: vancomycin + pip-tazo; vancomycin + meropenem (immunocompromised); ceftriaxone + metronidazole (community CAP + abdominal)
- De-escalate within 48-72h based on culture results and clinical response
- Duration: 7 days for most sources; 14 days for bacteremia; 4-6 weeks for endocarditis/osteomyelitis

**Steroids in septic shock:**
- Hydrocortisone 200 mg/day continuous infusion (or 50 mg q6h) — for refractory septic shock (norepinephrine ≥0.25 mcg/kg/min) per IDSA/SSC guidelines
- ADRENAL trial: hydrocortisone did not reduce 90-day mortality but shortened time on vasopressors
- APROCCHSS trial: hydrocortisone + fludrocortisone reduced 90-day mortality (49% vs 43%)
- Consider in suspected adrenal insufficiency (prior steroid use, adrenal hemorrhage)

### Cardiogenic Shock

**Etiology:**
- AMI (most common — 40-80% due to STEMI/NSTEMI)
- Acute decompensated heart failure
- Myocarditis (fulminant)
- Takotsubo cardiomyopathy
- Arrhythmia (prolonged VT, rapid AF, complete heart block)
- Mechanical complications of MI (papillary muscle rupture → acute MR, VSD, free wall rupture)

**Hemodynamic criteria:** CI <1.8 L/min/m2 (without support) or <2.0 with support + PCWP >15 + SBP <90 for >30 min (or vasopressors needed)

**Management:**
- Treat underlying cause: primary PCI for AMI (door-to-balloon ≤90 min), rate control/cardioversion for arrhythmia
- Hemodynamic support: norepinephrine (vasopressor) + dobutamine (inotrope); avoid large fluid boluses (already volume overloaded)
- Mechanical circulatory support (MCS):
  - IABP (Intra-aortic balloon pump): 1:1 counterpulsation; reduces afterload; increases coronary perfusion; IABP-SHOCK II — no mortality benefit in AMI cardiogenic shock; still used in mechanical complications, arrhythmia-refractory shock
  - Impella CP/5.5: axial flow pump via aortic valve; provides 3.5-5.5 L/min; UNLOAD and PROTECT trials — hemodynamic benefit; IMPRESS trial in AMICS — no mortality benefit; RECOVER IV ongoing
  - TandemHeart: external centrifugal pump; LA to femoral artery; highest hemodynamic support but complex insertion
  - VA-ECMO: veno-arterial ECMO; full hemodynamic support (4-6 L/min); indication in refractory cardiogenic shock; ECMO-CS ongoing trial; complications: LV distension (combine with Impella — "ECPella"), limb ischemia, bleeding

### Anaphylaxis and Anaphylactic Shock

**Diagnosis:** at least one of:
1. Acute skin involvement + airway compromise or hypotension after allergen exposure
2. Two or more of: skin involvement, airway compromise, hypotension, GI symptoms after likely allergen exposure
3. Hypotension after exposure to known allergen

**Treatment:**
- Epinephrine IM: 0.3-0.5 mg (1:1000) in anterolateral thigh — FIRST AND MOST IMPORTANT treatment
- Position: supine with legs elevated (unless respiratory compromise — then upright)
- Supplemental oxygen; 100% NRB
- IV access and fluid resuscitation (1-2 L crystalloid for distributive hypotension)
- Antihistamines (diphenhydramine 25-50 mg IV, ranitidine 50 mg IV) — adjunctive only, do NOT delay epinephrine
- Corticosteroids (methylprednisolone 125 mg IV) — prevent biphasic reaction; onset 4-8h; do NOT substitute for epinephrine
- Refractory anaphylaxis: IV epinephrine infusion 0.05-0.5 mcg/kg/min; glucagon 1-2 mg IV q5 min for patients on beta-blockers (glucagon reverses beta-blockade); vasopressin; methylene blue (for refractory vasodilation)
- Observation: minimum 4-6 hours after resolution; 12-24h if severe reaction or asthma history

### Hemorrhagic Shock

**Classification:**

| Class | Blood Loss | HR | BP | RR | Mental Status |
|-------|-----------|----|----|-----|--------------|
| I | <750 mL (<15%) | <100 | Normal | 14-20 | Anxious |
| II | 750-1500 mL (15-30%) | 100-120 | Decreased pulse pressure | 20-30 | Anxious |
| III | 1500-2000 mL (30-40%) | 120-140 | Decreased SBP | 30-40 | Confused |
| IV | >2000 mL (>40%) | >140 | Very low | >35 | Lethargic |

**Damage Control Resuscitation:**
- Permissive hypotension: target SBP 80-90 mmHg in penetrating trauma until surgical hemorrhage control (avoid excess fluid diluting clotting factors)
- TXA: 1g IV over 10 min then 1g over 8 hours within 3 hours of injury (CRASH-2)
- 1:1:1 ratio: pRBC:FFP:platelets (PROPPR trial — reduced 24h and 30-day mortality vs 2:1:1)
- Goal-directed resuscitation with TEG/ROTEM: viscoelastic testing to guide targeted product replacement
- Massive transfusion protocol (MTP) activation: 10+ units pRBC in 24h, hemodynamic instability with active bleeding

**Targets after resuscitation:**
- Hgb: 7-8 g/dL (lower threshold reduces transfusion without worse outcomes — TRICC trial)
- Platelets: >50,000/mcL (>100,000/mcL for intracranial or ophthalmic surgery)
- Fibrinogen: >150-200 mg/dL (cryoprecipitate — each bag contains ~250 mg fibrinogen; dose 10 bags)
- INR: <1.5x normal (4-factor PCC preferred over FFP for rapid reversal)
- Ionized calcium: >1.1 mmol/L (give 1g calcium gluconate or 0.5g calcium chloride per 2-4 units blood — citrate chelation)
- Temperature: >35°C (hypothermia worsens coagulopathy)
- pH: >7.20 (acidosis impairs coagulation enzymes)

---

## Sepsis and Infection in the ICU

### ICU-Acquired Infections

#### Ventilator-Associated Pneumonia (VAP)
- Definition: pneumonia occurring ≥48h after intubation; new infiltrate + 2 of: fever/hypothermia, leukocytosis/leukopenia, purulent sputum, decline in oxygenation
- VAP bundle (prevention):
  - Head-of-bed elevation 30-45 degrees
  - Daily awakening trial and SBT
  - Peptic ulcer prophylaxis (PPI or H2 blocker)
  - DVT prophylaxis
  - Oral chlorhexidine care q6-12h (for cardiac surgery patients; controversial in medical ICU)
  - Subglottic suction ETT (in patients expected to be intubated >72h)
  - Avoid unnecessary circuit changes (q7 days max)
- Empiric antibiotics: cover Pseudomonas, Staph aureus (vancomycin or linezolid if MRSA risk); duration 7 days if clinical improvement

#### Catheter-Associated UTI (CAUTI)
- Most common HAI; Foley catheter indications: urinary retention, accurate UO measurement (hemodynamic instability, diuresis), perineal wound care, comfort care
- Prevention: insert only when indicated; remove as soon as possible (daily review); sterile insertion technique; maintain closed drainage system; avoid dependent loops
- Diagnosis: symptomatic (fever/dysuria/flank pain) + pyuria + culture ≥10^3 CFU/mL in catheterized patient
- Asymptomatic bacteriuria: DO NOT TREAT (except pregnancy, prior to urologic surgery)

#### CLABSI (Central Line-Associated Bloodstream Infection)
- Prevention: see CVC section (insertion bundle + maintenance bundle)
- Diagnosis: bacteremia with CVC in place + no other identifiable source; or culture differential time >2h between central and peripheral draws
- Management: remove catheter if Staph aureus, Candida species, MDR organisms, hemodynamic instability; antibiotic lock therapy for difficult-access patients with CoNS
- Duration: uncomplicated CoNS CLABSI after catheter removal — 5-7 days; Staph aureus — minimum 14 days (TEE to exclude endocarditis); Candida — 14 days after last positive culture

### Antibiotic Stewardship in ICU
- De-escalation: narrow spectrum within 48-72h based on cultures
- Duration: shortest effective course — procalcitonin-guided discontinuation reduces antibiotic exposure (PRORATA trial)
- PKPD optimization: continuous infusion beta-lactams (time-dependent killing); aminoglycoside once-daily dosing (concentration-dependent + PAE); vancomycin AUC/MIC-guided dosing (target AUC 400-600)
- TDM (therapeutic drug monitoring): vancomycin AUC/MIC; aminoglycosides (peak/trough); colistin; voriconazole

---

## Renal Replacement Therapy in the ICU

### AKI Classification (KDIGO)

| Stage | Creatinine Criterion | Urine Output Criterion |
|-------|---------------------|------------------------|
| Stage 1 | 1.5-1.9x baseline or ≥0.3 mg/dL rise within 48h | <0.5 mL/kg/hr for 6-12 hours |
| Stage 2 | 2.0-2.9x baseline | <0.5 mL/kg/hr for ≥12 hours |
| Stage 3 | ≥3.0x baseline, or ≥4.0 mg/dL, or RRT initiated | <0.3 mL/kg/hr for ≥24h or anuria ≥12h |

### Indications for RRT
**Absolute (AEIOU):**
- A: Acidosis — severe metabolic acidosis (pH <7.10-7.15) refractory to bicarbonate
- E: Electrolytes — severe hyperkalemia (K >6.5 or refractory to medical management) with EKG changes
- I: Intoxication — dialyzable toxins (methanol, ethylene glycol, salicylates, lithium, valproate)
- O: Volume Overload — severe fluid overload refractory to diuretics (pulmonary edema, anasarca)
- U: Uremia — encephalopathy, pericarditis, bleeding (platelet dysfunction)

**Timing controversy:** ELAIN trial (early vs delayed CRRT) — early benefit; AKIKI trial — no benefit to early RRT; STARRT-AKI — standard timing noninferior; current practice: initiate for absolute indications; clinical judgment for borderline cases

### RRT Modalities

| Modality | Mechanism | Duration | Hemodynamics | Advantages |
|----------|-----------|----------|-------------|----------|
| IHD (intermittent hemodialysis) | Diffusion | 3-4h, 3x/week | Requires stable BP | High-efficiency clearance, cost |
| CRRT (continuous) | Diffusion + convection | 24h/day | Tolerated in shock | Hemodynamic stability, gradual fluid removal, brain-edema management |
| SLED (sustained low-efficiency) | Diffusion | 6-12h/day | Intermediate | Flexibility, uses IHD machine |

### CRRT Prescriptions

**Modalities:**
- CVVH (continuous venovenous hemofiltration): convection only; replacement fluid
- CVVHD (continuous venovenous hemodialysis): diffusion only; dialysate
- CVVHDF (continuous venovenous hemodiafiltration): both; highest clearance

**Dose:**
- Target 20-25 mL/kg/hr effluent — RENAL and ATN trials — higher doses (35 mL/kg/hr) did not improve outcomes
- Account for filter downtime — prescribe 25-30 mL/kg/hr to achieve delivered dose of 20-25

**Anticoagulation:**
- Regional citrate anticoagulation (RCA): citrate infused into blood before filter; chelates calcium → inhibits coagulation; calcium replaced after filter; preferred when systemic anticoagulation contraindicated; monitor ionized Ca (pre-filter goal 0.25-0.35, post-filter 1.0-1.2)
- Heparin: systemic anticoagulation; aPTT target 45-60 sec; use if thrombosis risk higher than bleeding risk
- No anticoagulation: high bleeding risk; shorter filter life

**Nutrition during CRRT:**
- Amino acid losses: 10-15 g/day; increase protein to 2-2.5 g/kg/day
- Trace element losses: increase replacement
- Phosphate losses may be significant — supplementation often required

---

## Neurological Emergencies in the ICU

### Traumatic Brain Injury (TBI)

**GCS Score:**

| Component | Response | Score |
|-----------|---------|-------|
| Eye opening | Spontaneous | 4 |
| | To voice | 3 |
| | To pain | 2 |
| | None | 1 |
| Verbal | Oriented | 5 |
| | Confused | 4 |
| | Words | 3 |
| | Sounds | 2 |
| | None | 1 |
| Motor | Obeys commands | 6 |
| | Localizes | 5 |
| | Withdraws | 4 |
| | Flexion (decorticate) | 3 |
| | Extension (decerebrate) | 2 |
| | None | 1 |

GCS 3-8 = severe TBI; GCS 9-12 = moderate; GCS 13-15 = mild

**ICP Management — Brain Trauma Foundation Tier System:**

Tier 0 (all patients): head elevation 30 degrees, neutral neck position, avoid hypotension (SBP >100), avoid hypoxia (SpO2 >95%), normothermia, treat seizures, adequate analgesia/sedation, ICP monitor for GCS ≤8 after resuscitation

Tier 1: CSF drainage via EVD; osmotherapy (mannitol 0.5-1 g/kg IV q6h — serum osm target <320; or hypertonic saline 23.4% 30 mL via central line or 3% NaCl infusion — target Na 145-155); head position optimization; avoid hypercapnia (PaCO2 35-40 mmHg)

Tier 2: Sedation deepening (propofol); neuromuscular blockade; mild hyperventilation (PaCO2 30-35 — bridge only, causes vasoconstriction and reduces CBF)

Tier 3: Decompressive craniectomy (DECRA trial — reduces ICP but worse functional outcomes); barbiturate coma (thiopental/pentobarbital — suppresses metabolic demand; burst-suppression on EEG; complications: hypotension, immunosuppression, prolonged sedation); temperature management (35-36°C)

**CPP = MAP - ICP; target CPP ≥60 mmHg (BTF Level IIA recommendation)**

### Status Epilepticus

**Definition:** continuous seizure ≥5 minutes or 2+ seizures without recovery to baseline

**Treatment algorithm:**

| Phase | Time | Treatment |
|-------|------|-----------|
| Benzodiazepine phase | 0-5 min | Lorazepam 0.1 mg/kg IV (max 4 mg) — repeat x1 if no response in 5 min; if no IV access: midazolam 10 mg IM or diazepam 20 mg PR |
| Second-line | 5-20 min | Fosphenytoin 20 mg PE/kg IV (max 150 mg PE/min); or levetiracetam 60 mg/kg IV (max 4500 mg); or valproate 40 mg/kg IV |
| Refractory | 20-40 min | Repeat second-line agent if not already used; anesthesia: propofol, midazolam infusion, phenobarbital 15-20 mg/kg |
| Super-refractory | >24h | Ketamine infusion; ketogenic diet; immunotherapy (IV methylprednisolone, IVIG, plasma exchange) for autoimmune; consider surgical/interventional options |

**EEG monitoring:** cEEG (continuous) for any patient with altered mental status after seizure, paralyzed patients, or post-anoxic brain injury — identifies non-convulsive SE (NCSE)

### Subarachnoid Hemorrhage (SAH)

**Grading (Hunt-Hess):**
- Grade I: asymptomatic or mild headache, slight nuchal rigidity
- Grade II: moderate-severe headache, nuchal rigidity, no neurologic deficit except CN palsy
- Grade III: drowsy, minimal neurologic deficit
- Grade IV: stuporous, moderate-severe hemiparesis
- Grade V: deep coma, decerebrate posturing, moribund

**ICU management:**
- Secure aneurysm: endovascular coiling or surgical clipping within 24-72h (early coiling reduces rebleed risk)
- Nimodipine: 60 mg PO/NG q4h x21 days — reduces cerebral vasospasm and delayed ischemic neurologic deficit (DIND); does NOT reduce vasospasm on imaging but reduces DCI and improves outcomes
- Vasospasm monitoring: TCD (transcranial Doppler) daily; CTA/CTP if TCD abnormal; clinical deterioration day 4-14
- Treatment of vasospasm: induced hypertension (norepinephrine to SBP 160-200); euvolemia; possible endovascular angioplasty/intra-arterial nicardipine
- Maintain euvolemia (not hypervolemic hemodilution — not evidence-based)
- Fever control: aggressively treat fever (worsens outcomes)
- Anticonvulsants: levetiracetam short-term (7 days) if seizure; routine prophylaxis controversial
- VTE prophylaxis: delay mechanical prophylaxis until aneurysm secured; sequential compression devices immediately

### Posterior Reversible Encephalopathy Syndrome (PRES)
- Clinical: headache, seizure, visual disturbance, encephalopathy + MRI findings of posterior leukoencephalopathy (vasogenic edema, T2/FLAIR hyperintensity predominately posterior)
- Causes: hypertensive emergency, eclampsia, immunosuppressants (cyclosporine, tacrolimus), chemotherapy (bevacizumab, cisplatin), sepsis
- Treatment: control underlying cause — aggressive BP lowering in hypertensive PRES; stop/reduce offending medication; antiepileptics for seizure; usually reversible with appropriate treatment

---

## ICU Nutrition

### Nutritional Assessment

| Tool | Components | Use |
|------|-----------|-----|
| NRS-2002 | BMI, weight loss, intake, acute illness | Hospitalized patients |
| NUTRIC Score | Age, APACHE II, SOFA, comorbidities, IL-6 | ICU-specific; predicts benefit from aggressive nutrition |

**Indirect calorimetry:** gold standard for energy expenditure measurement in ICU; oxygen consumption (VO2) and CO2 production (VCO2); RQ (VCO2/VO2): <0.7 fat oxidation, 0.85 mixed, 1.0 pure carbohydrate, >1.0 lipogenesis/overfeeding

### Enteral Nutrition

**Benefits:** maintains gut barrier integrity, reduces bacterial translocation, preserves mucosal immunity, prevents gut atrophy, reduces infections vs PN, cost-effective

**Timing:** within 24-48h of ICU admission in patients unable to maintain oral intake (ASPEN/SCCM guidelines — strong recommendation for early EN)

**Contraindications to EN:** hemodynamic instability requiring escalating vasopressors, active GI bleeding, mechanical intestinal obstruction, high-output enteric fistula, bowel ischemia

**Routes:**
- Nasogastric (NG): standard; bedside insertion; verify placement with CXR before use (NEVER start EN without radiographic confirmation)
- Orogastric (OG): intubated patients; avoids nasal pressure injury
- Post-pyloric (NJ, nasojejunal): high aspiration risk, recurrent high GRVs, prone positioning, delayed gastric emptying; requires fluoroscopy or endoscopy for placement (or bedside techniques with electromagnetic guidance)

**Tube feed formulations:**

| Type | Protein (g/1000 kcal) | Notes |
|------|----------------------|-------|
| Standard polymeric | 40-55 g | Most patients |
| High-protein | 60-90 g | ICU patients, trauma, burns |
| Semi-elemental/elemental | Variable | Severe malabsorption, short bowel, pancreatitis (jejunal) |
| Renal formula | 20-30 g, restricted K/P | Non-RRT AKI (controversial) |
| Diabetic formula | 40-50 g, low carb | Hyperglycemia management |
| Immune-modulating | + omega-3, arginine, glutamine | Mixed evidence; omega-3 may benefit ARDS |

**Gastric Residual Volume (GRV):**
- Check q4-6h if high aspiration risk
- Hold EN for GRV >500 mL (ASPEN 2016; lower threshold 250 mL still used in many ICUs)
- Promotility agents if GRV elevated: metoclopramide 10 mg IV q6h (dopamine antagonist; tardive dyskinesia with prolonged use); erythromycin 250 mg IV q6h or 3 mg/kg IV (motilin agonist; tolerance within 3 days)

### Parenteral Nutrition

**Indications:** EN contraindicated or not tolerated after >7 days; early PN in severely malnourished patients (BMI <18.5 or significant involuntary weight loss); GI failure

**Types:**
- Total Parenteral Nutrition (TPN): complete nutrition via central vein (high osmolarity); CIVAS compounded; 3-in-1 (dextrose + amino acids + lipid) or 2-in-1 (dextrose + amino acids; lipid separate)
- Peripheral Parenteral Nutrition (PPN): diluted formulation; max osmolarity ~900 mOsm; limited caloric density; short-term bridge

**Complications:**
- Hyperglycemia (most common): target BG 140-180 mg/dL; insulin algorithm/protocol required
- Refeeding syndrome: see below
- Hepatic dysfunction: fatty liver, cholestasis with prolonged PN; cycle PN (off 8-12h/day); reduce lipid dose; consider PO/EN transition; ursodeoxycholic acid for cholestasis
- Line infection: strict aseptic technique for all PN connections; dedicated PN lumen
- Venous thrombosis: heparin in PN bag (controversial)

### Refeeding Syndrome

**Pathophysiology:** severely malnourished patient reintroduced to carbohydrate-rich nutrition → insulin surge → cellular uptake of phosphate, potassium, magnesium; severe drops in all three within 24-72h of feeding

**Clinical consequences:**
- Hypophosphatemia: respiratory failure (impaired diaphragm contractility), hemolytic anemia, neurologic dysfunction, rhabdomyolysis, cardiac arrhythmia
- Hypokalemia: arrhythmias, paralytic ileus, weakness
- Hypomagnesemia: arrhythmias, seizures, neuromuscular irritability
- Thiamine deficiency (Wernicke's encephalopathy if thiamine not replaced before glucose)

**Prevention:**
- Identify high-risk patients (BMI <16, >10% weight loss in <2 months, minimal intake >10 days, low K/Mg/P before feeding)
- Replete electrolytes to normal before initiating feeds
- Administer thiamine 100-200 mg IV before any glucose
- Start nutrition slowly: 10-20 kcal/kg/day first week; advance over 4-7 days
- Monitor K, Mg, P q12-24h for first week; replete aggressively

---

## Glycemic Management in the ICU

### Hyperglycemia
- Stress hyperglycemia: catecholamine + cortisol + glucagon-mediated; insulin resistance; hepatic glycogenolysis
- Complications of hyperglycemia: impaired neutrophil function, increased infection, worsened neurologic injury, osmotic effects, impaired wound healing
- Target: 140-180 mg/dL for most ICU patients (NICE-SUGAR trial — intensive control 80-110 increased mortality vs conventional 140-180; hypoglycemia harm outweighs tight control benefit in critically ill)
- Insulin infusion protocol: regular insulin IV infusion; hourly glucose checks until stable; adjust per algorithm; Q2-4h once at goal

### Hypoglycemia in the ICU
- Definition: glucose <70 mg/dL (clinically significant); <40 mg/dL (severe)
- Risk factors: intensive insulin protocols, renal failure (decreased gluconeogenesis), liver failure, sepsis, abrupt cessation of dextrose/TPN, sulfonylureas
- Treatment: 50% dextrose 25-50 mL IV (12.5-25g); recheck glucose in 15 min; address underlying cause; 10% dextrose infusion for recurrent hypoglycemia; glucagon 1 mg IM/SC if no IV access

---

## Post-Intensive Care Syndrome (PICS)

### Definition and Domains
PICS encompasses new or worsening impairments in the following domains after critical illness, persisting after ICU discharge:

| Domain | Manifestations |
|--------|---------------|
| Cognitive | Memory impairment, attention deficits, reduced processing speed, executive dysfunction |
| Psychiatric | PTSD (25-40%), depression (30%), anxiety (30%) |
| Physical | ICU-acquired weakness, fatigue, reduced exercise capacity, pain syndromes, dysphagia |

### ICU-Acquired Weakness (ICUAW)
- Prevalence: >50% in patients mechanically ventilated >7 days
- Subtypes: critical illness polyneuropathy (CIP — axonal degeneration, EMG/NCS abnormal), critical illness myopathy (CIM — muscle wasting, myosin loss, CK elevated), combined (most common)
- Diagnosis: MRC sum score <48/60 (6 muscle groups bilateral; 0-5 scale each; total 60); requires cooperative patient
- Risk factors: prolonged MV, hyperglycemia, corticosteroids, aminoglycosides, NMB, immobility, SIRS/sepsis, organ failure
- Prevention: early mobilization (ABCDE bundle), glucose control, minimize NMB and corticosteroids, nutrition optimization
- Prognosis: recovery over months to years; significant residual weakness common; correlates with long-term mortality and quality of life

### PICS-F (Family)
- Caregiver burden, depression, anxiety, grief, PTSD in family members/caregivers
- Prevention: family communication (daily meetings), family presence/engagement, structured family support programs, ICU diaries

### Post-ICU Follow-Up
- ICU survivor clinics: multidisciplinary (physician, nurse, physio, occupational therapist, psychologist, pharmacist)
- Cognitive rehabilitation: neuropsychological testing, cognitive exercises
- Psychiatric screening: PHQ-9 (depression), GAD-7 (anxiety), PCL-5 (PTSD) at 3, 6, 12 months
- Functional rehabilitation: PT/OT in hospital and post-discharge; pulmonary rehabilitation for prolonged MV
- Medication reconciliation: many ICU medications continued unnecessarily at discharge (PPI stress ulcer prophylaxis in patients eating; antipsychotics; antifungals)

---

## Palliative Care in the ICU

### Communication
- Goals of care conversations: prognosis, values, treatment preferences; family meeting within 72h of ICU admission for high-risk patients
- Prognostic framing: avoid "percentage chance of survival" — frame as realistic description of likely outcomes
- REMAP framework: Reframe the situation, Expect emotion and empathize, Map out what's important to the patient, Align with values, Propose care that matches values
- Surrogate decision-makers: legal hierarchy varies by state; documented advance directives take precedence; POLST/MOLST for out-of-hospital documentation

### Withdrawal of Life-Sustaining Treatment
- Validated decision when consistent with patient values and goals; not morally different from withholding treatment
- Process: ensure family present if desired; adequate sedation/analgesia before and after extubation; titrate medication to comfort not to hasten death (double effect doctrine)
- Medications: morphine infusion (respiratory comfort) + midazolam or lorazepam (dyspnea, anxiety); scopalamine patch or glycopyrrolate for secretions
- Ventilator withdrawal: terminal extubation vs terminal wean; most ICUs prefer terminal extubation (immediate extubation with adequate pre-medication) as it is more consistent with patient comfort

### Dying in the ICU — Symptom Management

| Symptom | First-Line Treatment | Notes |
|---------|---------------------|-------|
| Dyspnea | Morphine 2-4 mg IV q1-2h; infusion | Also reduces respiratory rate and sense of air hunger |
| Pain | Opioid titration | Same agents as above; dose to effect |
| Anxiety/agitation | Lorazepam 0.5-2 mg IV; midazolam infusion | Benzodiazepines appropriate at end of life |
| Death rattle | Glycopyrrolate 0.2 mg IV q4h; scopolamine patch | Distressing to family; not painful to patient |
| Refractory symptoms | Palliative sedation (midazolam or propofol infusion) | Last resort; requires ethics consultation |

---

## Special ICU Topics

### Abdominal Compartment Syndrome (ACS)

**Intraabdominal Pressure (IAP) Measurement:**
- Patient supine; zero transducer at mid-axillary line at iliac crest
- Instill 25-30 mL sterile saline via Foley catheter; measure at end-expiration
- Normal IAP: <12 mmHg
- Intraabdominal Hypertension (IAH) grades: I (12-15), II (16-20), III (21-25), IV (>25 mmHg)
- ACS: IAP >20 mmHg + new or progressive organ dysfunction/failure

**Organ Effects of IAH/ACS:**

| Organ System | Effect |
|-------------|--------|
| Renal | Decreased renal perfusion pressure (APP = MAP - IAP); oliguric AKI; CrCl drops at IAP >15-20 |
| Respiratory | Diaphragm elevation → atelectasis; increased Pplat; decreased compliance; hypoxia/hypercapnia |
| Cardiovascular | Decreased venous return (IVC compression); reduced CO; false elevation of CVP and PCWP |
| CNS | Elevated ICP via impaired venous drainage (jugular/epidural venous plexus) |
| Splanchnic | Bowel ischemia, ileus, gut barrier failure, translocation |

**APP = MAP - IAP; target APP ≥60 mmHg**

**Management:**
- Non-surgical: nasogastric/rectal decompression; percutaneous drainage of ascites/hematoma; optimization of body position (reverse Trendelenburg); judicious diuresis; CRRT for fluid removal; avoid Trendelenburg and HOB >30 degrees (elevates IAP); acetaminophen and neostigmine for ileus
- Surgical: decompressive laparotomy; temporary abdominal closure (vacuum-assisted wound therapy — VAC); re-exploration and closure when swelling resolved (usually 48-72h)

### Burns in the ICU

**Burn Depth:**

| Depth | Appearance | Sensation | Healing |
|-------|-----------|-----------|--------|
| Superficial (1st degree) | Erythema, no blistering | Painful | 3-5 days, no scar |
| Superficial partial (2nd degree) | Blisters, moist, pink/red | Very painful | 1-3 weeks, minimal scar |
| Deep partial (2nd degree) | Pale, dry, less painful | Decreased sensation | 3-8 weeks, significant scar |
| Full thickness (3rd degree) | White/brown/black, leathery | Painless | No healing without grafting |
| 4th degree | Involves muscle/bone | None | Amputation often required |

**TBSA (Total Body Surface Area):**
- Rule of Nines: head 9%, each arm 9%, chest 18%, abdomen 18%, each leg 18%, perineum 1%
- Palmar method: patient's palm + fingers = approximately 1% TBSA
- Lund-Browder chart: most accurate (adjusts for pediatric proportions)

**Parkland Formula:**
- 4 mL/kg/% TBSA burned in first 24h (lactated Ringer's)
- 50% in first 8 hours from time of burn (not time of arrival); 50% in next 16 hours
- Titrate UO to 0.5-1 mL/kg/hr
- Avoid colloid in first 24h (controversy about albumin timing)

**Inhalation Injury:**
- Suspect: facial burns, singed nasal hairs, soot in mouth/nares, hoarseness, stridor, carbonaceous sputum, history of enclosed space fire
- Upper airway: edema → airway obstruction within hours; intubate EARLY before edema develops
- Lower airway: chemical tracheobronchitis; bronchospasm; bronchorrhea; impaired mucociliary clearance; pneumonia
- CO poisoning: pulse ox unreliable (measures oxy + carboxyhemoglobin as oxyhemoglobin); treat with 100% FiO2 (reduces CO half-life from 5h to 90 min); HBO therapy for severe poisoning
- Cyanide poisoning (fire/smoke): lactic acidosis + cardiovascular collapse; hydroxocobalamin 5g IV (Cyanokit) empirically in severe cases

### Acute Liver Failure (ALF)

**Definition:** acute hepatic injury + hepatic encephalopathy + INR ≥1.5 in patient without pre-existing liver disease

**Etiology:**
- USA: acetaminophen overdose (most common — 46%), drug-induced (non-APAP), viral hepatitis A/B, Wilson's disease, autoimmune hepatitis, ischemic hepatitis ("shock liver"), pregnancy-related (AFLP, HELLP), indeterminate

**King's College Criteria (prognosis/transplant listing):**
- Acetaminophen: pH <7.3 (after resuscitation) OR (PT >100s or INR >6.5) + creatinine >3.4 + Grade III-IV encephalopathy
- Non-acetaminophen: PT >100s (INR >6.5) OR 3 of: unfavorable etiology (non-A non-B hepatitis, drug-induced), age <10 or >40, jaundice >7d before encephalopathy, bilirubin >17.6, PT >50s

**ICU management of ALF:**
- Hepatic encephalopathy: lactulose 20-30 mL q2-4h (titrate to 2-3 BM/day); rifaximin 550 mg BID; protein restriction no longer recommended; ICP monitoring for Grade III-IV encephalopathy with renal failure; mannitol for elevated ICP; hypertonic saline (target Na 145-155) for refractory ICP
- Coagulopathy: do NOT correct INR prophylactically (INR is best prognostic marker); FFP only for active bleeding or invasive procedures; PCC for life-threatening bleeding
- Hypoglycemia: 10% dextrose continuous infusion; q1-4h glucose monitoring
- Renal failure: CRRT preferred (hemodynamic instability, ICP management); avoid nephrotoxins; stop acetaminophen in all patients with ALF
- Infection: prophylactic antibiotics and antifungals in centers awaiting transplant (infection excluded from KCC criteria)
- Liver transplantation: contact transplant center early; emergent listing for poor-prognosis criteria

### Pregnancy-Related ICU Admissions

**Key physiologic changes in pregnancy:**

| Parameter | Change | Clinical Implication |
|-----------|--------|---------------------|
| Blood volume | +40-50% | Dilutional anemia; greater hemorrhage tolerance before shock |
| Cardiac output | +30-40% | Higher baseline CO; SVR falls |
| FRC | -20-30% | Rapid desaturation on apnea; pre-oxygenate aggressively |
| RR | Increased | Respiratory alkalosis (PaCO2 28-32) normal; bicarbonate 18-21 normal |
| GFR | +50% | Lower normal creatinine (0.5-0.8); higher clearance affects drug dosing |
| Coagulation | Hypercoagulable | DVT/PE risk 5-10x higher |

**Common obstetric ICU admissions:**
- Preeclampsia/eclampsia: HTN >140/90 + proteinuria or end-organ damage; magnesium sulfate 4-6 g IV load then 1-2 g/hr for eclampsia prevention; definitive treatment = delivery
- HELLP syndrome: hemolysis (elevated LDH), elevated liver enzymes, low platelets; can occur antepartum or postpartum; treatment = delivery; corticosteroids for maturity if <34 weeks
- Amniotic fluid embolism (AFE): catastrophic — amniotic fluid into maternal circulation; cardiovascular collapse, DIC, seizures; resuscitation, treat DIC, delivery
- Peripartum cardiomyopathy: new HF in last month of pregnancy to 5 months postpartum; LVEF <45%; treat as standard HF (avoid ACEI in pregnancy); bromocriptine if breastfeeding; prognosis variable

**Drug safety in pregnancy (brief guidance):**
- Safe/relatively safe: penicillins, cephalosporins, azithromycin, metronidazole, acetaminophen, heparin, LMWH, hydrocortisone, labetalol, hydralazine, nifedipine, insulin
- Avoid: tetracyclines (teeth/bone), fluoroquinolones (cartilage), aminoglycosides (ototoxicity), ACE inhibitors/ARBs (renal dysgenesis), warfarin (embryopathy), NSAIDs (ductus arteriosus), valproate (neural tube defect)

---

## Toxicology in the ICU

### General Approach to Poisoning

1. Stabilize ABCs — intubate for GCS ≤8 or inability to protect airway
2. Decontamination: activated charcoal 1 g/kg (within 1-2h, if alert and able to protect airway, no hydrocarbon/caustic ingestion); whole bowel irrigation (polyethylene glycol) for iron, lithium, sustained-release formulations, body packing
3. Antidote (if available): see table below
4. Enhanced elimination: urinary alkalinization (salicylates, phenobarbital); hemodialysis (methanol, ethylene glycol, lithium, salicylates, theophylline); hemoperfusion
5. Supportive care: glucose, temperature, seizure control, cardiac monitoring

### Common ICU Toxidromes

| Toxidrome | Agent | Features | Treatment |
|-----------|-------|---------|-----------|
| Opioid | Heroin, morphine, fentanyl | Miosis, respiratory depression, decreased LOC, bradycardia | Naloxone 0.4-2 mg IV/IM/IN; repeat q2-3 min; infusion for long-acting opioids |
| Sympathomimetic | Cocaine, amphetamines | Tachycardia, hypertension, hyperthermia, agitation, diaphoresis, mydriasis | Benzodiazepines (first-line for agitation/seizure); cooling; avoid beta-blockers (unopposed alpha) |
| Cholinergic | Organophosphates, carbamate | Miosis, bradycardia, bronchospasm, secretions (SLUDGE: salivation, lacrimation, urination, defecation, GI distress, emesis) | Atropine 2-4 mg IV (titrate to dry secretions, not HR); pralidoxime (2-PAM) 1-2 g IV for OP poisoning |
| Anticholinergic | Diphenhydramine, TCAs, scopolamine | Tachycardia, hyperthermia, dry skin/mucous membranes, urinary retention, delirium, mydriasis | Supportive; physostigmine 0.5-2 mg slow IV for pure anticholinergic delirium |
| Serotonin syndrome | SSRIs + MAOI, triptans, linezolid | Hyperthermia, clonus, hyperreflexia, agitation, tremor, diaphoresis | Cyproheptadine 4-8 mg PO q6h; benzodiazepines; cooling; severe cases: NMB + intubation for hyperthermia |
| Neuroleptic malignant syndrome | Antipsychotics | Hyperthermia, rigidity, altered MS, autonomic instability, elevated CK | Dantrolene 2.5 mg/kg IV; bromocriptine 2.5 mg TID PO; cooling; benzodiazepines |

### Acetaminophen Overdose

- Toxic dose: >150 mg/kg or >7.5g single ingestion; risk increases with chronic alcohol use, malnutrition, P450 inducers
- Stages: Stage I (0-24h) — nausea/vomiting; Stage II (24-72h) — transaminase elevation, RUQ pain; Stage III (72-96h) — hepatic failure peak (INR, encephalopathy, AKI); Stage IV — recovery or death
- Diagnosis: serum APAP level at 4h post-ingestion; plot on Rumack-Matthew nomogram; if level above treatment line → treat
- Antidote: N-acetylcysteine (NAC) — IV protocol (150 mg/kg over 1h loading, then 12.5 mg/kg/hr x4h, then 6.25 mg/kg/hr x16h); PO protocol 70 mg/kg loading, 35 mg/kg q4h x17 doses; extends treatment until clinical/lab resolution in established hepatotoxicity
- Liver transplant evaluation: King's College Criteria (see above)

---

## Quality Metrics and ICU Outcomes

### Common ICU Quality Measures

| Metric | Target | Notes |
|--------|--------|-------|
| VAP rate | <1/1000 ventilator-days | VAP bundle compliance |
| CLABSI rate | <1/1000 catheter-days | CVC bundle compliance |
| CAUTI rate | <1/1000 catheter-days | Foley necessity review |
| HOB elevation | ≥30 degrees | >95% compliance |
| Daily SAT + SBT | >90% of eligible patients | ABCDE bundle |
| Delirium screening | Twice daily CAM-ICU | All ventilated and non-ventilated ICU patients |
| Early mobility | PT/OT consult within 72h | Documentation of mobility level |
| Glucose in target | 140-180 mg/dL | Hyperglycemia protocol compliance |
| VTE prophylaxis | >95% of eligible patients | UFH, LMWH, or SCD documentation |

### APACHE II Score
- Predicts in-hospital mortality from physiologic derangements in first 24h
- Components: 12 physiologic variables (temperature, MAP, HR, RR, FiO2, pH, Na, K, Cr, Hct, WBC, GCS), age points, chronic health points
- Score 0-71; higher score = higher predicted mortality
- Used for research stratification; not for individual prognosis

### SOFA Score (Sequential Organ Failure Assessment)

| Organ System | Score 0 | Score 1 | Score 2 | Score 3 | Score 4 |
|-------------|---------|---------|---------|---------|---------|
| Respiration (PaO2/FiO2) | ≥400 | 300-399 | 200-299 | 100-199 + vent | <100 + vent |
| Coagulation (Platelets k/uL) | ≥150 | 100-149 | 50-99 | 20-49 | <20 |
| Liver (Bilirubin mg/dL) | <1.2 | 1.2-1.9 | 2.0-5.9 | 6.0-11.9 | ≥12.0 |
| Cardiovascular | No vasopressors | MAP <70 | Dopamine ≤5 or Dob | Dop >5, Epi ≤0.1, NE ≤0.1 | Dop >15, Epi >0.1, NE >0.1 |
| CNS (GCS) | 15 | 13-14 | 10-12 | 6-9 | <6 |
| Renal (Creatinine mg/dL) | <1.2 | 1.2-1.9 | 2.0-3.4 | 3.5-4.9 or UO <500 mL/d | ≥5.0 or UO <200 mL/d |

Delta SOFA (change from admission) >2 = organ dysfunction in Sepsis-3 definition.

---

## Key Clinical Trials Summary

| Trial | Year | Question | Result |
|-------|------|---------|--------|
| ARDSNET | 2000 | 6 vs 12 mL/kg IBW in ARDS | 6 mL/kg reduced 28-day mortality (31% vs 40%) |
| PROSEVA | 2013 | Prone positioning in ARDS (PF <150) | Prone reduced 28-day mortality (16% vs 32.8%) |
| ACURASYS | 2010 | Cisatracurium 48h in ARDS | Reduced 90-day mortality vs placebo |
| ROSE | 2019 | Cisatracurium vs light sedation | No mortality benefit vs light sedation comparator |
| EOLIA | 2018 | VV-ECMO in severe ARDS | Trend to benefit (35% vs 46%, p=0.07); significant crossover |
| CATS | 2010 | Dopamine vs norepinephrine in shock | NE lower mortality; fewer arrhythmias |
| VASST | 2008 | Vasopressin + NE vs NE alone | No mortality difference; vasopressin-sparing effect |
| SEPSISPAM | 2014 | MAP 65 vs 85 in septic shock | No overall outcome difference; less RRT in hypertensives at MAP 85 |
| FACTT | 2006 | Liberal vs conservative fluids in ARDS | Conservative: shorter MV and ICU stay; no mortality difference |
| NICE-SUGAR | 2009 | Intensive (80-110) vs conventional (140-180) glucose | Intensive control increased 90-day mortality |
| PROPPR | 2015 | 1:1:1 vs 2:1:2 blood product ratio | 1:1:1 improved 24h and 30-day survival |
| CRASH-2 | 2010 | TXA in trauma hemorrhage | TXA within 3h reduced mortality; beyond 3h increased mortality |
| TRICC | 1999 | Restrictive (Hgb 7) vs liberal (Hgb 10) transfusion | Restrictive noninferior; lower mortality in less-ill patients |
| RENAL | 2009 | High (40) vs low (25) mL/kg/hr CRRT dose | No difference; 25 mL/kg/hr (delivered) sufficient |
| TracMan | 2013 | Early vs late tracheostomy | No mortality difference; no benefit to early tracheostomy |
| IABP-SHOCK II | 2012 | IABP in AMI cardiogenic shock | No mortality benefit |
| DECRA | 2011 | Decompressive craniectomy for TBI | Reduced ICP but worse functional outcomes |

---

## Drug Reference — Common ICU Medications

### Vasoactive Agents Quick Reference

| Drug | Route | Starting Dose | Max Dose | Primary Use |
|------|-------|-------------|----------|------------|
| Norepinephrine | Central IV | 0.05 mcg/kg/min | 3 mcg/kg/min | Septic shock |
| Vasopressin | Central IV | 0.03 units/min | 0.04 units/min | Adjunct septic shock |
| Epinephrine | Central IV | 0.01 mcg/kg/min | 0.5 mcg/kg/min | Cardiogenic/anaphylaxis |
| Phenylephrine | Central or peripheral IV | 50 mcg/min | 200 mcg/min | Pure vasopressor |
| Dopamine | Central IV | 2 mcg/kg/min | 20 mcg/kg/min | Low-moderate dose inotrope |
| Dobutamine | Central IV | 2 mcg/kg/min | 20 mcg/kg/min | Cardiogenic shock inotrope |
| Milrinone | Central IV | 0.125 mcg/kg/min | 0.75 mcg/kg/min | RV failure, cardiogenic shock |

### Sedation/Analgesia Quick Reference

| Drug | Dose | Onset | Offset | Primary Use |
|------|------|-------|--------|------------|
| Propofol | 5-50 mcg/kg/min | 30-60s | 5-15 min | Sedation (short/medium term) |
| Dexmedetomidine | 0.2-1.5 mcg/kg/hr | 5-10 min | 15-30 min | Light sedation, delirium |
| Midazolam | 0.02-0.1 mg/kg/hr | 2-5 min | Variable | ETOH withdrawal, seizures |
| Ketamine | 0.1-0.5 mg/kg/hr | 1-2 min | 10-15 min | Analgosedation, bronchospasm |
| Fentanyl | 25-200 mcg/hr | 1-3 min | 30-60 min | Analgesia (renal failure safe) |
| Hydromorphone | 0.2-0.5 mg IV q2h | 5-10 min | 3-4h | Analgesia |

### Anticoagulation in ICU

| Indication | Agent | Target | Notes |
|-----------|-------|--------|-------|
| DVT/PE treatment | Heparin infusion | aPTT 60-100 sec or anti-Xa 0.3-0.7 | Start with weight-based nomogram |
| DVT prophylaxis (medical) | Enoxaparin 40 mg SQ q24h | Anti-Xa 0.1-0.3 (level optional) | Reduce to 30 mg q24h if CrCl <30 |
| HIT (heparin-induced thrombocytopenia) | Argatroban or bivalirudin | aPTT 1.5-3x baseline | STOP ALL heparin products; check PF4 antibody |
| CRRT anticoagulation | Regional citrate or heparin | See CRRT section | Citrate preferred if systemic AC contraindicated |
| AF in ICU | IV heparin or DOAC (if stable) | aPTT per protocol | CHADS2-VASc risk stratification for long-term |

---

## Infection Prophylaxis in the ICU

### Stress Ulcer Prophylaxis (SUP)
- Indications for PPI or H2 blocker: mechanical ventilation ≥48h, coagulopathy (INR >1.5, PTT >2x, platelets <50k), shock, prior GI ulcer/bleeding
- Agent: pantoprazole 40 mg IV/PO or famotidine 20 mg IV/PO
- REVISE trial (2023): pantoprazole reduced GI bleeding vs placebo but increased VAP rate and 90-day mortality (stopped early); risk-benefit reassessment ongoing — use only in high-risk patients
- Discontinue when patient tolerating oral intake

### DVT Prophylaxis
- Pharmacological: LMWH preferred over UFH (more predictable, once daily); UFH 5000 units SQ BID or TID acceptable
- Timing: within 24-48h of ICU admission; hold for 24h after neuraxial procedure, 12h for peripheral nerve block
- Mechanical: sequential compression devices (SCDs) on lower extremities — use when pharmacological prophylaxis contraindicated; not as effective as pharmacological alone
- Contraindications to pharmacological: active bleeding, severe thrombocytopenia (platelets <50k), recent CNS/spinal surgery, severe coagulopathy — use SCDs

### Antifungal Prophylaxis
- High-risk groups: prolonged ICU stay (>7 days) with multiple risk factors (TPN, broad-spectrum antibiotics, immunosuppression, abdominal surgery, hemodialysis, Candida colonization)
- Fluconazole prophylaxis: reduces Candida infections in surgical ICU; not routinely recommended in medical ICU (risk of azole resistance development)
- Empiric antifungal therapy: start if invasive Candida suspected (fever not responding to antibiotics + risk factors); echinocandin (micafungin, caspofungin) preferred for critically ill; fluconazole acceptable if low azole-resistance risk

---

*This knowledge base is intended for educational and clinical decision support purposes. Clinical judgment, institutional protocols, and current evidence-based guidelines should govern individual patient care decisions. Medical knowledge evolves rapidly — refer to UpToDate, current SCCM/ESICM guidelines, and primary literature for the most recent recommendations.*
