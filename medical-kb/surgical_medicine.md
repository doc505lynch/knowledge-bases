# Surgical Medicine Knowledge Base

**Domain:** Surgical Medicine — Perioperative Care, General Surgery, Vascular Surgery, Orthopedics, Critical Care Surgery
**Purpose:** Reference knowledge base for clinical decision support. Structured for RAG retrieval (chunk size 1500, overlap 200).
**Last Updated:** 2026-04-10
**Scope:** Preoperative assessment through postoperative complications, including subspecialty surgical topics.

---

## Preoperative Assessment

Preoperative assessment serves to identify modifiable risk factors, optimize the patient's physiologic state before surgery, and inform perioperative management decisions. Every surgical patient requires a structured evaluation regardless of procedure type or urgency.

### ASA Physical Status Classification

The American Society of Anesthesiologists (ASA) Physical Status Classification is the most widely used system for grading preoperative patient health. It correlates with perioperative morbidity and mortality. Classification is assigned by the anesthesiologist prior to any anesthetic procedure.

| ASA Class | Definition | Examples |
|-----------|------------|---------|
| ASA I | Normal, healthy patient | No organic, physiologic, or psychiatric disturbance; non-smoker; no or minimal alcohol use; BMI <30 |
| ASA II | Mild systemic disease | Well-controlled diabetes mellitus, hypertension, or hypothyroidism; mild obesity (BMI 30-40); current smoker; social alcohol use; pregnancy; remote MI (>3 months) |
| ASA III | Severe systemic disease, not immediately life-threatening | Poorly controlled DM or HTN; COPD; morbid obesity (BMI >40); active hepatitis; alcohol dependence; pacemaker; moderate reduction in ejection fraction; ESRD on dialysis; history of MI/CVA/TIA within 3 months; premature infant (PCA <60 weeks) |
| ASA IV | Severe systemic disease that is a constant threat to life | Recent MI or CVA (<3 months); severe cardiac valvular disease with hemodynamic compromise; sepsis; DIC; ARD or ESRD not regularly dialyzed |
| ASA V | Moribund patient, not expected to survive without operation | Ruptured abdominal aortic aneurysm; massive trauma; intracranial bleed with elevated ICP; bowel ischemia in the setting of significant cardiac pathology; multi-organ failure |
| ASA VI | Brain-dead patient declared, organs being removed for donation | Declared brain-dead donor; all organ procurement procedures |

- The suffix "E" is added for emergency procedures (e.g., ASA IIE, ASA IIIE).
- Emergency surgery approximately doubles the operative risk compared to elective surgery at the same ASA class.
- ASA I and II: mortality risk <0.1%. ASA III: ~1-2%. ASA IV: ~7-10%. ASA V: ~40% within 24 hours.

---

### Cardiac Risk Assessment

Cardiac complications — including myocardial infarction (MI), heart failure, arrhythmia, and cardiac death — represent the leading cause of perioperative mortality in non-cardiac surgery. Structured cardiac risk assessment is mandatory before any elective intermediate- or high-risk procedure.

#### Revised Cardiac Risk Index (RCRI)

The RCRI (Lee Index, 1999) is the most validated preoperative cardiac risk score. It predicts the risk of major adverse cardiac events (MACE) including MI, pulmonary edema, ventricular fibrillation, complete heart block, and cardiac death.

| Predictor | Point Value | Details |
|-----------|-------------|---------|
| High-risk surgery | 1 point | Intraperitoneal, intrathoracic, or suprainguinal vascular surgery |
| Ischemic heart disease | 1 point | History of MI, positive stress test, current chest pain from presumed ischemic cause, or use of nitrate therapy |
| Congestive heart failure | 1 point | History of CHF, pulmonary edema, or bilateral rales on exam |
| Cerebrovascular disease | 1 point | History of stroke or TIA |
| Diabetes mellitus requiring insulin | 1 point | Insulin-dependent diabetes (not just oral agents) |
| Preoperative serum creatinine >2.0 mg/dL | 1 point | Excludes patients on dialysis |

**RCRI Risk Stratification:**

| RCRI Score | Estimated MACE Risk | Clinical Action |
|------------|---------------------|-----------------|
| 0 | <1% (very low) | Proceed to surgery without further cardiac workup |
| 1 | ~1% (low) | Proceed to surgery; optimize risk factors |
| 2 | ~2.4% (moderate) | Consider further testing if it will change management |
| 3+ | >5.4% (high) | Cardiology consultation; consider non-invasive testing; weigh risks vs benefits |

#### Surgical Risk Categories (AHA/ACC Perioperative Guidelines)

The 2014 AHA/ACC Guideline on Perioperative Cardiovascular Evaluation stratifies surgical procedures by inherent risk of MACE.

**Low-Risk Procedures (<1% MACE risk):**
- Superficial surgeries (skin, soft tissue)
- Endoscopic procedures
- Cataract surgery
- Breast surgery
- Ambulatory surgery

**Intermediate-Risk Procedures (1-5% MACE risk):**
- Intraabdominal and intrathoracic surgery
- Orthopedic procedures (hip/knee arthroplasty)
- Prostate surgery
- Head and neck surgery
- Renal transplantation

**High-Risk Procedures (>5% MACE risk):**
- Aortic and major vascular surgery
- Peripheral vascular surgery
- Emergent major operations, particularly in the elderly

#### Functional Capacity and METs Assessment

Functional capacity is expressed in Metabolic Equivalent of Task (MET) units. One MET = resting oxygen consumption at rest (3.5 mL O2/kg/min). Assessment of functional capacity is a critical component of the stepwise cardiac evaluation algorithm.

| MET Level | Activity Examples |
|-----------|-------------------|
| 1-3 METs (poor) | Eating, dressing, walking on level ground at 2-3 mph, light housework |
| 4 METs (moderate — surgical threshold) | Climbing one flight of stairs, walking on level ground at 4 mph, heavy housework, golf |
| >4 METs (good) | Running, heavy manual labor, strenuous sports, cycling, swimming laps |
| >10 METs (excellent) | Competitive athletics, strenuous endurance exercise |

**The 4 MET Threshold:**
- Patients who can achieve 4 METs without symptoms are considered to have adequate functional capacity for most surgical procedures.
- Inability to achieve 4 METs (or unknown functional capacity) in patients with 2+ RCRI risk factors may warrant non-invasive cardiac testing before intermediate- or high-risk surgery.
- Non-invasive testing options: exercise treadmill test, dobutamine stress echocardiogram, pharmacologic nuclear stress test.
- Coronary revascularization before elective surgery is NOT routinely recommended solely to reduce perioperative cardiac risk. It is indicated only if the patient has indications independent of the planned surgery (e.g., unstable angina, LMCA disease, severe 3-vessel disease with poor LV function).

---

### Perioperative Beta-Blocker Management

**Continue beta-blockers** if the patient is already taking them. Abrupt discontinuation increases the risk of rebound hypertension, tachycardia, and MI.

**Initiate beta-blockers** in patients who:
- Have intermediate or high cardiac risk (RCRI 3+) AND are undergoing high-risk surgery
- Have known coronary artery disease undergoing high-risk surgery
- Are undergoing major vascular surgery with ischemia on preoperative testing

**Do NOT initiate** beta-blockers within 24 hours of surgery, in hypotensive patients, in bradycardic patients (HR <60), or in patients with decompensated heart failure.

Preferred agent: metoprolol succinate (beta-1 selective). Target HR 60-80 bpm.

---

### Anticoagulation Management

#### Perioperative Warfarin Management

**Hold Warfarin:**
- Stop warfarin 5 days before elective surgery (to allow INR to normalize to <1.5).
- Check INR 1-2 days before surgery; administer vitamin K 1-2.5 mg PO if INR still elevated.
- Restart warfarin 12-24 hours postoperatively once hemostasis is confirmed.

**When to Bridge (Heparin Bridging):**
Bridging anticoagulation with low molecular weight heparin (LMWH) or unfractionated heparin (UFH) is indicated when the thromboembolic risk without anticoagulation exceeds the bleeding risk.

| Condition | Bridging Recommendation |
|-----------|------------------------|
| Mechanical mitral valve (any type) | Bridge |
| Mechanical aortic valve (older generation — tilting disc, caged ball) | Bridge |
| Mechanical aortic valve (bileaflet) + any stroke risk factor | Bridge |
| AF with CHA2DS2-VASc score 5-6 | Bridge |
| VTE within past 3 months | Bridge |
| Severe thrombophilia (protein C/S deficiency, antiphospholipid syndrome, factor V Leiden homozygous) | Bridge |
| AF with CHA2DS2-VASc 0-2 | Do NOT bridge |
| Mechanical bileaflet aortic valve, no other risk factors | Do NOT bridge |
| Single VTE >12 months ago, no other risk factors | Do NOT bridge |

BRIDGE trial (2015): Bridging did NOT reduce arterial thromboembolism in AF patients but DID increase major bleeding. Routine bridging for AF is no longer recommended for most patients.

#### Direct Oral Anticoagulant (DOAC) Hold Times

DOACs do not require bridging. They are held before surgery based on renal function and procedure bleeding risk.

| DOAC | Mechanism | Minor Procedure Hold | Major Procedure Hold | Renal Adjustment |
|------|-----------|---------------------|---------------------|-----------------|
| Apixaban (Eliquis) | Factor Xa inhibitor | 24-48h | 48h (72h if CrCl 25-50) | Extend to 72h if CrCl <25 |
| Rivaroxaban (Xarelto) | Factor Xa inhibitor | 24h | 48h | Extend to 48-72h if CrCl <30 |
| Dabigatran (Pradaxa) | Direct thrombin inhibitor | 24-48h | 48h (96h if CrCl 30-50) | Extend to 96-120h if CrCl <30 |
| Edoxaban (Savaysa) | Factor Xa inhibitor | 24h | 48h | Minimal renal adjustment needed |

- Dabigatran is most dependent on renal clearance; use creatinine clearance (CrCl) to calculate hold time.
- High-bleeding-risk procedures (neurosurgery, cardiac surgery, major vascular) require the longest hold periods.
- Resume DOACs 24-72 hours postoperatively when hemostasis is confirmed.
- In life-threatening DOAC bleeding: idarucizumab (Praxbind) reverses dabigatran; andexanet alfa (Andexxa) reverses apixaban and rivaroxaban.

---

### Antiplatelet Management

#### Aspirin
- For patients NOT on aspirin for secondary prevention (i.e., no established ASCVD): hold aspirin 7-10 days before surgery for major procedures.
- For secondary prevention patients (known ASCVD, prior stent, prior MI/stroke): continue aspirin through most procedures due to ischemic risk.
- Exception: neurosurgery, spinal surgery, intraocular surgery, and tonsillectomy — hold aspirin even in secondary prevention patients unless cardiologist advises otherwise.
- POISE-2 trial (2014): initiating aspirin perioperatively increased major bleeding without reducing cardiac events.

#### P2Y12 Inhibitor Hold Times

| Drug | Hold Time Before Surgery | Reversal Agent |
|------|------------------------|----------------|
| Clopidogrel (Plavix) | 5 days | None (transfuse platelets if emergency) |
| Ticagrelor (Brilinta) | 3-5 days | None; half-life is 7-8.5h (active metabolite also inhibits) |
| Prasugrel (Effient) | 7 days | None |
| Cangrelor (Kengreal) | 1-3 hours (IV, rapidly reversible) | Stop infusion 1-3h before surgery |

**Dual Antiplatelet Therapy (DAPT) and Coronary Stents:**
- Bare metal stent (BMS): defer elective surgery minimum 30 days (ideally 6 weeks). If must operate sooner, continue DAPT through procedure if possible.
- Drug-eluting stent (DES — 1st generation): defer minimum 12 months.
- Drug-eluting stent (DES — 2nd and 3rd generation): defer minimum 6 months.
- Premature DAPT discontinuation in stent patients carries risk of in-stent thrombosis (1-2% mortality per event). Discuss with cardiologist before any elective surgery.

---

### Pulmonary Risk Assessment

Pulmonary complications (pneumonia, respiratory failure, atelectasis, prolonged mechanical ventilation) are as common as cardiac complications following major surgery and carry significant morbidity and mortality.

#### Key Pulmonary Risk Factors

**Patient-Related:**
- ASA class III or IV
- Age >60
- Obesity (BMI >30), especially with obstructive sleep apnea (OSA)
- CHF
- Functional dependence
- Chronic obstructive pulmonary disease (COPD)
- Current cigarette smoking
- Albumin <3.5 g/dL (nutritional compromise)
- Preoperative SpO2 <95% on room air
- Sensory or motor neurological deficits

**Procedure-Related:**
- Upper abdominal surgery (highest risk for pulmonary complications)
- Thoracic surgery
- Surgery duration >3 hours
- General anesthesia (higher risk than neuraxial or regional)
- Emergency surgery
- Head or neck surgery

#### Arozullah Multifactorial Index for Postoperative Respiratory Failure

The Arozullah Score predicts risk of postoperative respiratory failure (inability to wean from ventilator >48h, or reintubation).

| Risk Factor | Points |
|-------------|--------|
| Type of surgery: abdominal aortic aneurysm | 27 |
| Type of surgery: thoracic | 21 |
| Type of surgery: neurosurgery, upper abdominal, or peripheral vascular | 14 |
| Type of surgery: neck | 11 |
| Emergency surgery | 11 |
| Albumin <30 g/L (<3.0 g/dL) | 9 |
| BUN >30 mg/dL | 8 |
| COPD (FEV1 <70% predicted) | 6 |
| Functional dependence | 7 |
| Age 70-79 | 6 |
| Age 80+ | 6 |

Risk Class: Class 1 (<10 points, ~0.5% respiratory failure rate); Class 2 (11-19 points, ~2%); Class 3 (20-27 points, ~5%); Class 4 (28-40 points, ~11%); Class 5 (>40 points, ~27%).

#### Smoking Cessation

- Maximum benefit requires cessation 8 weeks or more before surgery.
- Benefits of cessation at 8+ weeks: reduced pulmonary complications, improved mucociliary clearance, reduction in carboxyhemoglobin, improved wound healing.
- Cessation less than 8 weeks before surgery: may transiently increase secretions (reactive hyperemia phase) but still reduces carboxyhemoglobin and improves oxygen delivery.
- Even 24-hour cessation improves carboxyhemoglobin levels and nicotine-induced vasoconstriction.
- Nicotine replacement therapy can be used perioperatively.

#### Incentive Spirometry and Pulmonary Conditioning

- Incentive spirometry: patient-controlled device producing sustained maximal inspiration (SMI) to promote alveolar inflation.
- Use preoperatively to establish baseline and teach technique.
- Postoperative use: 10 breaths per session, every 1-2 hours while awake, for first 72h after surgery.
- Evidence supports use in upper abdominal and thoracic procedures.
- Chest physiotherapy: indicated for patients with excessive secretions (COPD, bronchiectasis, cystic fibrosis).
- Preoperative bronchodilator therapy: inhaled beta-2 agonists and anticholinergics for COPD/asthma optimization.
- CPAP/BiPAP: initiate preoperatively in patients with undiagnosed or inadequately treated OSA.

---

### Diabetic Perioperative Management

Hyperglycemia in the perioperative period is associated with increased SSI risk, poor wound healing, prolonged length of stay, and increased mortality. The goal is to maintain blood glucose 140-180 mg/dL intraoperatively and postoperatively.

#### Oral Antidiabetic Agents

| Medication Class | Perioperative Action | Reason |
|-----------------|---------------------|--------|
| Metformin | Hold morning of surgery | Risk of lactic acidosis if contrast used or AKI develops; restart 48h postop when renal function confirmed stable |
| SGLT-2 inhibitors (empagliflozin, dapagliflozin, canagliflozin) | Hold 3 days before surgery | Risk of euglycemic diabetic ketoacidosis (euDKA) with fasting and physiologic stress |
| Sulfonylureas (glipizide, glimepiride) | Hold morning of surgery | Hypoglycemia risk with NPO status |
| GLP-1 agonists (semaglutide, liraglutide) | Hold 1-7 days before surgery (per new ADA/ASA guidance) | Risk of delayed gastric emptying → aspiration |
| Thiazolidinediones (pioglitazone) | Hold morning of surgery | Fluid retention; generally low hypoglycemia risk |
| DPP-4 inhibitors (sitagliptin, saxagliptin) | May continue or hold; low hypoglycemia risk | Generally safe to hold for safety simplicity |

#### Insulin Management

**Day Before Surgery:**
- Continue all usual insulin doses (basal and bolus) with normal meal intake.
- Adjust doses if eating less than usual.

**Morning of Surgery (NPO):**
- Basal insulin: administer 50-80% of usual basal insulin dose (e.g., if patient takes 40 units glargine, give 20-32 units the morning of surgery).
- Bolus/prandial insulin: hold if NPO.
- Insulin pump patients: continue pump at a reduced basal rate (60-80% of usual basal); perioperative glucose monitoring every 30-60 minutes.
- Check blood glucose on arrival, every 1-2h intraoperatively, every 2-4h postoperatively.

**Intraoperative and ICU Insulin Protocols:**
- Continuous IV insulin infusion preferred for critically ill patients or prolonged procedures.
- Target: glucose 140-180 mg/dL (per NICE-SUGAR trial recommendations).
- Intensive glucose control (80-110 mg/dL) increases hypoglycemia and mortality — avoid.

---

### Nutritional Assessment

Malnutrition is an independent predictor of postoperative complications including SSI, anastomotic leak, and mortality.

**High-Risk Nutritional Markers:**
- Serum albumin <3.5 g/dL: low oncotic pressure, impaired tissue healing, high complication risk
- Serum albumin <2.0 g/dL: very high risk; consider delaying elective surgery for nutritional optimization
- Prealbumin (transthyretin) <15 mg/dL: more sensitive acute-phase marker of malnutrition
- Unintentional weight loss >10% body weight in the past 6 months: significant risk factor for poor outcomes
- Weight loss >20%: severe malnutrition; preoperative nutritional support strongly recommended
- BMI <18.5: underweight; higher complication risk

**Nutritional Optimization:**
- Delay elective surgery to allow enteral nutritional supplementation for 7-14 days if severely malnourished.
- Parenteral nutrition (PN): use if GI tract non-functional and surgery can be delayed; associated with infection risk from central venous access.
- Immunonutrition (arginine, omega-3 fatty acids, glutamine): evidence supports use in head and neck cancer, GI cancer, and ICU patients; reduces infectious complications.
- Obesity: independent risk factor for DVT/PE, wound complications, OSA, difficult airway, and anastomotic failure.

---

### Preoperative Fasting Guidelines (ASA NPO Guidelines)

Fasting before anesthesia reduces the risk of pulmonary aspiration of gastric contents. The following are minimum fasting times under the 2017 ASA practice guidelines. Longer fasting does not improve safety.

| Ingested Material | Minimum Fasting Period | Notes |
|-------------------|----------------------|-------|
| Clear liquids (water, clear juice, black coffee/tea, carbonated beverages) | 2 hours | Most important for patient comfort and compliance |
| Breast milk | 4 hours | Applies to infant feeding; shorter than non-human milk |
| Infant formula | 6 hours | More protein than breast milk, slower gastric emptying |
| Non-human milk (cow's milk, soy) | 6 hours | Treat as solids |
| Light meal (toast and clear liquid, no fat or meat) | 6 hours | Fried foods or meat may require 8+ hours |
| Heavy meal (fried foods, fatty foods, meat) | 8 hours | Conservative; always confirm with anesthesiologist |
| Alcohol | Treat as meal; delay surgery if intoxicated | Altered drug metabolism, aspiration risk |

**Special Considerations:**
- Preoperative carbohydrate loading (ERAS protocol): complex carbohydrate drink 400 mL up to 2 hours before surgery; reduces insulin resistance, anxiety, and nausea.
- High aspiration risk patients (GERD, obesity, diabetes with gastroparesis, hiatal hernia, pregnancy): may require longer fast or pharmacologic aspiration prophylaxis (metoclopramide, H2 blocker, sodium citrate).
- Emergency surgery: administer rapid sequence induction (RSI) regardless of fasting status.

---

## Anesthesia Overview

Anesthesia is the pharmacologically induced reversible state of unconsciousness, analgesia, amnesia, and muscle relaxation to allow surgical intervention without patient pain or awareness. Anesthetic management is tailored to the patient, the procedure, and anticipated physiologic changes.

### General Anesthesia

General anesthesia consists of three phases: induction, maintenance, and emergence.

#### Induction Agents

| Agent | Dose | Onset | Key Properties and Indications |
|-------|------|-------|-------------------------------|
| Propofol | 1.5-2.5 mg/kg IV | 30-60 seconds | Standard induction agent; causes hypotension and apnea; antiemetic properties; avoid in egg/soy allergy (lipid emulsion) |
| Etomidate | 0.2-0.3 mg/kg IV | 30-60 seconds | Hemodynamically stable; preferred in shock, cardiovascular compromise, hypovolemia; adrenal suppression with prolonged use — avoid continuous infusion |
| Ketamine | 1-2 mg/kg IV | 30-60 seconds | Dissociative anesthetic; increases HR, BP, and cardiac output (sympathomimetic); bronchodilator; preserves airway reflexes partially; increased oral secretions; emergence delirium (reduce with midazolam); useful in shock, asthma, pediatric patients |
| Thiopental | 3-5 mg/kg IV | 15-30 seconds | Barbiturate; decreases ICP; rarely used in modern anesthesia; decreases cardiac output; long elimination half-life |
| Midazolam | 0.02-0.04 mg/kg IV | 2-3 minutes | Benzodiazepine; anxiolysis and amnesia; often used as premedication rather than induction; reversal with flumazenil |

**Induction adjuncts:**
- Fentanyl 1-3 mcg/kg IV prior to induction: blunts laryngoscopy hemodynamic response
- Lidocaine 1-1.5 mg/kg IV: reduces ICP increase with laryngoscopy; reduces bronchospasm
- Succinylcholine 1.5 mg/kg IV or rocuronium 1.2 mg/kg IV for rapid sequence induction (RSI)

#### Maintenance Agents

**Volatile (Inhaled) Anesthetics:**

| Agent | MAC (%) | Key Properties |
|-------|---------|----------------|
| Sevoflurane | 2.0 | Preferred for inhalational induction (non-pungent); rapid onset and emergence; minimal cardiovascular depression; avoid in malignant hyperthermia susceptible patients |
| Desflurane | 6.0 | Fastest emergence (lowest blood:gas partition coefficient); airway irritant — not used for inhalational induction; requires heated vaporizer |
| Isoflurane | 1.15 | Coronary steal possible in patients with fixed coronary stenosis; significant cardiovascular depression; older but still used |
| Nitrous oxide (N2O) | 104 | Used as adjunct (reduces MAC of volatile agent); diffuses into air-containing spaces (bowel, pneumothorax, middle ear) — contraindicated in pneumothorax, bowel obstruction, intracranial surgery |

MAC (minimum alveolar concentration) = concentration at which 50% of patients do not move with surgical incision. Reduced by opioids, benzodiazepines, hypothermia, elderly age. Increased by hyperthermia, chronic alcohol use, younger age.

**Total Intravenous Anesthesia (TIVA):**
- Propofol infusion 25-150 mcg/kg/min + remifentanil or other opioid infusion.
- Preferred when volatile agents are contraindicated (malignant hyperthermia susceptibility), in neurophysiologic monitoring cases, or when PONV risk is high.

#### Emergence

- Emergence phase: discontinuation of anesthetic agents, reversal of neuromuscular blockade, and return of spontaneous ventilation and consciousness.
- Neuromuscular blockade reversal: neostigmine 0.04-0.07 mg/kg + glycopyrrolate 0.2 mg per 1 mg neostigmine; or sugammadex 2 mg/kg for rocuronium/vecuronium reversal.
- Complications: laryngospasm, bronchospasm, breath-holding, coughing, agitation (especially in pediatric patients), residual neuromuscular blockade.
- Smooth extubation criteria: patient awake and following commands, sustained head lift >5 seconds, tidal volume >5 mL/kg, adequate reversal (TOF ratio >0.9).

---

### MAC — Monitored Anesthesia Care and Sedation

**MAC (Monitored Anesthesia Care):**
- Anesthesiologist or CRNA present; patient retains spontaneous ventilation and airway reflexes.
- Common agents: midazolam (anxiolysis), fentanyl/remifentanil (analgesia), propofol infusion (sedation), ketamine (dissociation/analgesia).
- Used for: endoscopy, ophthalmology, cardiac catheterization, superficial surgery, biopsies.
- Risk: deep sedation may progress to general anesthesia; airway management equipment always available.

**Conscious Sedation (Moderate Sedation):**
- Can be administered by non-anesthesiologist practitioners under specific credentialing.
- Patient responds purposefully to verbal or tactile stimulation.
- Commonly midazolam + fentanyl.

**Sedation Depth Scale (RASS):**

| Score | Label | Description |
|-------|-------|-------------|
| +4 | Combative | Overtly combative, violent, immediate danger to staff |
| +3 | Very agitated | Pulls or removes tubes/catheters; aggressive |
| +2 | Agitated | Frequent non-purposeful movement, fights ventilator |
| +1 | Restless | Anxious but movements not aggressive or vigorous |
| 0 | Alert and calm | Target for most non-ventilated patients |
| -1 | Drowsy | Not fully alert; sustained awakening >10 seconds |
| -2 | Light sedation | Briefly awakens to voice (<10 seconds) |
| -3 | Moderate sedation | Movement or eye opening to voice, no gaze |
| -4 | Deep sedation | No response to voice; movement to physical stimulation |
| -5 | Unarousable | No response to voice or physical stimulation |

Target RASS: 0 to -2 for most ICU patients on mechanical ventilation per SCCM guidelines.

---

### Neuraxial Anesthesia

Neuraxial anesthesia involves injection of local anesthetic into the subarachnoid (spinal) or epidural space to produce regional block of the spinal cord and nerve roots.

#### Spinal Anesthesia

- Single injection into the subarachnoid (intrathecal) space, typically at L3-L4 or L4-L5 (below spinal cord termination at L1-L2).
- Onset: 5-10 minutes; duration dependent on agent (bupivacaine 2-3h, tetracaine 2-4h).
- Produces: motor block, sensory block, sympathetic blockade (hypotension).
- Level of block: T4 = nipple line (adequate for lower abdominal/pelvic); T10 = umbilicus; T12 = inguinal ligament; L1-S5 = lower extremities.
- Indications: inguinal hernia, hip/knee arthroplasty, TURP, cesarean section, lower abdominal procedures.
- Complications: post-dural puncture headache (PDPH) — treated with caffeine, hydration, epidural blood patch; total spinal (high block); hypotension (treat with vasopressor — ephedrine or phenylephrine; IV fluid bolus).

#### Epidural Anesthesia

- Catheter-based, continuous infusion into epidural space; onset 15-30 minutes.
- Does NOT puncture dura; no PDPH risk with careful technique.
- Allows titration of level and duration; catheter can remain for postoperative analgesia.
- Common infusion: bupivacaine 0.1-0.25% + fentanyl or hydromorphone.
- Indications: thoracic and abdominal surgery, labor analgesia, post-thoracotomy pain.
- Complications: dural puncture headache (wet tap), high/total spinal, epidural hematoma (monitor closely in anticoagulated patients), epidural abscess (infectious), urinary retention.
- Contraindications: coagulopathy, thrombocytopenia, patient refusal, increased ICP, infection at injection site, hemodynamic instability.

**Anticoagulation and Neuraxial Timing:**

| Anticoagulant | Hold Before Neuraxial | Resume After Neuraxial |
|---------------|----------------------|------------------------|
| LMWH prophylactic (enoxaparin 40mg) | 12h before | 12h after |
| LMWH therapeutic (enoxaparin 1mg/kg BID) | 24h before | 24h after |
| Warfarin | INR <1.4 | 24h after |
| UFH prophylactic | 4h before | 1h after |
| Apixaban/Rivaroxaban | 48-72h | 6h after |

---

### Regional Nerve Blocks

Regional anesthesia uses local anesthetic injection near peripheral nerve trunks to produce sensory and motor block of a defined anatomical region. Performed with ultrasound guidance or nerve stimulator.

#### Upper Extremity Blocks

| Block | Approach | Coverage | Common Indications |
|-------|----------|----------|--------------------|
| Interscalene | Lateral neck, C5-C6 level | Shoulder and upper arm (C5, C6, C7) | Shoulder arthroplasty, rotator cuff, proximal humerus |
| Supraclavicular | Above clavicle, brachial plexus trunk level | Entire arm below shoulder | Forearm and hand surgery; humerus fractures |
| Infraclavicular | Below clavicle, cord level | Elbow, forearm, hand | Radial/ulnar/median nerve territory procedures |
| Axillary | Medial upper arm, terminal branch level | Elbow, forearm, hand (not axilla) | Hand surgery, forearm procedures |

Complications of upper extremity blocks: pneumothorax (interscalene and supraclavicular, 0.5-1%), phrenic nerve palsy (interscalene — 100% ipsilateral; contraindicated in contralateral phrenic palsy or single lung), Horner syndrome, intravascular injection, nerve injury.

#### Lower Extremity Blocks

| Block | Coverage | Common Indications |
|-------|----------|--------------------|
| Femoral nerve block | Anterior thigh, knee (anteromedial) | Femur fracture pain, knee surgery |
| Adductor canal block | Medial knee and leg (saphenous nerve, distal femoral nerve) | Total knee arthroplasty (motor-sparing — preferred over femoral nerve block to allow early ambulation) |
| Popliteal sciatic block | Foot and ankle (excluding medial aspect), posterior leg | Foot and ankle surgery, below-knee amputation |
| Fascia iliaca block | Femoral nerve territory | Hip fracture analgesia |
| PENG (pericapsular nerve group) block | Obturator, femoral, accessory obturator nerves at hip capsule | Hip arthroplasty, hip fracture analgesia |

---

### Malignant Hyperthermia

Malignant hyperthermia (MH) is a pharmacogenetic disorder of skeletal muscle causing an uncontrolled increase in intracellular calcium triggered by specific anesthetic agents.

**Triggering Agents:**
- All volatile inhalational anesthetics: halothane, isoflurane, sevoflurane, desflurane
- Succinylcholine (depolarizing neuromuscular blocking agent)

**Pathophysiology:**
- Mutation in RYR1 gene (ryanodine receptor type 1) → unregulated calcium release from sarcoplasmic reticulum → sustained muscle contraction, hyperthermia, metabolic crisis.
- Autosomal dominant inheritance with variable penetrance.

**Clinical Presentation (MAUS mnemonic):**
- Muscle rigidity (masseter spasm often first sign, generalized rigidity)
- Acidosis (metabolic and respiratory — increased CO2 production)
- Unexplained tachycardia and hypertension
- Sweating and skin mottling
- Hyperthermia (late sign — temperature rise up to 1-2°C per 5 minutes in fulminant cases)
- Hypercarbia (rising ETCO2 — often earliest sign)
- Rhabdomyolysis, hyperkalemia, elevated CK
- Disseminated intravascular coagulation (DIC) in severe cases

**Treatment:**
1. Immediately stop volatile anesthetic and succinylcholine.
2. Call for help; notify surgeon to stop or expedite procedure.
3. Switch to TIVA (propofol-based) or air-only ventilation.
4. Hyperventilate with 100% O2 (high flow >10 L/min); use clean circuit.
5. Dantrolene 2.5 mg/kg IV bolus — repeat every 5 minutes up to 10 mg/kg total until symptoms controlled.
6. Sodium bicarbonate for severe metabolic acidosis.
7. Active cooling: ice packs to axillae/groin, cold IV fluids, cold gastric lavage, cooling blankets.
8. Treat hyperkalemia: calcium chloride (stabilize membrane), insulin + dextrose, sodium bicarbonate.
9. Monitor urine output; maintain UOP >1-2 mL/kg/hr with IV fluids (prevent myoglobinuric renal failure).
10. ICU admission; continue dantrolene 1 mg/kg Q6h for 24-48 hours.
11. Refer patient and family for genetic counseling and MH testing (caffeine-halothane contracture test, or genetic testing for RYR1/CACNA1S mutations).

**MH Hotline (MHAUS): 1-800-644-9737** (available 24/7 for anesthesiologists).

**Dantrolene Mechanism:** Binds ryanodine receptor, inhibits calcium release from sarcoplasmic reticulum.

---

### Succinylcholine — Contraindications and Dangers

Succinylcholine is a depolarizing neuromuscular blocker used in RSI for its ultra-rapid onset (60 seconds) and short duration (10-15 minutes). It causes fasciculations and transient hyperkalemia (~0.5 mEq/L normal patients).

**Absolute Contraindications (risk of severe hyperkalemia — potentially fatal):**

| Condition | Mechanism |
|-----------|-----------|
| Burn injuries (>72 hours post-burn) | Upregulation of extrajunctional ACh receptors causes massive K+ efflux with depolarization |
| Crush injuries and muscle trauma (>24-48h) | Same receptor upregulation mechanism; K+ release can cause VF/asystole |
| Prolonged immobilization or denervation | Proliferation of extrajunctional ACh receptors in atrophied or denervated muscle |
| Upper motor neuron lesions (stroke, spinal cord injury) | Denervation hypersensitivity and upregulation of immature (extrajunctional) ACh receptors |
| Neuromuscular disorders (Duchenne muscular dystrophy, polymyositis, severe myopathy) | Fragile membranes; abnormal receptor distribution |
| Hyperkalemia (pre-existing K+ >5.5 mEq/L) | Even normal depolarization-associated K+ rise can push into fatal range |

**Other Cautions:**
- Pseudocholinesterase deficiency (genetic): prolonged blockade (succinylcholine apnea); treat with FFP or fresh blood; support ventilation.
- Glaucoma (open angle): avoid; transient increase in intraocular pressure.
- Personal or family history of malignant hyperthermia: contraindicated.
- Penetrating eye injury: contraindicated (IOP increase).

Alternative to succinylcholine for RSI: high-dose rocuronium 1.2 mg/kg IV (equivalent onset; reversed by sugammadex 16 mg/kg if needed urgently).

---

## Fluid Management

### Maintenance Fluid Calculation — 4-2-1 Rule

Used to calculate maintenance fluid rate for NPO patients or those unable to take oral fluids.

| Weight Range | Rate |
|-------------|------|
| First 0-10 kg | 4 mL/kg/hr |
| Next 10-20 kg (kg 11-20) | +2 mL/kg/hr |
| Each kg above 20 kg | +1 mL/kg/hr |

Example: 70 kg patient = (4 x 10) + (2 x 10) + (1 x 50) = 40 + 20 + 50 = 110 mL/hr.

Maintenance fluids are used when oral intake is not possible. They are NOT a substitute for resuscitation fluids in hypovolemic states.

---

### Crystalloid Solutions

| Solution | Na+ (mEq/L) | Cl- (mEq/L) | K+ (mEq/L) | Bicarb/Equiv | Osmolarity | Notes |
|----------|-------------|-------------|------------|-------------|------------|-------|
| Normal Saline (0.9% NaCl) | 154 | 154 | 0 | 0 | 308 | Hyperchloremic non-anion gap metabolic acidosis with large volumes; avoid in TBI (hypertonicity) |
| Lactated Ringer's (LR) | 130 | 109 | 4 | 28 (lactate) | 273 | More physiologic; avoid in severe hepatic failure (cannot metabolize lactate) and hyperkalemia (contains 4 mEq/L K+) |
| PlasmaLyte | 140 | 98 | 5 | 50 (acetate + gluconate) | 295 | Most physiologic; no lactate; acetate metabolized in muscle; preferred in liver failure and hyperkalemia |
| D5W (5% dextrose in water) | 0 | 0 | 0 | 0 | 252 | Effectively free water after dextrose metabolized; use for free water replacement, not volume resuscitation |
| D5 0.45% NaCl (D5 half-normal) | 77 | 77 | 0 | 0 | 406 | Standard maintenance for peds and some adults; not appropriate for resuscitation |
| 3% NaCl (hypertonic) | 513 | 513 | 0 | 0 | 1026 | Reserved for severe symptomatic hyponatremia correction or ICP reduction |

---

### Goal-Directed Fluid Therapy

Traditional fluid management used static parameters (CVP, pulmonary artery occlusion pressure) to guide fluid resuscitation. Evidence now strongly favors dynamic parameters reflecting volume responsiveness.

**Dynamic Parameters (superior to CVP):**
- Pulse pressure variation (PPV): variation in arterial pulse pressure during mechanical ventilation. PPV >13% predicts fluid responsiveness in mechanically ventilated patients with normal sinus rhythm.
- Stroke volume variation (SVV): similar principle; derived from pulse oximetry plethysmography or arterial waveform.
- Passive leg raise (PLR) maneuver: raise legs to 45° from supine; fluid challenge equivalent of 300-450 mL; if CO increases >10%, patient is fluid responsive.

**Why CVP Is Unreliable:**
- Central venous pressure (CVP) does not reliably predict fluid responsiveness.
- Large variations in CVP can occur without actual volume change due to venous compliance changes.
- FEAST trial and multiple systematic reviews: no benefit to targeting high CVP in critically ill patients; harm from excessive fluid administration.

**Fluid Overload Consequences:**
- Pulmonary edema
- Abdominal compartment syndrome
- Anastomotic edema and leak risk
- Prolonged ileus
- Peripheral edema and poor wound healing

**Perioperative Goal-Directed Therapy (GDT) Protocol (ERAS surgery):**
- Avoid preoperative prolonged fasting; give carbohydrate loading.
- Intraoperative euvolemia (zero balance); use dynamic parameters.
- Avoid prophylactic IV fluid boluses; replace losses as they occur.
- Postoperative: transition to oral fluids as soon as tolerated.

---

### Colloid Solutions

| Colloid | Type | Mechanism | Indications | Contraindications / Adverse Effects |
|---------|------|-----------|-------------|-------------------------------------|
| Albumin 5% | Natural protein colloid | Volume expansion (isoncotic) | Resuscitation when crystalloid exceeds 3-4L; spontaneous bacterial peritonitis; large-volume paracentesis | Expensive; allergic reaction (rare); theoretical coagulopathy with large volumes |
| Albumin 25% | Concentrated natural protein | Draws fluid from interstitium to intravascular | Hepatic failure with ascites (autorefusion); nephrotic syndrome; burns | Volume overload risk; less useful if capillary leak present |
| Hetastarch (HES, Voluven) | Synthetic hydroxyethyl starch | Volume expansion | Previously used in surgical resuscitation | AVOID in sepsis (increased mortality — CHEST, 6S trials); AKI risk; coagulopathy (inhibits Factor VIII, vWF, platelet function); pruritus |
| Dextran 40/70 | Polysaccharide | Volume expansion; reduces blood viscosity | Limited use; formerly used in vascular surgery | Anaphylaxis; coagulopathy; renal tubular obstruction; avoid before blood typing (interferes with crossmatch) |

---

### Transfusion Medicine

#### Red Blood Cell (pRBC) Transfusion

**Trigger:**
- Hemoglobin <7 g/dL: transfuse in most stable hospitalized patients.
- Hemoglobin 7-8 g/dL: transfuse if symptomatic (chest pain, dyspnea, hypotension, tachycardia) or active cardiac ischemia.
- Hemoglobin <8 g/dL: threshold for cardiac surgery patients, active myocardial ischemia.
- Hemoglobin <10 g/dL: rarely indicated except in symptomatic cardiac patients with ongoing ischemia.

Liberal vs. restrictive: TRICC, TRISS, FOCUS trials all support restrictive strategy (Hgb 7-8 g/dL trigger) in most patients.

**One unit pRBC:** ~250-300 mL; raises hemoglobin ~1 g/dL in a 70-kg adult; raises hematocrit ~3%.

**Transfusion Complications:**

| Complication | Timing | Mechanism | Features |
|-------------|--------|-----------|---------|
| TACO (Transfusion-Associated Circulatory Overload) | During/immediately after | Volume overload | Dyspnea, hypertension, bilateral crackles, worsening oxygenation; treat with diuresis |
| TRALI (Transfusion-Related Acute Lung Injury) | Within 6h | Donor anti-HLA/anti-neutrophil antibodies activate recipient neutrophils | Fever, hypoxia, bilateral infiltrates, NON-cardiogenic pulmonary edema; hypotension; treat supportively |
| Febrile Non-Hemolytic Reaction | During/within 4h | Cytokines in stored blood or recipient antibodies to donor leukocytes | Fever, chills, no hemolysis; pre-medicate with acetaminophen |
| Acute Hemolytic Reaction | Immediate | ABO incompatibility | Fever, flank pain, hemoglobinuria, DIC, shock; STOP transfusion immediately; resuscitate; fluids + diuretics |
| Delayed Hemolytic Reaction | 3-14 days post | Minor antigen (Kidd, Duffy) anamnestic response | Falling Hgb, rising bilirubin, mild jaundice, positive Coombs |
| Septic Transfusion | During | Bacterial contamination (platelets most common: Staphylococcus) | High fever, rigors, hypotension; broad-spectrum antibiotics |
| Allergic/Anaphylactic | During | IgE-mediated response to plasma proteins | Urticaria, bronchospasm, anaphylaxis; treat with diphenhydramine, epinephrine if anaphylaxis |

#### Blood Products

| Product | Volume/Unit | Contains | One-Unit Effect |
|---------|------------|---------|-----------------|
| pRBC | ~250-350 mL | Red blood cells, minimal plasma/platelets | Raises Hgb ~1 g/dL, Hct ~3% |
| Fresh Frozen Plasma (FFP) | ~250 mL | All coagulation factors, protein C/S, fibrinogen (~2.5 mg/mL) | Raises clotting factors ~15-20%; INR reduction variable; 1 INR unit |
| Platelets — apheresis | ~250 mL | ~3×10^11 platelets | Raises platelet count ~30,000-50,000/mcL |
| Platelets — pooled (6 units) | ~250 mL | Equivalent to 1 apheresis unit | Raises platelet count ~30,000-50,000/mcL |
| Cryoprecipitate | 10-20 mL/unit (typical dose: 10 units pooled) | Fibrinogen (~150-250 mg/unit), Factor VIII, vWF, Factor XIII, fibronectin | 10-unit pool raises fibrinogen ~50-100 mg/dL |

**Transfusion of Fibrinogen:** Target fibrinogen >100 mg/dL in bleeding patients (>200 mg/dL in obstetric hemorrhage). Source: cryoprecipitate (first-line) or fibrinogen concentrate (Riastap).

#### Coagulopathy Management

| Condition | Treatment |
|-----------|-----------|
| Warfarin reversal — non-urgent | Vitamin K 5-10 mg IV/PO (INR normalizes in 24-48h) |
| Warfarin reversal — urgent (significant bleeding) | 4-factor PCC (KCentra) + Vitamin K; PCC provides rapid INR correction |
| DOAC reversal — dabigatran | Idarucizumab (Praxbind) 5g IV |
| DOAC reversal — apixaban/rivaroxaban | Andexanet alfa (Andexxa); or 4-factor PCC if unavailable |
| Uremic platelet dysfunction | DDAVP (desmopressin) 0.3 mcg/kg IV; improves platelet function via vWF release |
| Mild hemophilia A or von Willebrand disease (type 1) | DDAVP 0.3 mcg/kg IV; releases stored vWF and Factor VIII |
| Hemophilia A — moderate/severe | Factor VIII concentrate (recombinant preferred) |
| Hemophilia B | Factor IX concentrate |
| Heparin toxicity | Protamine sulfate: 1 mg per 100 units UFH administered in last 2-3h |
| Platelet dysfunction (aspirin, clopidogrel) — emergency | Platelet transfusion |
| Massive transfusion coagulopathy | Balanced resuscitation: 1:1:1 ratio pRBC:FFP:platelets; tranexamic acid (TXA) early (within 3h of injury) |

---

## Surgical Site Infections and Wound Care

### CDC Classification of Surgical Site Infections

| Class | Definition | Characteristics |
|-------|------------|----------------|
| Superficial Incisional | Involves only skin or subcutaneous tissue of incision | Occurs within 30 days; purulent drainage, or organisms from culture, or surgeon diagnosis |
| Deep Incisional | Involves deep soft tissues (fascia, muscle) | Within 30 days (no implant) or 90 days (with implant); pus, dehiscence, fever + localized pain; abscess on imaging |
| Organ/Space | Involves any anatomy opened or manipulated during operation (other than incision) | Pus from drain placed into organ space; abscess or infection in organ space; positive culture |

### Antibiotic Prophylaxis

Surgical antibiotic prophylaxis is administered to prevent SSI, not to treat established infection. Proper timing is critical — antibiotic must be in tissues at the time of incision.

| Procedure | First-Line Prophylaxis | Alternative (Beta-lactam Allergy) |
|-----------|----------------------|----------------------------------|
| Clean and clean-contaminated abdominal, orthopedic, vascular, cardiothoracic | Cefazolin 2g IV (<120 kg); 3g IV (>120 kg) | Clindamycin (gram-positive coverage) OR gentamicin/aztreonam (gram-negative) |
| Colorectal surgery | Cefazolin + metronidazole, OR ertapenem | Gentamicin + metronidazole OR clindamycin |
| MRSA colonization | Vancomycin 15 mg/kg IV (max 3g) in addition to standard prophylaxis | Continue vancomycin as alternative |
| Cardiac procedures with prosthetic material | Cefazolin ± vancomycin (MRSA high-risk units) | Vancomycin 15 mg/kg |
| Hysterectomy | Cefazolin 2g + metronidazole | Clindamycin + gentamicin |
| Urologic procedures (GU manipulation) | Fluoroquinolone OR TMP-SMX, based on urine culture | Gentamicin |

**Timing:** Within 60 minutes of skin incision (vancomycin and fluoroquinolones: within 120 minutes due to longer infusion time).
**Redosing:** Every 4 hours for cefazolin during prolonged procedures, or every 2 half-lives of the drug if blood loss >1500 mL.
**Duration:** Single dose for most procedures; not more than 24 hours postoperatively (24 hours for cardiothoracic surgery).

---

### Wound Classification

| Class | Definition | SSI Risk | Examples |
|-------|------------|---------|---------|
| Clean | Uninfected operative wound; no inflammation; no hollow viscus entered; closed primarily | 1-5% | Hernia repair, vascular surgery, breast surgery, craniotomy |
| Clean-Contaminated | Hollow viscus entered under controlled conditions (no unusual contamination) | 5-15% | Elective colon resection, cholecystectomy, hysterectomy, nephrectomy |
| Contaminated | Open fresh wounds; major break in sterile technique; bile/GI spillage; acute non-purulent inflammation | 15-30% | Penetrating trauma <6 hours, gross contamination during hollow viscus repair |
| Dirty/Infected | Old traumatic wounds with devitalized tissue; existing infection; perforated viscus | >30% | Perforated appendicitis, diverticular abscess, fecal peritonitis |

---

### Wound Healing Phases

| Phase | Duration | Key Events |
|-------|----------|-----------|
| Hemostasis | Minutes (0-30 min) | Platelet activation, fibrin clot formation, vasospasm; growth factor release (PDGF, TGF-β) |
| Inflammatory | Days 1-5 | Neutrophil infiltration (days 1-2), macrophage dominance (days 2-5); debridement of bacteria and debris; cytokine release; neovascularization begins |
| Proliferation | Days 5-21 | Fibroblast migration and collagen synthesis (type III collagen initially); angiogenesis; wound contraction (myofibroblasts); epithelialization |
| Remodeling | Weeks to 2 years | Type III collagen replaced by type I collagen; wound strength increases to ~80% of normal (never reaches 100%); scar maturation |

**Factors Impairing Wound Healing:**

| Category | Specific Factors |
|---------|----------------|
| Systemic | Diabetes (neuropathy, microvascular disease, hyperglycemia impairs neutrophil function), malnutrition (protein/zinc/vitamin C deficiency), anemia, renal failure, liver failure |
| Pharmacologic | Corticosteroids (suppress inflammation and collagen synthesis), chemotherapy, immunosuppressants, NSAIDs |
| Local | Infection, hematoma, seroma, excessive tension on wound, radiation (obliterative endarteritis of local vasculature), poor blood supply |
| Patient factors | Smoking (vasoconstriction, carboxyhemoglobin), obesity, age (decreased angiogenesis and cellular proliferation) |

---

### Negative Pressure Wound Therapy (NPWT/VAC)

Negative pressure wound therapy uses subatmospheric pressure applied to an open wound through foam or gauze interface to promote healing.

**Mechanisms of Action:**
- Removes wound exudate and edema
- Increases local blood flow
- Promotes granulation tissue formation
- Reduces bacterial burden
- Mechanically draws wound edges together

**Indications:**
- Open and complex wounds (traumatic, surgical dehiscence)
- Diabetic foot ulcers
- Pressure ulcers (stage III and IV)
- Burns (split-thickness skin graft bolstering)
- Open abdomen (temporary abdominal closure in damage control surgery)
- Sternal wound infections post-cardiac surgery

**Settings:**
- Continuous mode: -125 mmHg — preferred for acute wounds, high-exudate wounds
- Intermittent mode: cycles between -125 mmHg and 0 mmHg — may enhance granulation tissue formation in chronic wounds; less comfortable

**Contraindications:**
- Necrotic tissue with eschar (debride first)
- Untreated osteomyelitis
- Malignancy in wound
- Exposed blood vessels or organs (without interposed fascia)
- Fistula to body cavity
- Dry wound or wound not requiring drainage

---

## Abdominal Surgery

### Appendicitis

#### Clinical Presentation
Acute appendicitis results from obstruction of the appendiceal lumen (fecalith, lymphoid hyperplasia, carcinoid) leading to distension, ischemia, and bacterial invasion.

**Classic Symptom Sequence:**
1. Visceral pain — periumbilical or diffuse, poorly localized (stretching of appendix)
2. Anorexia and nausea/vomiting
3. Migration of pain to right lower quadrant (RLQ) — as parietal peritoneum becomes involved
4. Fever (usually low-grade in uncomplicated; high fever suggests perforation)
5. Leukocytosis (typically 10,000-18,000; left shift common)

**Physical Exam Findings:**
- McBurney's point tenderness: 1/3 of the way from the ASIS to the umbilicus
- Rebound tenderness (Blumberg's sign)
- Guarding and involuntary rigidity (peritoneal signs)
- Rovsing's sign: RLQ pain on palpation of LLQ (cross-rebound)
- Psoas sign: RLQ pain with right hip extension (retrocecal appendix)
- Obturator sign: RLQ pain with internal rotation of right hip (pelvic appendix)

#### Alvarado Score

| Finding | Points |
|---------|--------|
| Migration of pain to RLQ | 1 |
| Anorexia | 1 |
| Nausea or vomiting | 1 |
| Tenderness in RLQ | 2 |
| Rebound tenderness | 1 |
| Elevated temperature (>37.3°C / 99.1°F) | 1 |
| Leukocytosis (WBC >10,000) | 2 |
| Leukocyte left shift | 1 |
| **Total** | **10** |

Score 7-10: highly suggestive appendicitis; Score 5-6: compatible, consider CT; Score 1-4: appendicitis unlikely.

#### Imaging

- **CT abdomen and pelvis with IV contrast**: gold standard. Sensitivity 94-98%, specificity 95%. Signs: appendix >6mm, periappendiceal fat stranding, appendicolith, abscess, free fluid, perforation.
- **Ultrasound**: first-line in children and pregnant patients to avoid radiation. Less operator-dependent in lean patients. Signs: non-compressible appendix >6mm diameter. Sensitivity 71-86% (poor for retrocecal or obese patients).
- **MRI**: preferred in pregnancy when ultrasound equivocal. High sensitivity and specificity; expensive and not always available emergently.

#### Treatment

**Uncomplicated Appendicitis (non-perforated):**
- Laparoscopic appendectomy: standard of care. Advantages: less SSI, shorter hospital stay, faster recovery.
- Non-operative management (antibiotics alone): IV antibiotics (ertapenem, pip-tazo, or cefoxitin) for 24-48h, then oral antibiotics for total 10-day course. Success rate ~70% at 1 year. ~30% will develop recurrent appendicitis requiring surgery.
- Non-operative management with appendicolith: higher failure rate; laparoscopic appendectomy generally preferred.

**Complicated Appendicitis (perforated with phlegmon or abscess):**
- Phlegmon: IV antibiotics + percutaneous CT-guided drainage if abscess >3 cm. Interval appendectomy in 6-8 weeks (controversial — many surgeons defer if asymptomatic at follow-up).
- Perforated with diffuse peritonitis: emergent laparoscopic or open appendectomy with washout.

**Antibiotic Coverage:**
- Must cover gram-negative enteric organisms (E. coli, Klebsiella) and anaerobes (Bacteroides fragilis)
- Cefoxitin (2nd-generation cephalosporin with anaerobic coverage) — adequate for uncomplicated
- Piperacillin-tazobactam (pip-tazo) — broad-spectrum; used for complicated/perforated
- Ertapenem — effective carbapenem; used for hospital-acquired resistant organisms or severe cases

---

### Acute Cholecystitis and Biliary Emergencies

#### Biliary Colic vs. Acute Cholecystitis

| Feature | Biliary Colic | Acute Cholecystitis |
|---------|--------------|---------------------|
| Duration | 30 min to 6h; self-limited | Persistent >6h; progressive |
| Pain | Episodic, colicky, postprandial | Constant, progressive, RUQ |
| Fever | Absent | Present |
| Leukocytosis | Absent | Present |
| Murphy's sign | Absent | Present |
| Ultrasound | Gallstones, no wall thickening | Gallstones, wall >4mm, pericholecystic fluid, sonographic Murphy's |
| Cause | Transient cystic duct obstruction | Sustained cystic duct obstruction → inflammation, secondary infection |

**Ultrasound Findings in Acute Cholecystitis:**
- Gallbladder wall thickening >4 mm
- Pericholecystic fluid
- Sonographic Murphy's sign (maximum tenderness under ultrasound probe over gallbladder)
- Gallstones (90% of acute cholecystitis)
- Sludge, distension

**HIDA Scan (Hepatobiliary Iminodiacetic Acid):**
- Functional test assessing cystic duct patency and gallbladder ejection fraction.
- Non-visualization of gallbladder (blocked cystic duct): sensitivity 97%, specificity 90% for acute cholecystitis.
- Used when ultrasound is equivocal or when acalculous cholecystitis suspected.
- Ejection fraction <35% on CCK-stimulated HIDA: biliary dyskinesia.

#### Cholangitis

**Pathophysiology:** Bacterial infection of bile ducts, usually from choledocholithiasis causing bile stasis, biliary obstruction, and ascending bacterial infection.

**Charcot's Triad (Classic):** Present in 50-70% of cases.
- Fever and chills
- Jaundice (elevated bilirubin, alkaline phosphatase)
- RUQ pain

**Reynolds Pentad (Severe/Suppurative):** Charcot's Triad plus:
- Hypotension (septic shock)
- Altered mental status (AMS/confusion)

**Treatment of Cholangitis:**
1. Resuscitation: IV fluids, vasopressors if needed, correct coagulopathy.
2. IV antibiotics immediately: cover gram-negatives (E. coli, Klebsiella, Pseudomonas) and anaerobes (Bacteroides).
   - Mild-moderate: ampicillin-sulbactam, piperacillin-tazobactam, or cefazolin + metronidazole
   - Severe/septic: piperacillin-tazobactam, ertapenem, or carbapenem
3. Urgent biliary decompression: ERCP with sphincterotomy and stone extraction (first-line), or surgical drainage, or percutaneous transhepatic biliary drain (PTBD) if ERCP fails.
4. Cholecystectomy: after acute episode resolved (interval 6-8 weeks).

**Tokyo Guidelines Severity Grading for Cholangitis:**
- Grade I (Mild): Responds to initial antibiotic therapy; no organ dysfunction.
- Grade II (Moderate): Inadequate response to initial medical therapy; localized inflammation.
- Grade III (Severe): Organ dysfunction (cardiovascular, neurologic, respiratory, renal, hepatic, hematologic); requires urgent biliary decompression.

#### Acute Cholecystitis Treatment

- IV antibiotics: cefazolin + metronidazole (mild); pip-tazo (moderate-severe or high flora risk)
- Laparoscopic cholecystectomy: preferred within 72 hours of symptom onset (early surgery superior to delayed in ACALC trial and meta-analyses: shorter LOS, equivalent complication rate, avoids recurrent attacks during prolonged conservative management)
- High-risk patients: percutaneous cholecystostomy (ultrasound-guided drainage) as bridge to elective cholecystectomy

---

### Bowel Obstruction

#### Small Bowel Obstruction (SBO)

**Etiology (most common causes):**
1. Adhesions: 60-75% of SBOs; prior abdominal surgery (especially pelvic, appendectomy, right colectomy)
2. Hernia (external — inguinal, femoral, umbilical): 15-20%; consider if no prior surgery
3. Malignancy: 5-10%
4. Crohn's disease: strictures from inflammation or fibrosis
5. Intussusception: most common in children; lead point in adults (lipoma, carcinoid, lymphoma)
6. Gallstone ileus: large gallstone erodes into duodenum via cholecystoduodenal fistula; Rigler's triad on X-ray (pneumobilia, SBO, ectopic gallstone)

**Clinical Presentation:**
- Colicky, crampy abdominal pain (worse with peristalsis)
- Vomiting (bilious early; feculent late in distal SBO)
- Abdominal distension (more pronounced with distal obstruction)
- Obstipation (inability to pass gas or stool) in complete obstruction
- High-pitched, tinkling bowel sounds early; absent bowel sounds late (strangulation)

**CT Findings:**
- Dilated small bowel loops >3 cm
- Transition point: abrupt change from dilated to decompressed bowel
- Air-fluid levels on upright X-ray or CT
- Free fluid, mesenteric edema, bowel wall thickening: suggest strangulation or ischemia (requires urgent surgery)
- Pneumatosis intestinalis, portal venous gas: bowel necrosis (emergency)

**Management:**

| Scenario | Management |
|---------|------------|
| Partial SBO, no strangulation | NPO, NGT decompression, IV fluids, serial exams; 72h trial of conservative management |
| Complete SBO | Nasogastric tube, IV fluids, electrolyte correction; surgical consultation; prompt surgery if no resolution |
| Signs of strangulation | Emergent surgery (increased WBC, fever, peritoneal signs, CT findings of ischemia) |
| Adhesiolysis failure at 3-5 days | Surgery |

Water-soluble contrast study (gastrografin): used to predict likelihood of non-operative resolution in adhesive SBO. Contrast in colon within 24h predicts resolution.

#### Large Bowel Obstruction (LBO)

**Etiology:**
- Colorectal carcinoma (60%): most common cause of LBO
- Sigmoid volvulus (15%): elderly, institutionalized, constipated patients; "coffee bean" sign on X-ray
- Cecal volvulus (10%): younger patients; mobile cecum twists on mesentery
- Diverticular stricture
- Ogilvie syndrome (pseudo-obstruction)

**Management by Cause:**

| Cause | Primary Management |
|-------|-------------------|
| Colorectal cancer causing obstruction | Colonic stent (bridge to elective surgery) or Hartmann's procedure (emergent) |
| Sigmoid volvulus | Endoscopic (rigid or flexible scope) decompression; recurrence rate 50-90% without sigmoid resection; elective surgery after decompression |
| Cecal volvulus | Surgical (cecopexy + resection); endoscopic decompression rarely successful |
| Ogilvie syndrome | Neostigmine 2 mg slow IV infusion (monitoring for bradycardia/bronchospasm with atropine available); colonoscopic decompression if neostigmine fails |

**Ogilvie Syndrome (Acute Colonic Pseudo-Obstruction):**
- Massive colonic dilation without mechanical obstruction
- Risk: cecal diameter >12 cm associated with perforation risk
- Predisposing factors: recent surgery (especially orthopedic), spinal cord injury, opioids, electrolyte abnormalities, severe illness
- Treatment ladder: correct electrolytes, minimize opioids, ambulate → neostigmine (most effective pharmacologic) → colonoscopic decompression → surgery (rare)
- Neostigmine 2 mg IV over 3-5 minutes; watch for bradycardia (treat with atropine 0.5-1 mg); contraindicated in mechanical obstruction, sepsis, severe asthma

---

### Hernia

#### Inguinal Hernia Classification

**Anatomic Distinction:**

| Type | Location | Contents at Risk | Repair Approach |
|------|----------|-----------------|-----------------|
| Indirect inguinal | Protrudes through deep inguinal ring, lateral to inferior epigastric vessels, follows spermatic cord | Contains processus vaginalis; most common hernia in all ages and both sexes | Mesh repair (Lichtenstein open or laparoscopic TAPP/TEP) |
| Direct inguinal | Protrudes through Hesselbach's triangle (medial to inferior epigastric vessels, above inguinal ligament, lateral to rectus sheath) | Defect in transversalis fascia | Mesh repair; lower strangulation risk than indirect |
| Femoral | Protrudes through femoral canal, below inguinal ligament, medial to femoral vein, lateral to pubic tubercle | More common in women; highest incarceration/strangulation rate of groin hernias | Emergency repair if strangulated; elective repair always warranted |

**Hernia Status:**
- Reducible: contents can be manually returned to peritoneal cavity.
- Incarcerated: contents cannot be reduced; not necessarily ischemic.
- Strangulated: blood supply compromised; ischemia and necrosis; surgical emergency.

**Laparoscopic Approaches:**
- TAPP (transabdominal preperitoneal): enters peritoneal cavity, places mesh in preperitoneal space.
- TEP (totally extraperitoneal): avoids peritoneal cavity; lower risk of intra-abdominal complications; requires carbon dioxide space.
- Preferred for bilateral hernias and recurrent inguinal hernias after prior open repair.

---

## Vascular Surgery

### Aortic Aneurysm

**Definitions:**
- Aortic aneurysm: dilation >1.5 times normal diameter. Normal aorta: 2 cm.
- Abdominal aortic aneurysm (AAA): aorta >3 cm diameter (clinical definition of aneurysm); >5.5 cm in males or >5.0 cm in females = repair threshold.
- Thoracic aortic aneurysm (TAA): ascending aorta >5.5 cm (repair threshold); descending thoracic >6 cm.

**AAA Surveillance:**
- 3.0-3.9 cm: repeat ultrasound every 3 years
- 4.0-4.9 cm: repeat ultrasound every 12 months
- 5.0-5.4 cm: repeat ultrasound every 6 months; vascular surgery referral
- 5.5 cm or symptomatic (pain, tenderness): repair

**Screening:** One-time abdominal ultrasound screening for male smokers aged 65-75 (USPSTF Grade B recommendation).

**Repair Options:**
- EVAR (endovascular aortic repair): stent graft deployed via femoral artery access; less physiologic stress; preferred in elderly, high operative risk, hostile abdomen.
- Open surgical repair: synthetic Dacron or PTFE graft; better long-term durability; preferred in young patients, anatomy not favorable for EVAR.
- EVAR vs. open: 30-day mortality lower with EVAR; long-term survival equivalent; EVAR requires life-long surveillance for endoleak.

**Ruptured AAA:** Mortality 40-50% operative (80-90% overall including pre-hospital deaths). Presents with triad: sudden severe back/flank pain, pulsatile abdominal mass, hypotension. Emergent repair (EVAR preferred if suitable anatomy).

#### Aortic Dissection

**Classification:**

| System | Type | Description | Treatment |
|--------|------|-------------|-----------|
| Stanford A | Involves ascending aorta (regardless of extent) | Surgical emergency — risk of pericardial tamponade, aortic regurgitation, coronary artery involvement, stroke | Emergency surgical repair (open) |
| Stanford B | Descending aorta only (does not involve ascending) | Medical management (anti-impulse therapy); TEVAR for complicated cases | IV labetalol/esmolol (HR target 60-70) + nitroprusside if needed (target SBP 100-120 mmHg) |
| DeBakey I | From ascending through aortic arch and descending | Surgical | As above |
| DeBakey II | Ascending only | Surgical | As above |
| DeBakey III | Descending only | Medical ± TEVAR | As above |

**Complicated Type B Dissection (TEVAR indicated):**
- Malperfusion (end-organ ischemia)
- Refractory hypertension
- Progression of dissection
- Rapid expansion or aneurysmal dilation >6 cm
- Rupture or impending rupture

**Medical Management of Type B Dissection:**
- IV labetalol (beta-blocker): first-line anti-impulse therapy; reduces heart rate AND blood pressure.
- IV esmolol infusion: titratable; useful in critically ill.
- IV nitroprusside: vasodilator; use with beta-blocker (avoid reflex tachycardia).
- Target: SBP 100-120 mmHg, HR 60 bpm.

---

### Peripheral Vascular Disease

#### Ankle-Brachial Index (ABI)

The ABI is the ratio of systolic blood pressure in the ankle (posterior tibial or dorsalis pedis) to the highest brachial systolic blood pressure.

| ABI | Interpretation |
|-----|---------------|
| >1.3 | Non-compressible vessels (calcification — diabetes, CKD); falsely elevated; duplex ultrasound or toe-brachial index required |
| 0.91-1.30 | Normal |
| 0.70-0.90 | Mild PAD; usually asymptomatic or mild claudication |
| 0.41-0.69 | Moderate PAD; claudication with short walking distances |
| <0.40 | Severe PAD; critical limb ischemia; rest pain, ulceration, gangrene |

**Toe-Brachial Index (TBI):** Measured with photoplethysmography; normal >0.7; not affected by calcification; preferred in diabetics and renal failure patients.

#### Fontaine Classification of PAD

| Stage | Description | Clinical Features |
|-------|-------------|------------------|
| I | Asymptomatic | Abnormal hemodynamics but no symptoms |
| IIa | Mild claudication | Walking distance >200 meters before pain |
| IIb | Moderate-severe claudication | Walking distance <200 meters before pain |
| III | Ischemic rest pain | Nocturnal foot pain, relieved by dependency |
| IV | Ulceration or gangrene | Tissue loss; critical limb-threatening ischemia (CLTI) |

**Treatment:**
- Stage I-IIa: cardiovascular risk factor modification (smoking cessation, statin, antiplatelet), structured exercise program.
- Stage IIb: above plus cilostazol (phosphodiesterase-3 inhibitor; improves claudication distance); avoid in heart failure.
- Stage III-IV (CLTI): revascularization (endovascular PTA/stenting or surgical bypass); wound care; amputation if not revascularizable.

#### Acute Limb Ischemia

Life- and limb-threatening emergency. Time to revascularization ideally within 6 hours (irreversible injury after 6 hours).

**The 6 P's:**
1. Pain (severe, out of proportion)
2. Pallor (white/mottled skin)
3. Pulselessness (absent Doppler signals)
4. Paresthesia (impending nerve ischemia)
5. Paralysis (severe ischemia — motor deficit is late finding; indicates severe ischemia)
6. Poikilothermia (coolness to touch)

**Embolism vs. Thrombosis:**

| Feature | Embolism | Thrombosis |
|---------|----------|-----------|
| Onset | Sudden, acute | Progressive (known PAD background) |
| Prior claudication | Absent | Usually present |
| Source | AF, MI, valvular heart disease | In situ atherosclerosis |
| Contralateral pulses | Normal | Reduced (bilateral PAD) |
| Angiogram | Sharp cut-off, skip lesions | Diffuse disease, collaterals |

**Treatment:**
- Embolism: embolectomy (Fogarty balloon catheter — surgical) + systemic anticoagulation.
- Thrombosis: catheter-directed thrombolysis (tPA via angiography catheter into clot); surgical bypass if thrombolysis fails or contraindicated.
- Compartment syndrome post-revascularization: reperfusion injury → fasciotomy.

---

## Orthopedic Surgery

### Fracture Management Principles

#### AO (Arbeitsgemeinschaft fur Osteosynthesefragen) Classification

The AO classification system categorizes fractures by location and morphology. The format is bone.segment.type.group.subgroup.

**Fracture Types:**
- Type A: Extra-articular (simplest)
- Type B: Partial articular involvement
- Type C: Complete articular involvement (most complex)

**Basic Fracture Morphology:**
- Transverse: perpendicular to bone axis; high-energy or fatigue
- Oblique: angled; common with torsional forces
- Spiral: rotational force; classic "toddler's fracture" in young children (also sign of abuse)
- Comminuted: multiple fragments; high-energy
- Segmental: two separate fracture lines isolating a "floating" segment
- Impacted: fragments driven together; axial loading
- Avulsion: tendon or ligament pulls off bony attachment

**ORIF Indications (Open Reduction Internal Fixation):**
- Articular fractures (>2 mm displacement) — restore congruity to prevent post-traumatic arthritis
- Displaced fractures with unacceptable alignment (angulation, shortening, rotation)
- Open fractures
- Fractures with neurovascular compromise
- Pathologic fractures (bone metastases)
- Fractures that cannot be maintained in cast/splint (unstable)
- Multiple trauma patients requiring early mobilization (damage control orthopaedics)

#### Open Fractures — Gustilo-Anderson Classification

| Grade | Wound | Bone Injury | Contamination | Treatment Notes |
|-------|-------|-------------|---------------|----------------|
| Type I | <1 cm, clean | Low-energy | Minimal | Cefazolin; I&D; primary closure or delayed primary closure |
| Type II | 1-10 cm | Moderate energy | Moderate | Cefazolin + (aminoglycoside if farmyard); I&D; delayed closure |
| Type IIIa | >10 cm; adequate soft tissue coverage | High energy | Heavy contamination | Cefazolin + aminoglycoside; I&D; flap usually not needed |
| Type IIIb | >10 cm; periosteal stripping; inadequate soft tissue | Extensive bone exposure | Severe | Cefazolin + aminoglycoside; plastic surgery for soft tissue coverage (flap) |
| Type IIIc | Any size; associated arterial injury requiring repair | — | — | Add penicillin G (clostridial); vascular surgery required; high amputation rate |

**Penicillin G:** Added in highly contaminated wounds or agricultural injuries for clostridial (gas gangrene) coverage.

**Timing of I&D (Irrigation and Debridement):**
- Classic teaching: within 6-8 hours.
- Current evidence: within 24 hours adequate if early antibiotics administered; however, earlier remains standard for Grade III injuries.
- Irrigation: copious normal saline (3-9 liters); pulsatile lavage debated.

#### Hip Fractures

**Epidemiology:** Most common orthopedic surgical emergency in the elderly. Mortality 20-30% at 1 year.

**Garden Classification (Femoral Neck Fractures):**

| Garden Stage | Description | Displacement | Treatment |
|-------------|-------------|-------------|-----------|
| I | Incomplete/valgus impacted | None (impacted) | ORIF (cannulated screws) — usually |
| II | Complete, non-displaced | None | ORIF (cannulated screws) |
| III | Complete, partial displacement | Partial | Arthroplasty (hemiarthroplasty or THA) |
| IV | Complete, full displacement | Complete | Arthroplasty — high avascular necrosis risk if ORIF |

**Femoral Neck vs. Intertrochanteric:**
- Femoral neck fractures: intracapsular; risk of avascular necrosis (disrupted blood supply to femoral head); displaced = arthroplasty.
- Intertrochanteric fractures: extracapsular; blood supply usually preserved; ORIF with sliding hip screw (cephalomedullary nail for unstable patterns).

**Early Surgery (<48 hours):** Associated with reduced mortality, lower complication rates (pneumonia, DVT, pressure ulcer, delirium), and shorter hospital stay. Delay beyond 48h associated with significantly increased 30-day mortality.

**VTE Prophylaxis:** Mandatory; LMWH or aspirin; extended prophylaxis for 35 days post-hip fracture surgery.

---

### Compartment Syndrome

**Definition:** Elevated pressure within a closed fascial compartment compromising perfusion to muscles and nerves within that compartment.

**Causes:**
- Fractures (tibia, forearm most common)
- Crush injuries
- Reperfusion after acute limb ischemia
- Prolonged external compression
- Burns
- Excessive fluid resuscitation (abdominal compartment syndrome)
- Tight cast or splint

**Classic Presentation — 6 P's:**
- Pain (especially with passive stretch of muscles within the compartment — most sensitive early sign)
- Pressure (tense, woody compartment on palpation)
- Paresthesia (tingling, numbness — nerve ischemia)
- Paralysis (late — muscle ischemia)
- Pallor
- Pulselessness (late, poor prognostic sign)

**Diagnosis:**
- Clinical diagnosis first in awake, cooperative patients.
- Compartment pressure measurement: Stryker device or arterial line transducer.
- Fasciotomy indicated when:
  - Measured compartment pressure ≥30 mmHg (absolute pressure threshold), OR
  - Delta P ≤30 mmHg (diastolic blood pressure minus compartment pressure ≤30 mmHg — more physiologic threshold, accounts for perfusion pressure)

**Fasciotomy:**
- Must release all affected compartments.
- Leg: 4 compartments (anterior, lateral, superficial posterior, deep posterior) — two-incision technique.
- Forearm: 2 compartments (volar, dorsal) — volar incision extending to carpal tunnel most important.
- Leave wounds open; delayed primary closure or skin grafting at 48-72h.

**Complications of Missed Compartment Syndrome:**
- Volkmann's ischemic contracture (forearm)
- Permanent neurologic deficit
- Myonecrosis and rhabdomyolysis
- Renal failure (myoglobinuria)

---

### Spine Surgery Essentials

#### Cervical Spine Clearance

**NEXUS Criteria (can clear without imaging if ALL of the following):**
1. No posterior midline cervical spine tenderness
2. No evidence of intoxication
3. Normal level of alertness
4. No focal neurologic deficit
5. No painful distracting injury

If any NEXUS criterion fails: obtain imaging.

**Canadian C-Spine Rule:** More specific for high-risk injuries in alert, stable patients. Considers high-risk factors (age >65, dangerous mechanism, paresthesia in extremities), low-risk factors, and ability to actively rotate neck 45° bilaterally.

#### ASIA Impairment Scale (Spinal Cord Injury)

| Grade | Classification | Definition |
|-------|---------------|------------|
| A | Complete | No sensory or motor function below the neurological level, including S4-S5 |
| B | Sensory Incomplete | Sensory but not motor function preserved below neurological level including S4-S5 |
| C | Motor Incomplete | Motor function preserved below neurological level; more than half key muscles below NLI have muscle grade <3 |
| D | Motor Incomplete | Motor function preserved below neurological level; at least half key muscles below NLI have muscle grade ≥3 |
| E | Normal | Sensory and motor functions are normal; may have reflex changes |

#### Cauda Equina Syndrome

**Definition:** Compression of the cauda equina (lumbosacral nerve roots below L1-L2) causing:
- Saddle anesthesia (perineum, perianal, and inner thigh numbness)
- Bowel dysfunction (constipation, fecal incontinence)
- Bladder dysfunction (urinary retention most common, overflow incontinence)
- Bilateral or unilateral lower extremity weakness and sensory loss
- Areflexia (lower motor neuron injury)

**Etiology:** Massive central disc herniation (most common), epidural hematoma, epidural abscess, spinal stenosis, tumor, trauma.

**Diagnosis:** MRI lumbar spine — emergent.

**Treatment:** Emergency surgical decompression (laminectomy). Best outcomes when decompressed within 24-48 hours of onset. Delays beyond 48 hours associated with permanent bowel, bladder, and sexual dysfunction.

---

## Critical Care Surgery

### ARDS — Acute Respiratory Distress Syndrome

#### Berlin Definition (2012)

**Diagnostic Criteria (all required):**
1. Onset: within 1 week of known clinical insult or new/worsening respiratory symptoms
2. Chest X-ray or CT: bilateral opacities not fully explained by effusions, lobar/lung collapse, or nodules
3. Edema: respiratory failure not fully explained by cardiac failure or fluid overload (if no risk factor for ARDS, echocardiography required)
4. Oxygenation impairment (PaO2/FiO2 measured with PEEP ≥5 cmH2O)

| Severity | PaO2/FiO2 Ratio | Mortality |
|---------|----------------|----------|
| Mild | 200-300 mmHg | ~27% |
| Moderate | 100-200 mmHg | ~32% |
| Severe | <100 mmHg | ~45% |

**Common Causes of ARDS:**
- Pulmonary (direct): pneumonia (bacterial, viral), aspiration, near-drowning, pulmonary contusion, inhalation injury
- Extrapulmonary (indirect): sepsis (most common), massive transfusion, pancreatitis, trauma, burns, drug overdose (heroin, salicylates, cocaine)

#### Lung-Protective Ventilation Strategy (ARDSNet Protocol)

| Parameter | Target | Rationale |
|-----------|--------|-----------|
| Tidal Volume (TV) | 6 mL/kg of ideal body weight (IBW) | Prevents volutrauma (overdistension of alveoli) |
| Plateau Pressure (Pplat) | ≤30 cmH2O | Prevents barotrauma and ventilator-induced lung injury (VILI) |
| PEEP | Titrate per PEEP-FiO2 table (minimum 5 cmH2O; higher in severe) | Prevents cyclic atelectrauma; improves oxygenation |
| FiO2 | Minimum to achieve SpO2 88-95% | Prevents oxygen toxicity |
| pH target | 7.30-7.45 | Permissive hypercapnia accepted (7.25-7.30) |
| SpO2 target | 88-95% | Permissive hypoxemia; prevents oxygen toxicity |

**IBW Calculation:**
- Males: 50 + 2.3 × (height in inches - 60)
- Females: 45.5 + 2.3 × (height in inches - 60)

**Advanced Strategies for Refractory ARDS:**

| Intervention | Indication | Effect |
|-------------|-----------|--------|
| Prone positioning | Severe ARDS (PaO2/FiO2 <150); recommended >16 hours/day | Reduces mortality (PROSEVA trial: 28-day mortality 16% vs 33%) |
| Neuromuscular blockade (cisatracurium) | PaO2/FiO2 <150 in first 48h | Reduces barotrauma, systemic inflammation (ACURASYS trial); ventilator synchrony; ROSE trial (2019) questions benefit — sedation-first approach now debated |
| Inhaled pulmonary vasodilators (iNO, epoprostenol) | Rescue therapy for severe refractory hypoxemia | Improves V/Q mismatch; no mortality benefit |
| ECMO (venovenous) | Ultra-refractory ARDS (EOLIA criteria: PaO2/FiO2 <50 for >3h; PaO2/FiO2 <80 for >6h; pH <7.25 with pCO2 ≥60 for >6h despite maximal conventional therapy) | EOLIA trial: no significant 60-day mortality difference; many crossovers; still considered rescue |

---

### Abdominal Compartment Syndrome

**Definitions (WSACS — World Society of the Abdominal Compartment Syndrome):**
- Intra-abdominal pressure (IAP): normal <5-7 mmHg; measured via bladder catheter (transduction technique, 25 mL saline instillation, midaxillary line reference, end-expiration).
- Intra-abdominal hypertension (IAH): IAP ≥12 mmHg on repeated measurements.
- Abdominal compartment syndrome (ACS): IAP >20 mmHg (sustained) PLUS at least one new organ dysfunction attributable to elevated IAP.

**Causes:**
- Massive fluid resuscitation (damage control resuscitation, burns)
- Ileus, bowel obstruction
- Retroperitoneal hematoma
- Ascites (rapid accumulation)
- Primary: peritonitis, intra-abdominal hemorrhage
- Secondary: extra-abdominal cause (sepsis, large-volume resuscitation)

**Organ Dysfunction in ACS:**
- Cardiovascular: decreased venous return (IVC compression) → decreased cardiac output; increased SVR
- Respiratory: diaphragm elevation → increased airway pressure → ARDS
- Renal: renal vein compression + decreased perfusion → oliguria, AKI (oliguria begins at IAP >15-20)
- Hepatic: hepatic blood flow reduction → hepatic dysfunction
- CNS: elevated ICP (transmission of intra-abdominal pressure)
- Mesenteric: bowel ischemia from mesenteric vein compression and reduced perfusion

**Treatment:**
1. Non-surgical measures (for IAH, not ACS):
   - NGT decompression
   - Rectal tube, enemas for colonic decompression
   - Diuretics or dialysis for fluid removal
   - Neuromuscular blockade (relaxes abdominal wall)
   - Avoid elevated HOB >30° if possible
2. Decompressive laparotomy: indicated for ACS (IAP >20 + organ dysfunction). Immediate reduction of IAP, open abdomen management.
3. Open abdomen management: temporary abdominal closure (TAC) with Bogota bag, Wittmann Patch, or NPWT system (ABThera/KCI). Goal: fascial closure within 5-7 days.

---

### Damage Control Surgery

Damage control surgery (DCS) is a staged surgical strategy for the management of life-threatening injuries or emergency surgical conditions in physiologically depleted patients. Prioritizes survival over anatomic repair.

**Indications (Lethal Triad: Hypothermia + Acidosis + Coagulopathy):**
- Core temperature <35°C (hypothermia)
- pH <7.2 (metabolic acidosis)
- INR >1.5 / coagulopathy
- Massive transfusion requirement
- Inability to achieve hemostasis despite conventional measures
- Injury exceeding surgeon's capacity for definitive repair in unstable patient

**DCS Phases:**

| Phase | Location | Goals |
|-------|----------|-------|
| Phase 0 (Permissive hypotension) | Pre-hospital/ED | Limit crystalloid; target SBP 80-90; tourniquet; blood products |
| Phase I (Abbreviated laparotomy) | OR | Control hemorrhage (packing, clamping, temporary shunts); control contamination (staple, ligate bowel); temporary abdominal closure |
| Phase II (ICU resuscitation) | ICU | Warm patient; correct coagulopathy; restore perfusion; NPWT for open abdomen |
| Phase III (Definitive repair) | OR | Re-explore at 24-72h; remove packing; definitive bowel/vascular repair; fascial closure |
| Phase IV (Reconstruction) | OR (delayed) | Ostomy reversal; hernia repair; late reconstruction |

**Balanced Resuscitation:**
- 1:1:1 ratio of pRBC:FFP:platelets from the outset.
- Tranexamic acid (TXA) 1g IV within 3 hours of injury (CRASH-2 trial): reduces mortality from hemorrhage.
- Cryoprecipitate if fibrinogen <150 mg/dL.
- Calcium chloride to replace calcium lost in citrated blood products.
- Avoid crystalloid excess (dilutes clotting factors, causes hypothermia).

---

## Postoperative Complications

### The 5 W's of Postoperative Fever

Postoperative fever is defined as temperature >38.5°C (101.3°F) on two consecutive readings at least 4 hours apart. The "5 W's" mnemonic provides a systematic diagnostic framework organized by timing.

| W | Complication | Typical POD | Mechanism / Diagnosis |
|---|-------------|-------------|----------------------|
| Wind | Atelectasis / Pneumonia | POD 1-2 (atelectasis), POD 3-5 (pneumonia) | Atelectasis: microatelectasis from splinting; treat with incentive spirometry, ambulation, CPAP. Pneumonia: aspiration or VAP; chest X-ray, sputum culture |
| Water | Urinary tract infection | POD 3-5 | Indwelling urinary catheter; urinalysis + culture; remove catheter ASAP |
| Wound | Surgical site infection | POD 5-7 | Erythema, warmth, induration, purulence; open wound, culture, antibiotics |
| Walking | DVT / Pulmonary embolism | POD 5+ (any postoperative time) | Venous thromboembolism; Doppler ultrasound (DVT), CT-PA (PE); anticoagulate |
| Wonder drugs | Drug fever / C. difficile | Any time | Drug reaction (beta-lactams, heparin, phenytoin); C. diff (abdominal pain, diarrhea, high WBC); check stool PCR |

**Additional causes not in classic mnemonic:**
- Blood transfusion reaction (during/after transfusion)
- Pancreatitis (POD 3-5 after biliary or pancreatic surgery)
- Anastomotic leak (POD 5-7; fever + tachycardia + abdominal pain)
- Deep vein septic thrombophlebitis (persistent fever despite antibiotics)
- Malignant hyperthermia (intraoperative)

---

### VTE Prophylaxis

**Mechanical Prophylaxis:**
- Sequential compression devices (SCDs): applied to bilateral lower extremities before anesthetic induction; maintained until ambulatory.
- Graduated compression stockings (TED stockings): less effective than SCDs; used adjunctively.

**Pharmacologic Prophylaxis:**

| Agent | Dose | Indication |
|-------|------|-----------|
| Enoxaparin (Lovenox) | 40 mg SQ daily (standard risk) | General surgery, medical patients; start 12-24h postop |
| Enoxaparin (Lovenox) high-risk | 30 mg SQ BID | Major orthopedic surgery (hip/knee replacement) |
| Unfractionated Heparin (UFH) | 5,000 units SQ TID or BID | Renal failure (preferred over LMWH when CrCl <30) |
| Fondaparinux | 2.5 mg SQ daily | Hip/knee surgery; heparin allergy |
| Aspirin | 81-325 mg daily | Hip/knee arthroplasty (may be used alone in low-risk or as adjunct) |
| Rivaroxaban (Xarelto) | 10 mg PO daily | Total hip/knee arthroplasty |

**Extended VTE Prophylaxis:**
- Major abdominal cancer surgery: LMWH for 28 days postoperatively (ENOXACAN II trial; significant reduction in VTE without increased bleeding).
- Total hip replacement: 28-35 days of anticoagulation.
- Total knee replacement: 10-14 days minimum.

---

### Anastomotic Leak

Anastomotic leak is a communication between the intra-luminal bowel content and the peritoneal cavity (or adjacent space) due to failure of surgical anastomosis. One of the most feared postoperative complications.

**Risk Factors:**
- Distal rectal anastomosis (stapled low anterior resection — highest risk, up to 15-20%)
- Preoperative radiation
- Diabetes
- Malnutrition
- Immunosuppression
- Ischemia of anastomotic ends
- Tension on anastomosis
- Absence of diverting stoma
- Emergency surgery

**Clinical Presentation:**
- Fever and leukocytosis (especially after day 4-5 when initial postoperative fever should be resolving)
- Tachycardia out of proportion
- Abdominal pain and peritoneal signs
- High drain amylase (from small bowel leak) or bile/intestinal content in drain
- Paradoxically, "improving" pain followed by sudden deterioration

**Diagnosis:**
- CT abdomen/pelvis with IV + rectal/oral contrast: most sensitive (free air after expected resolution, pericolic fluid, extraluminal contrast, abscess)
- Water-soluble contrast enema: if CT equivocal

**Management:**

| Severity | Management |
|---------|-----------|
| Minor (contained, no peritonitis) | NPO, IV antibiotics, CT-guided percutaneous drain, bowel rest; may avoid re-operation |
| Moderate (pelvic/loculated abscess) | Percutaneous or endoluminal drainage; IV antibiotics; proximal diversion (stoma) |
| Major (diffuse peritonitis, hemodynamic instability) | Emergency re-operation: washout, drainage, takedown of anastomosis with Hartmann's procedure (end colostomy) |

---

### Ileus vs. Postoperative Small Bowel Obstruction

| Feature | Postoperative Ileus | Early SBO (POD 3-5) |
|---------|--------------------|--------------------|
| Timing | POD 0-3 (expected) | POD 3-10 |
| Bowel sounds | Absent or minimal | May be high-pitched/tinkling |
| Nausea/vomiting | Present | Present |
| Distension | Diffuse | May be more localized |
| CT scan | Dilated small and large bowel without transition point | Transition point; dilated small bowel with decompressed colon |
| Management | NGT, NPO, early ambulation, gum chewing (stimulates vagal motility), alvimopan for post-surgical ileus | NGT, NPO; surgical evaluation; may require re-operation |

**Prolonged Ileus Risk Factors:** Opioids, hypokalemia, hypomagnesemia, peritoneal contamination, intra-abdominal hematoma, prolonged surgery, retroperitoneal dissection.

---

### Postoperative Complications by Specialty

#### Biliary Surgery — Bile Leak Post-Cholecystectomy

- Incidence: 0.3-2% after laparoscopic cholecystectomy
- Sources: cystic duct stump blowout, duct of Luschka (minor bile ducts from liver bed), major bile duct injury
- Diagnosis: elevated drain bilirubin (drain:serum bilirubin ratio >3), CT, HIDA scan, ERCP
- Management: ERCP with sphincterotomy ± biliary stent (most effective for cystic duct stump); image-guided drainage of bile collections

**Bile Duct Injury:**
- Major injury: complete transection or excision of CBD; requires hepaticojejunostomy (biliary-enteric anastomosis); hepatobiliary surgeon
- Masquerade: right hepatic duct clipped as cystic duct; jaundice POD 2-5

#### Thyroid and Parathyroid Surgery — Recurrent Laryngeal Nerve Injury

- RLN runs in the tracheoesophageal groove; at risk in total thyroidectomy, parathyroidectomy, neck dissection
- Unilateral injury: hoarseness, voice change; majority recover within 6 months
- Bilateral injury: stridor, respiratory distress; may require tracheostomy (emergency)
- Prevention: intraoperative nerve monitoring (IONM)
- Superior laryngeal nerve injury (external branch): loss of high-pitched voice (singers/vocalists)

**Post-Thyroidectomy Hypocalcemia:**
- Cause: transient or permanent hypoparathyroidism (inadvertent parathyroid gland removal or devascularization)
- Symptoms: perioral tingling, fingertip numbness, Chvostek's sign (facial twitching with tapping CN VII), Trousseau's sign (carpal spasm with BP cuff inflation), tetany, laryngospasm
- Timing: 24-72h post-thyroidectomy
- Management: oral calcium + vitamin D (calcitriol) for transient; IV calcium gluconate for symptomatic/severe; check PTH and ionized calcium

#### Pelvic Surgery — Ureteral Injury

- Most common cause of ureteral injury: inadvertent ligation or transection during hysterectomy, colon resection, or retroperitoneal dissection
- At-risk zones: crossing of ureter under uterine artery, ureterovesical junction, pelvic brim
- Delayed diagnosis: flank pain, hydronephrosis, fistula (vesicovaginal, ureterovaginal), elevated creatinine from urinoma
- Diagnosis: CT urogram, retrograde pyelogram
- Management: early injury (intraoperative recognition) — primary repair or reanastomosis; delayed diagnosis — nephrostomy tube (to protect kidney) + delayed repair

---

## Oncologic Surgery Principles

### Staging and Resection

**TNM Staging System:**
- T (Tumor): describes primary tumor size and local invasion (T1-T4, Tis for in situ)
- N (Nodes): regional lymph node involvement (N0-N3)
- M (Metastasis): distant metastasis (M0 = absent, M1 = present)
- Stage groups: I through IV (IV = distant metastasis in most cancers)

**Resection Margin Classification:**

| Classification | Definition | Clinical Significance |
|---------------|------------|----------------------|
| R0 | Complete resection; microscopically negative margins | Goal of curative intent surgery; best prognosis |
| R1 | Microscopic residual tumor at margin | Increased local recurrence; adjuvant therapy often indicated |
| R2 | Macroscopic residual tumor; gross residual at margin or unresected deposits | Palliative resection; poor prognosis; systemic therapy primary |

---

### Sentinel Lymph Node Biopsy

**Principle:** The sentinel lymph node (SLN) is the first lymph node to receive drainage from a tumor. If negative, the remaining regional nodes are presumed negative, sparing the patient full regional node dissection.

**Technique:**
- Inject radiolabeled technetium-99m sulfur colloid (day before or day of surgery) and/or blue dye (isosulfan blue or methylene blue) perilesionally.
- Intraoperative gamma probe (for radiotracer) and direct visualization (blue dye) to identify SLN.
- Send for frozen section or permanent histopathology.

**Indications:**
- Melanoma (>1 mm depth or <1mm with ulceration/high mitotic rate): SLN biopsy recommended if SLN negative, spares elective regional lymph node dissection.
- Breast cancer (clinically node-negative): SLN biopsy; if negative, avoids full axillary lymph node dissection (ALND); reduces lymphedema, nerve injury.

---

### Colorectal Cancer Surgery

**Right-Sided (Cecum, Ascending Colon, Hepatic Flexure):** Right hemicolectomy — resect from terminal ileum to mid-transverse colon; ileocolic anastomosis.

**Left-Sided (Splenic Flexure, Descending, Sigmoid):** Left hemicolectomy or sigmoid colectomy; colorectal anastomosis.

**Rectal Cancer:**
- Total mesorectal excision (TME): complete sharp dissection of the entire mesorectal envelope under direct vision; reduces local recurrence from 30% to <10%.
- Low anterior resection (LAR): TME + colorectal or coloanal anastomosis for mid/upper rectal cancers.
- Abdominoperineal resection (APR): for low rectal cancers within 1-2 cm of sphincter complex; permanent end colostomy.
- Diverting loop ileostomy: protects low anastomoses.
- Neoadjuvant therapy: long-course chemoradiation (5-FU + 45-50 Gy) or short-course radiation (25 Gy over 5 days) prior to surgery for stage II-III rectal cancers.

---

### Breast Cancer Surgery

**Early-Stage Breast Cancer (Stage I-II):**
- Lumpectomy (breast-conserving surgery, BCS) + whole breast radiation = mastectomy in terms of overall survival (Fisher NSABP B-06 trial and multiple meta-analyses).
- Mastectomy: simple (skin-sparing, nipple-sparing options available) or modified radical mastectomy (MRM — includes axillary lymph node dissection).
- Reconstruction: immediate or delayed; tissue expander/implant or autologous flap (TRAM, DIEP, latissimus dorsi).

**Axillary Staging:**
- SLN biopsy (Z0011 trial): 1-2 positive SLNs in patients undergoing BCS + adjuvant radiation → no need for ALND.
- ALND: indicated for 3 or more positive SLNs, SLN biopsy positive in patients undergoing mastectomy without radiation.

**BRCA Mutations:**
- BRCA1/2: high lifetime breast cancer risk (up to 70-85%); bilateral prophylactic mastectomy reduces risk by >90%.
- Risk-reducing bilateral salpingo-oophorectomy: reduces ovarian cancer risk and breast cancer risk (pre-menopausal women).

---

### Enhanced Recovery After Surgery (ERAS)

ERAS protocols are multimodal, evidence-based perioperative care pathways designed to attenuate the surgical stress response, preserve physiologic function, and accelerate recovery.

**Core ERAS Elements:**

| Phase | Intervention |
|-------|-------------|
| Preoperative | Preoperative counseling and patient education; carbohydrate loading (maltodextrin drink 400 mL up to 2h before surgery); optimize nutrition; prehabilitation (exercise); screen for anemia/nutritional deficiency; avoid prolonged fasting; multimodal premedication (acetaminophen, celecoxib, gabapentin, antacid) |
| Intraoperative | Goal-directed fluid therapy; normothermia (forced air warming, warm IV fluids); TIVA or minimally invasive technique; avoid excessive crystalloid; drains/tubes only when necessary; multimodal analgesia (neuraxial, regional blocks) |
| Postoperative | Early oral nutrition (POD 0 or 1); early removal of urinary catheter (POD 1-2); early ambulation (POD 0-1); multimodal analgesia (minimize opioids — scheduled acetaminophen + NSAIDs + regional blocks); no routine nasogastric tubes; stimulate GI motility (gum, coffee, alvimopan) |

**Outcomes with ERAS:**
- 30-50% reduction in length of hospital stay
- 30-50% reduction in complications (ileus, SSI, VTE, pulmonary)
- Faster return of bowel function
- Reduced opioid consumption
- Equivalent or lower readmission rates

**Multimodal Analgesia — Opioid-Sparing Regimen:**
- Scheduled acetaminophen (1g PO/IV Q6-8h) as foundation.
- Scheduled NSAID (ketorolac IV or ibuprofen PO) — avoid in renal failure, platelet dysfunction, high bleeding risk.
- Gabapentin/pregabalin: reduces opioid requirements by 30-50%.
- Neuraxial analgesia (epidural or intrathecal morphine): gold standard for thoracic and major abdominal procedures.
- Regional blocks: transversus abdominis plane (TAP) block, erector spinae plane block, quadratus lumborum block for abdominal pain.
- PCIA (patient-controlled IV analgesia) with opioids as rescue only.

---

## Quick Reference Tables

### Common Intraoperative Drug Doses

| Drug | Dose | Indication |
|------|------|-----------|
| Propofol | 1.5-2.5 mg/kg IV | Induction |
| Etomidate | 0.2-0.3 mg/kg IV | Induction (hemodynamic instability) |
| Ketamine | 1-2 mg/kg IV | Induction (shock, asthma) |
| Succinylcholine | 1.5 mg/kg IV | RSI depolarizing NMB |
| Rocuronium | 0.6 mg/kg (intubating); 1.2 mg/kg (RSI) | Non-depolarizing NMB |
| Sugammadex | 2 mg/kg (routine reversal); 16 mg/kg (emergency reversal of 1.2 mg/kg rocuronium) | Rocuronium/vecuronium reversal |
| Neostigmine | 0.04-0.07 mg/kg + glycopyrrolate | NMB reversal (non-depolarizing) |
| Dantrolene | 2.5 mg/kg IV bolus; repeat up to 10 mg/kg | Malignant hyperthermia |
| Epinephrine | 0.01 mg/kg IV (1:10,000); 0.01 mg/kg IM (1:1,000) | Anaphylaxis, cardiac arrest |
| Vasopressin | 0.03-0.04 units/min infusion (septic shock); 40 units IV bolus (cardiac arrest) | Vasopressor |
| Norepinephrine | 0.01-3 mcg/kg/min infusion | First-line vasopressor for septic shock |
| Phenylephrine | 50-200 mcg IV bolus; 0.1-0.5 mcg/kg/min infusion | Hypotension (pure alpha agonist) |
| Ephedrine | 5-25 mg IV bolus | Intraoperative hypotension (especially spinal) |
| Atropine | 0.01-0.02 mg/kg IV (min 0.1 mg) | Bradycardia |

### Perioperative Lab Values Requiring Action

| Lab Value | Threshold | Action |
|-----------|-----------|--------|
| Hemoglobin | <8 g/dL preop | Consider transfusion or iron supplementation |
| Platelet count | <50,000 | Platelet transfusion for surgical hemostasis |
| INR | >1.5 for surgery | Delay; vitamin K or FFP/PCC |
| Serum potassium | >5.5 mEq/L | Postpone elective surgery; treat |
| Serum potassium | <3.0 mEq/L | Correct before elective surgery (arrhythmia risk) |
| Serum sodium | <125 mEq/L (symptomatic) | Correct; assess for SIADH vs hypovolemia |
| Blood glucose | >250 mg/dL | Delay elective surgery; insulin protocol |
| Albumin | <2.5 g/dL | Nutritional optimization before elective surgery |
| Creatinine (acute rise) | >50% from baseline | Nephrology consult; adjust drug dosing |

---

*End of Surgical Medicine Knowledge Base*
*Total coverage: Preoperative assessment, anesthesia, fluid management, wound care, abdominal surgery, vascular surgery, orthopedic surgery, critical care surgery, postoperative complications, oncologic surgery principles, and ERAS protocols.*
