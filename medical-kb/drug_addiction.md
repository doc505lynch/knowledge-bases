# Drug Addiction: Clinical Reference Knowledge Base

> Domain: Addiction Medicine / Substance Use Disorders
> Intended use: Open WebUI RAG system (chunk size 1500, overlap 200, Top K 5)
> Sources: DSM-5, ASAM guidelines, SAMHSA TIPs, FDA labeling, peer-reviewed literature

---

## General Framework

### Defining Substance Use Disorder

Substance Use Disorder (SUD) is defined in the DSM-5 as a cluster of cognitive, behavioral, and physiological symptoms indicating that an individual continues using a substance despite significant substance-related problems. The diagnosis is made when at least 2 of 11 criteria are met within a 12-month period.

#### DSM-5 SUD Criteria (11 Items)

The 11 criteria span four domains: impaired control, social impairment, risky use, and pharmacological criteria.

**Impaired Control**
1. The substance is often taken in larger amounts or over a longer period than intended.
2. There is a persistent desire or unsuccessful efforts to cut down or control use.
3. A great deal of time is spent in activities necessary to obtain the substance, use it, or recover from its effects.
4. Craving, or a strong desire or urge to use the substance.

**Social Impairment**
5. Recurrent substance use resulting in a failure to fulfill major role obligations at work, school, or home.
6. Continued substance use despite having persistent or recurrent social or interpersonal problems caused or exacerbated by the effects of the substance.
7. Important social, occupational, or recreational activities are given up or reduced because of substance use.

**Risky Use**
8. Recurrent substance use in situations in which it is physically hazardous.
9. Substance use is continued despite knowledge of having a persistent or recurrent physical or psychological problem that is likely to have been caused or exacerbated by the substance.

**Pharmacological Criteria**
10. Tolerance — a need for markedly increased amounts to achieve intoxication or desired effect, or a markedly diminished effect with continued use of the same amount.
11. Withdrawal — the characteristic withdrawal syndrome for the substance, or the substance (or a closely related substance) is taken to relieve or avoid withdrawal symptoms.

#### Severity Specifiers

| Severity | Criteria Met | Clinical Significance |
|----------|-------------|----------------------|
| Mild | 2-3 | Early intervention strongly indicated |
| Moderate | 4-5 | Formal treatment recommended |
| Severe | 6 or more | Intensive or residential treatment typically required |

Note: The terms "dependence" and "abuse" from DSM-IV have been replaced by the single spectrum diagnosis of SUD. "In early remission" = no criteria 3-12 months; "in sustained remission" = no criteria 12+ months.

---

### SBIRT: Screening, Brief Intervention, and Referral to Treatment

SBIRT is a comprehensive, integrated, public health approach to the delivery of early intervention and treatment services for persons with risky substance use, and those with, or at risk of developing, substance use disorders.

#### Screening Tools

**AUDIT (Alcohol Use Disorders Identification Test)**
- 10 questions covering quantity, frequency, dependence, and harmful use
- Score range: 0-40
- Cutoffs: 8+ (men) = hazardous/harmful drinking; 4+ (women/elderly) = significant
- AUDIT-C (first 3 questions only): score 3+ in men, 2+ in women = positive screen

**CAGE Questionnaire**
- C — Have you ever felt you should Cut down on your drinking?
- A — Have people Annoyed you by criticizing your drinking?
- G — Have you ever felt Guilty about your drinking?
- E — Have you ever had a drink first thing in the morning as an Eye-opener?
- Scoring: 2+ positive responses = clinically significant; sensitivity 71-93% for alcohol dependence

**DAST-10 (Drug Abuse Screening Test)**
- 10 yes/no questions about drug use in past 12 months (excludes alcohol and tobacco)
- Score 0: no problem reported
- Score 1-2: low level, monitor
- Score 3-5: moderate, brief intervention
- Score 6-8: substantial, referral to treatment
- Score 9-10: severe, intensive treatment

**CRAFFT (Ages 12-21)**
- Car, Relax, Alone, Forget, Friends, Trouble
- 2+ positive = significant risk; widely used in adolescent primary care

#### Brief Intervention: FRAMES Model

| Component | Description |
|-----------|-------------|
| Feedback | Personalized feedback about screening results and risk |
| Responsibility | Emphasize personal responsibility for change |
| Advice | Clear advice to change behavior |
| Menu | Offer a menu of options for changing behavior |
| Empathy | Warm, reflective, empathic counseling style |
| Self-efficacy | Reinforce patient belief in ability to change |

A brief intervention is typically 5-15 minutes. It is effective for risky use that has not yet progressed to moderate or severe SUD. It is not a substitute for formal treatment in severe SUD.

#### Referral to Treatment

Criteria for referral include: moderate to severe SUD by DSM-5 criteria, failed brief intervention, co-occurring psychiatric disorder requiring integrated treatment, medical complications, history of severe withdrawal.

Levels of care follow ASAM criteria:
- Level 0.5: Early intervention
- Level 1: Outpatient treatment (less than 9 hours/week)
- Level 2.1: Intensive outpatient (9-19 hours/week)
- Level 2.5: Partial hospitalization (20+ hours/week)
- Level 3.1-3.7: Residential/inpatient treatment (varying medical management)
- Level 4: Medically managed intensive inpatient

---

### Biopsychosocial Model of Addiction

Addiction is not a moral failure or a matter of willpower. It is a chronic, relapsing brain disorder with biological, psychological, and social determinants.

#### Biological Factors
- Genetic heritability: approximately 40-60% of risk for alcohol use disorder; similar for opioid and stimulant use disorders
- Neuroadaptation: chronic exposure changes receptor density, signal transduction, and gene expression
- Co-occurring medical conditions: chronic pain, traumatic brain injury, hepatitis C, HIV
- Pharmacokinetics: rate of drug delivery to brain (IV > smoked > intranasal > oral) correlates with abuse potential

#### Psychological Factors
- Trauma and adverse childhood experiences (ACEs): dose-response relationship between ACE score and SUD risk
- Psychiatric comorbidity: depression, PTSD, anxiety, ADHD, bipolar disorder
- Coping style: maladaptive coping, emotion dysregulation, low distress tolerance
- Cognitive distortions: denial, minimization, justification
- Expectancy effects: beliefs about drug effects influence use patterns

#### Social Factors
- Peer influence: especially critical during adolescence
- Family environment: parenting style, family history of SUD, family conflict
- Socioeconomic status: poverty, unemployment, housing instability
- Access to treatment: geographic, financial, and systemic barriers
- Stigma: reduces help-seeking; contributes to delayed diagnosis
- Social isolation: recovery capital is heavily social

---

### Brain Reward Pathways

#### Mesolimbic Dopamine System

The mesolimbic dopamine pathway is the primary neural circuit underlying reinforcement learning and the acute rewarding effects of drugs. Dopaminergic neurons originate in the ventral tegmental area (VTA) and project to the nucleus accumbens (NAc), prefrontal cortex (PFC), amygdala, and hippocampus.

**Normal function:** Natural rewards (food, sex, social bonding) cause modest, phasic dopamine release in the NAc, signaling salience and motivating behavior.

**Drug effects:** Drugs of abuse cause supraphysiologic dopamine release — 2 to 10 times greater than natural rewards — and do so more rapidly. This intensity overwhelms normal homeostatic mechanisms.

#### Nucleus Accumbens (NAc)

The NAc is the primary convergence point for motivation, reward, and habit formation. It integrates input from:
- VTA (dopaminergic): reward signal
- Amygdala (glutamatergic): emotional memories and cue reactivity
- Hippocampus (glutamatergic): contextual memories
- Prefrontal cortex (glutamatergic): executive control and goal-directed behavior

In addiction, the NAc becomes hypersensitized to drug-associated cues and hyposensitized to natural rewards. This drives compulsive drug seeking even in the absence of acute pleasure.

#### Prefrontal Cortex (PFC) Dysregulation

The PFC governs executive function: impulse control, decision-making, delayed gratification, and inhibitory control over subcortical drives.

Chronic drug use causes:
- Reduced PFC gray matter volume (demonstrated in MRI studies)
- Decreased D2/D3 receptor availability in PFC
- Impaired inhibitory control over the NAc and amygdala
- Poor decision-making as measured by Iowa Gambling Task
- Increased impulsivity and risk-taking

This PFC hypofrontality is a core feature of addiction and explains why willpower-based approaches fail: the neural substrate of self-control is structurally and functionally compromised.

#### Neuroadaptation and Allostasis

With repeated drug use, the brain shifts from a liking/reward system to a wanting/craving system:
- Downregulation of dopamine receptors: chronic high dopamine causes receptor density reduction, blunting the reward response to both drugs and natural stimuli (anhedonia)
- Opponent process theory: the acute positive hedonic effect is followed by a negative emotional state (dysphoria, anxiety) as homeostasis reasserts — this "opponent process" intensifies with repeated use
- Allostatic load: the reward set-point shifts downward; the individual now uses drugs not for pleasure but to reach baseline function and avoid withdrawal/dysphoria
- Sensitization: the incentive salience of drug cues becomes sensitized (increases), while the rewarding effect of the drug itself decreases — explains why craving persists long after physical dependence resolves

---

## Opioid Use Disorder

### Epidemiology

The opioid epidemic in the United States has occurred in three overlapping waves:
- Wave 1 (1990s-2010): prescription opioid overprescribing
- Wave 2 (2010-2013): heroin, as prescription supply tightened
- Wave 3 (2013-present): illicitly manufactured fentanyl (IMF) and analogs

As of the early 2020s, more than 75% of opioid overdose deaths involve synthetic opioids. Opioid use disorder affects approximately 2.7 million Americans.

---

### Pharmacology and Potency

Opioid potency is expressed as morphine milligram equivalents (MME), which standardizes dosing comparisons across opioids.

#### Morphine Milligram Equivalent (MME) Conversion Table

| Opioid | Oral MME Conversion Factor | Notes |
|--------|---------------------------|-------|
| Morphine (oral) | 1x (reference) | Standard reference opioid |
| Codeine (oral) | 0.15x | Prodrug; requires CYP2D6 conversion |
| Hydrocodone (oral) | 1x | Equivalent to morphine mg for mg |
| Oxycodone (oral) | 1.5x | More bioavailable than morphine |
| Oxymorphone (oral) | 3x | High potency; significant abuse |
| Hydromorphone (oral) | 4x (oral), 20x (IV) | Dilaudid; high overdose risk |
| Methadone (oral) | Variable 3-10x | Increases with dose; complex pharmacokinetics |
| Fentanyl (transdermal) | 2.4 per mcg/h patch | E.g., 25mcg/h patch = 60 MME/day |
| Fentanyl (IV/IMF) | 100x (oral morphine equivalent) | 0.1mg fentanyl = 10mg morphine IV |
| Buprenorphine (analgesic) | ~75x (partial agonist ceiling) | Ceiling on respiratory depression |
| Tapentadol (oral) | 0.4x | Dual mechanism: mu-agonist + NRI |
| Tramadol (oral) | 0.1x | Weak mu-agonist; serotonin effects |

#### Fentanyl Analogs and Illicitly Manufactured Opioids

The street drug supply is now dominated by illicitly manufactured fentanyl (IMF) and increasingly by fentanyl analogs with varying potencies.

| Compound | Approximate Potency vs. Morphine | Clinical Notes |
|----------|----------------------------------|----------------|
| Fentanyl | 100x | Standard; street supply varies enormously in concentration |
| Acetylfentanyl | 15x | Less potent than fentanyl; may cause false reassurance about safety |
| Furanylfentanyl | 20x | Detected in many powder drug supplies |
| Carfentanil | 10,000x | Veterinary opioid; used as elephant tranquilizer; microgram doses lethal |
| Nitazenes (e.g., isotonitazene) | 500-1,000x | Emerging class; benzimidazole-opioids |
| Xylazine (tranq) | Not an opioid (alpha-2 agonist) | Not reversed by naloxone; causes severe skin necrosis |

**Clinical implication of contaminated supply:** Because IMF is mixed inconsistently into counterfeit pills and powders, "hot spots" (areas of concentrated fentanyl within a batch) lead to unpredictable overdose risk even for experienced users. Fentanyl test strips detect the presence of fentanyl but do not quantify concentration.

#### Opioid Half-Life Comparison

| Opioid | Half-Life | Onset (IV) | Duration of Action |
|--------|-----------|-----------|-------------------|
| Fentanyl | 3-12 hours (context-sensitive) | <1 min | 30-60 min (IV bolus) |
| Heroin (diacetylmorphine) | 2-6 min (rapidly converts to morphine) | <1 min | 3-5 hours |
| Morphine | 2-4 hours | 5-10 min | 3-5 hours |
| Hydromorphone | 2-3 hours | 5 min | 4-5 hours |
| Oxycodone | 3-5 hours | N/A (oral) | 4-6 hours (IR) |
| Methadone | 24-36 hours (range 8-59h) | 10-20 min | 24-36 hours |
| Buprenorphine | 24-42 hours | 15-45 min (SL) | 24-72 hours |

---

### Opioid Withdrawal

#### Clinical Opioid Withdrawal Scale (COWS)

COWS is an 11-item clinician-administered scale used to assess the severity of opioid withdrawal. It guides dosing during buprenorphine induction.

| Item | Parameter | Score Range |
|------|-----------|-------------|
| 1 | Resting pulse rate (beats/min) | 0-5 |
| 2 | Diaphoresis (sweating) | 0-4 |
| 3 | Restlessness (observation) | 0-5 |
| 4 | Pupil size | 0-5 |
| 5 | Bone or joint aches | 0-4 |
| 6 | Runny nose or tearing | 0-4 |
| 7 | GI upset (nausea, vomiting, diarrhea) | 0-5 |
| 8 | Tremor | 0-4 |
| 9 | Yawning | 0-4 |
| 10 | Anxiety or irritability | 0-4 |
| 11 | Gooseflesh (piloerection) | 0-5 |

**COWS Severity Thresholds**

| Total Score | Severity |
|-------------|---------|
| 5-12 | Mild withdrawal |
| 13-24 | Moderate withdrawal |
| 25-36 | Moderately severe withdrawal |
| 36+ | Severe withdrawal |

A COWS score of 8 or higher is generally required before initiating traditional buprenorphine induction to reduce risk of precipitated withdrawal.

#### Withdrawal Timeline by Opioid Type

**Short-acting opioids (heroin, oxycodone IR, hydrocodone IR, hydromorphone)**
- Onset: 8-24 hours after last use
- Peak symptoms: 36-72 hours
- Duration: 4-10 days
- Symptoms: anxiety, diaphoresis, rhinorrhea, lacrimation, yawning, myalgias, nausea, vomiting, diarrhea, piloerection, insomnia

**Long-acting opioids (methadone, sustained-release morphine/oxycodone)**
- Onset: 24-48 hours after last use
- Peak symptoms: 72-96 hours
- Duration: 10-20 days or longer (methadone withdrawal can persist weeks)

**Post-acute withdrawal syndrome (PAWS)**
- Persists weeks to months after acute withdrawal
- Symptoms: dysphoria, anhedonia, cognitive impairment, insomnia, cravings
- Major contributor to early relapse
- Managed with behavioral interventions, MOUD continuation, exercise

#### Non-MOUD Symptom Management (Comfort Medications)

These are adjunctive medications used for opioid withdrawal symptom relief when MOUD is not immediately available or as bridge therapy.

| Symptom | Medication | Dose |
|---------|-----------|------|
| Autonomic symptoms (global) | Clonidine (alpha-2 agonist) | 0.1-0.3mg PO TID; monitor BP (hold if SBP <90) |
| Pain, myalgias | NSAIDs (ibuprofen) | 400-600mg q6-8h with food |
| Pain, myalgias | Acetaminophen | 500-1000mg q6h |
| GI cramping | Dicyclomine | 10-20mg PO QID |
| Diarrhea | Loperamide | 4mg initial, then 2mg after each loose stool (max 16mg/day) |
| Nausea/vomiting | Ondansetron | 4-8mg q8h |
| Anxiety, insomnia | Hydroxyzine | 25-100mg q6-8h |
| Insomnia | Trazodone | 50-150mg QHS |
| Muscle cramps | Methocarbamol | 750-1500mg q8h |
| Restless legs | Gabapentin | 300-600mg TID |

**Note:** Clonidine treats the autonomic features of withdrawal but does not address cravings, dysphoria, or the subjective experience of withdrawal as effectively as MOUD.

---

### Medications for Opioid Use Disorder (MOUD)

MOUD — including buprenorphine, methadone, and naltrexone — is the standard of care for OUD. MOUD reduces mortality, reduces illicit drug use, improves social functioning, and reduces criminal activity. Withholding MOUD from patients with OUD is not evidence-based and contributes to preventable deaths.

---

#### Buprenorphine

**Mechanism of Action**
Buprenorphine is a partial agonist at the mu-opioid receptor and an antagonist at the kappa-opioid receptor. Its partial agonism means it activates the mu receptor but produces a ceiling effect — above approximately 32mg, additional doses do not increase respiratory depression. This ceiling on respiratory depression gives buprenorphine a wide safety margin compared to full agonists. Its extremely high receptor affinity (higher than morphine, heroin, or fentanyl) allows it to displace other opioids from receptors.

**Formulations**

| Formulation | Brand | Composition | Route | Notes |
|-------------|-------|-------------|-------|-------|
| Buprenorphine/naloxone film | Suboxone | 4:1 bup:naloxone (2/0.5, 4/1, 8/2, 12/3mg) | Sublingual/buccal | First-line; naloxone deters injection |
| Buprenorphine/naloxone tablet | Zubsolv | 0.7/0.18, 1.4/0.36, 5.7/1.4mg | Sublingual | Higher bioavailability; lower dose equivalent |
| Buprenorphine monoproduct | Subutex/generic | 2mg, 8mg | Sublingual | Used in pregnancy; no naloxone |
| Extended-release injectable | Sublocade | 100mg, 300mg | SQ monthly | Eliminates daily dosing; prevents diversion |
| Extended-release injectable | Brixelle | 8mg, 16mg, 24mg, 32mg | SQ weekly | Weekly option; rapid induction available |
| Implant | Probuphine | 4 implants x 80mg each | Subdermal 6 months | For stable patients on 8-16mg/day |

**Sublocade Extended-Release Dosing Protocol**
- Month 1 and 2: 300mg SQ injection
- Month 3 onward: 100mg SQ (may continue 300mg if needed)
- Must be stable on at least 8mg/day transmucosal buprenorphine before initiating
- No patient self-administration (REMS program)
- Injection site: abdomen; forms a solid depot; do not rub or massage

**Traditional Buprenorphine Induction Protocol**
1. Patient must be in mild to moderate withdrawal (COWS score 8 or higher)
2. Last use of short-acting opioid: at least 12-24 hours prior; long-acting (methadone): at least 24-72 hours prior
3. Starting dose: 2-4mg SL; observe for 1-2 hours; if no precipitated withdrawal, administer additional 2-4mg
4. Day 1 target dose: 8-16mg total
5. Titrate upward over the first several days based on cravings and withdrawal symptoms
6. Target maintenance dose: typically 16-24mg/day (range 8-32mg)
7. Higher doses (24-32mg) may be more effective for patients using high-potency fentanyl

**Low-Dose Buprenorphine Induction (Bernese Method)**

The Bernese (or micro-induction) method was developed to allow buprenorphine induction without requiring prior withdrawal, particularly useful for patients using high-dose fentanyl where traditional induction risks precipitated withdrawal.

- Day 1: Buprenorphine/naloxone 0.5-1mg SL while patient continues using opioids
- Days 2-7: Gradually increase dose (0.5-1mg increments every 1-2 days) while continuing other opioids
- Day 5-7: Discontinue other opioids once buprenorphine dose reaches 8-16mg
- This allows buprenorphine to gradually displace opioids from receptors without triggering precipitated withdrawal
- Particularly valuable in the fentanyl era, as fentanyl's long tissue storage makes traditional induction risky

**Precipitated Withdrawal**
Precipitated withdrawal occurs when buprenorphine is administered while opioid agonists still substantially occupy mu receptors. Buprenorphine, due to its high receptor affinity, rapidly displaces the full agonist but only partially activates the receptor — producing a sudden, severe withdrawal state.
- Onset: within 30-90 minutes of buprenorphine dose
- Symptoms: more severe and rapid than spontaneous withdrawal; extreme anxiety, cramping, diaphoresis, vomiting
- Management: comfort medications, continued buprenorphine doses (paradoxically, escalating buprenorphine dose to fully saturate receptors), supportive care
- Prevention: ensure adequate withdrawal (COWS 8+) or use Bernese method

**X-Waiver Elimination**
The Mainstreaming Addiction Treatment (MAT) Act, enacted December 2022 as part of the Consolidated Appropriations Act of 2023, eliminated the federal DATA 2000 X-waiver requirement. Since January 2023, any DEA-licensed practitioner (physicians, nurse practitioners, physician assistants) may prescribe buprenorphine for OUD without additional training or patient limits.

**Key Drug Interactions**
- Benzodiazepines and CNS depressants: additive respiratory depression; do not withhold buprenorphine (risk-benefit favors treatment), but educate on risk
- CYP3A4 inhibitors (azole antifungals, macrolides, ritonavir): increase buprenorphine levels — consider dose reduction
- CYP3A4 inducers (rifampin, carbamazepine, phenytoin): decrease buprenorphine levels — may require dose increase
- Other opioids: in standard doses, buprenorphine blocks the euphoric effects of other opioids due to high receptor occupancy

---

#### Methadone for OUD

**Mechanism of Action**
Methadone is a full mu-opioid receptor agonist with additional NMDA receptor antagonist activity. The NMDA antagonism may contribute to reduced opioid tolerance development. Methadone has a long and variable half-life of 24-36 hours (range 8-59 hours), which enables once-daily dosing but also creates risk for accumulation and QTc prolongation.

**Regulatory Framework**
Methadone for OUD may only be dispensed from federally licensed Opioid Treatment Programs (OTPs), also called methadone clinics. OTPs are regulated by SAMHSA and the DEA. Patients must initially attend daily for dosing; take-home doses are granted based on compliance, time in treatment, and stability.

**Dosing Guidelines**

| Phase | Dose |
|-------|------|
| Initial dose | 10-30mg; observe patient for 2-4 hours for sedation |
| Maximum initial dose | 30mg on Day 1; no more than 40mg by Day 2 |
| Titration | Increase no more than 5-10mg every 3-7 days |
| Therapeutic range | 60-120mg/day (higher doses associated with better retention and outcomes) |
| High-dose range | Up to 150mg/day for patients with persistent cravings or fentanyl use |

**QTc Monitoring**
Methadone prolongs the cardiac QTc interval via hERG potassium channel blockade, creating risk for torsades de pointes.

| QTc Value | Action |
|-----------|--------|
| Baseline <450ms | Proceed with treatment |
| 450-500ms | Discuss risks, proceed with caution and increased monitoring |
| >500ms | Reduce methadone dose or discontinue; consult cardiology |
| Monitoring schedule | Baseline ECG, then at 30 days, at dose 100mg+, then annually |

**Methadone Drug Interactions**

| Interacting Drug | Effect on Methadone | Mechanism |
|-----------------|--------------------|---------| 
| Rifampin | Levels drop 50-80%; withdrawal | CYP3A4/CYP2B6 induction |
| Carbamazepine, phenytoin | Reduced levels; withdrawal | CYP3A4/CYP2B6 induction |
| Fluconazole, ketoconazole | Increased levels; toxicity | CYP3A4 inhibition |
| Ciprofloxacin, erythromycin | QTc prolongation (additive) | hERG channel blockade |
| Antipsychotics (haloperidol, ziprasidone) | QTc prolongation (additive) | hERG channel blockade |
| HIV antiretrovirals (ritonavir, lopinavir) | Variable — usually reduce levels | CYP3A4/2B6 induction or inhibition |
| Alcohol, benzodiazepines | CNS/respiratory depression | Additive |

**Take-Home Eligibility (Federal Regulations)**
- 90+ days: 1 take-home per week allowed
- 2 years: 2 take-homes per week allowed
- After 2 years of demonstrated stability: up to 1 month of take-homes (exceptional take-homes)
- COVID-19 exception: SAMHSA liberalized take-home policies during the pandemic; many states have retained expanded access

---

#### Naltrexone for OUD

**Mechanism of Action**
Naltrexone is a full opioid antagonist at mu, kappa, and delta receptors. It blocks all opioid effects and has no agonist properties. It does not cause dependence or withdrawal. It works best for highly motivated patients who are already detoxified and do not require agonist stabilization.

**Formulations**

| Formulation | Brand | Dose | Route | Frequency |
|-------------|-------|------|-------|-----------|
| Oral naltrexone | ReVia, generic | 50mg | PO | Daily |
| Extended-release injectable | Vivitrol | 380mg | IM gluteal | Monthly |

Extended-release naltrexone (XR-NTX) is preferred over oral due to dramatically superior adherence and outcomes.

**Induction Requirements**

Before initiating naltrexone, the patient must be fully opioid-free to avoid precipitating withdrawal:
- Short-acting opioids (heroin, hydrocodone, oxycodone): 7-10 days opioid-free
- Buprenorphine: 10-14 days after last dose (due to long half-life and high receptor affinity)
- Methadone: 14+ days after last dose (some guidelines recommend 21+ days)

**Naloxone Challenge Test (before initiating)**
- Administer naloxone 0.4-0.8mg IV or 0.8mg SQ/IM
- If no withdrawal signs in 45-60 minutes, patient is likely opioid-free
- Some clinicians use a smaller oral naltrexone challenge (12.5mg) as a safer approach

**Monitoring**
- Liver function tests: baseline and periodically; naltrexone is hepatotoxic at supratherapeutic doses; contraindicated in acute hepatitis or liver failure
- If opioids are needed (surgery, acute pain): regional anesthesia preferred; if opioids are required, higher doses may be needed to overcome receptor blockade; consult pain management

**Ideal Candidates for Naltrexone**
- Highly motivated patients with strong recovery support
- Healthcare professionals and others in monitored professions
- Patients with legal mandates requiring opioid-free status
- Patients who have already completed medically supervised withdrawal
- Patients who explicitly prefer a non-opioid treatment option

---

### Opioid Overdose: Recognition and Reversal

#### Clinical Presentation

The opioid overdose triad:
1. Respiratory depression (rate <12/min, or shallow/irregular)
2. Miosis (pinpoint pupils)
3. Altered consciousness (ranging from sedation to unresponsive)

Additional signs: cyanosis, gurgling or absent respirations, bradycardia, hypotension, pulmonary edema, skin findings (track marks, abscess sites).

Atypical presentations with fentanyl analogs: "wooden chest syndrome" (chest wall rigidity from rapid high-dose fentanyl) may prevent effective bag-mask ventilation.

Xylazine co-intoxication (increasingly common): patient may be unresponsive and have necrotic skin wounds; naloxone will partially reverse opioid effects but will not reverse xylazine alpha-2 agonism — support ventilation.

#### Naloxone Dosing

Naloxone is a competitive opioid antagonist. Duration of action is 45-90 minutes — shorter than most opioids — requiring vigilance for re-narcotization.

| Route | Formulation | Dose | Repeat |
|-------|------------|------|--------|
| Intranasal | Narcan 4mg/0.1mL | 1 spray each nostril (4mg total) | Repeat q2-3 min x2 |
| IM/SQ | Generic 0.4mg/mL | 0.4mg to 2mg | Repeat q2-3 min |
| IV | Generic 0.4mg/mL | 0.4mg to 2mg slow IV push | Repeat q2-3 min |
| Auto-injector | Evzio 0.4mg | 0.4mg IM thigh | Repeat q2-3 min |
| High-dose IN | Kloxxado 8mg | 8mg per nostril | For suspected carfentanil/nitazenes |
| IV infusion | Calculate from reversal dose | 2/3 of effective reversal dose per hour | Continuous until opioid cleared |

**High-dose opioid (fentanyl/carfentanil) overdose approach:**
- Start with 4mg intranasal (2mg per nostril) or 2mg IV
- Repeat every 2-3 minutes up to 10mg if no response
- Prepare for high-volume naloxone requirement; have IV infusion available
- Carfentanil poisoning may require 10-50mg+ total naloxone

**IV infusion calculation:**
1. Determine dose that achieved reversal (e.g., 2mg)
2. Infusion rate = 2/3 of reversal dose per hour = ~1.3mg/hour
3. Mix in D5W or NS; reassess and titrate to maintain adequate respiration without precipitating withdrawal in dependent patient

**Re-narcotization monitoring:**
- Observe for minimum 2-4 hours after last naloxone dose for short-acting opioids
- Observe 4-6+ hours for long-acting or sustained-release opioids, or transdermal patches
- Fentanyl's large volume of distribution means ongoing drug release from tissue stores

#### Community Naloxone Distribution

- Standing orders allow pharmacists to dispense naloxone without individual prescriptions
- Lay rescuer training: recognize overdose, call 911, administer naloxone, perform rescue breathing
- Good Samaritan laws (47 states + DC): provide legal protection for persons who call 911 during an overdose
- Co-prescribing naloxone: indicated whenever prescribing >50 MME/day, combined opioid + benzodiazepine, or known history of SUD

---

## Alcohol Use Disorder

### Epidemiology and Risk

Alcohol use disorder affects approximately 14.5 million adults in the United States. It is the third leading preventable cause of death. Standard drink definitions are essential for clinical communication:

**Standard Drink = 14 grams of pure alcohol:**
- 12 oz regular beer (5% ABV)
- 5 oz wine (12% ABV)
- 1.5 oz distilled spirits (40% ABV)

**Low-risk drinking guidelines (NIAAA):**
- Men: no more than 4 drinks on any day and no more than 14 per week
- Women: no more than 3 drinks on any day and no more than 7 per week
- Ages 65+: no more than 3 drinks on any day and no more than 7 per week

---

### Alcohol Screening

**AUDIT (Alcohol Use Disorders Identification Test)**
The full AUDIT is a 10-item validated questionnaire covering three domains:
- Hazardous alcohol use (questions 1-3)
- Dependence symptoms (questions 4-6)
- Harmful alcohol use (questions 7-10)
- Score 8+: hazardous or harmful use (men); Score 4+: hazardous or harmful use (women and elderly); Score 20+: likely severe AUD

**AUDIT-C (first 3 questions only)**

| Question | Response Options | Points |
|----------|-----------------|--------|
| How often do you have a drink containing alcohol? | Never / Monthly or less / 2-4x/month / 2-3x/week / 4+x/week | 0-4 |
| How many standard drinks on a typical day? | 1-2 / 3-4 / 5-6 / 7-9 / 10+ | 0-4 |
| How often do you have 6 or more drinks on one occasion? | Never / Less than monthly / Monthly / Weekly / Daily or almost daily | 0-4 |

- Men: score 3+ = positive screen
- Women: score 2+ = positive screen

**CAGE Questionnaire**
- Cut down, Annoyed, Guilty, Eye-opener
- 2+ positive = clinically significant screen; sensitivity 71-93%, specificity 77-96% for alcohol dependence

---

### Alcohol Withdrawal

Alcohol withdrawal can be life-threatening due to CNS hyperexcitability following removal of GABAergic suppression.

#### Pathophysiology

Chronic alcohol use upregulates NMDA glutamate receptors and downregulates GABA-A receptors. Upon alcohol cessation, the brain is left in a state of excitatory/inhibitory imbalance — excess glutamate activity drives withdrawal symptoms, seizures, and delirium.

#### Clinical Institute Withdrawal Assessment — Alcohol (CIWA-Ar)

The CIWA-Ar is the standard clinical tool for monitoring alcohol withdrawal severity. It contains 10 items, with a maximum score of 67.

| Item | Scoring Range | Notes |
|------|--------------|-------|
| Nausea and vomiting | 0-7 | 0 = none; 7 = constant nausea/vomiting |
| Tremor | 0-7 | Outstretched arms |
| Paroxysmal sweats | 0-7 | 0 = none; 7 = drenching sweats |
| Anxiety | 0-7 | 0 = none; 7 = acute panic state |
| Agitation | 0-7 | 0 = normal activity; 7 = pacing/thrashing |
| Tactile disturbances | 0-7 | Formication, numbness, pruritus |
| Auditory disturbances | 0-7 | Harshness, frightening sounds, hallucinations |
| Visual disturbances | 0-7 | Sensitivity, blurriness, hallucinations |
| Headache/fullness in head | 0-7 | Do not rate dizziness |
| Orientation/clouding of sensorium | 0-4 | Date, year, who is around patient |

**CIWA-Ar Severity and Treatment Thresholds**

| Score | Severity | Treatment |
|-------|---------|-----------|
| <8-10 | Mild | Monitor; may not need medication |
| 10-18 | Moderate | Consider benzodiazepine treatment |
| >18 | Severe | Benzodiazepine treatment required |
| >20 or DTs | Severe/critical | ICU admission; aggressive BZD therapy |

#### Alcohol Withdrawal Timeline

| Phase | Timing | Manifestations |
|-------|--------|---------------|
| Early withdrawal | 6-24 hours after last drink | Tremor, anxiety, diaphoresis, tachycardia, hypertension, insomnia, GI symptoms |
| Seizures | 6-48 hours (peak ~24 hours) | Generalized tonic-clonic; usually brief; risk of status epilepticus; no focal features |
| Alcoholic hallucinosis | 12-48 hours | Visual, auditory, or tactile hallucinations with clear sensorium; distinct from DTs |
| Delirium tremens (DTs) | 48-96 hours (onset 24-72h) | Confusion, global disorientation, vivid hallucinations, autonomic instability; medical emergency |

**Delirium Tremens (DTs)**
- Mortality: 5-15% without treatment; <1% with prompt aggressive treatment
- Risk factors: prior history of DTs or withdrawal seizures, concomitant medical illness, heavy/prolonged use, older age, elevated CIWA on presentation, hypokalemia
- Features: fever, profuse diaphoresis, tachycardia (>120 bpm), hypertension or hypotension, confusion, agitation, vivid visual/tactile hallucinations, picking at nonexistent objects (carphologia)

#### Wernicke Encephalopathy

Wernicke encephalopathy is a neurological emergency caused by thiamine (B1) deficiency, common in patients with AUD due to poor nutrition and malabsorption.

**Classic triad (all three present in only ~10% of cases):**
1. Confusion (global confusional state)
2. Ophthalmoplegia or nystagmus (CN VI palsy most common)
3. Gait ataxia (cerebellar)

**Treatment — CRITICAL: Give thiamine BEFORE glucose**
- Thiamine 500mg IV three times daily for 3 days (then oral thiamine 100mg daily)
- Glucose without thiamine first depletes remaining thiamine stores and can precipitate or worsen Wernicke's
- In the ED: assume thiamine deficiency in any malnourished, alcohol-using, or altered patient

**Wernicke-Korsakoff Syndrome**
- Develops when Wernicke encephalopathy is not adequately treated
- Cardinal features: severe anterograde amnesia (inability to form new memories), retrograde amnesia, confabulation (unconscious fabrication of memories)
- Mammillary body and thalamic damage visible on MRI
- Prognosis: 25% make a good recovery; 25% have persistent severe amnesia; 50% partial recovery

---

### Alcohol Withdrawal Treatment

#### Benzodiazepine Protocol

Benzodiazepines are the first-line treatment for alcohol withdrawal. They act at GABA-A receptors, compensating for the upregulation of NMDA receptors caused by chronic alcohol use.

**CIWA-guided (symptom-triggered) protocol — preferred for inpatient:**
- Lorazepam 1-2mg IV/IM or PO every 1 hour when CIWA-Ar score 8 or higher
- Reassess CIWA-Ar every 30-60 minutes after each dose
- Diazepam 5-10mg IV/IM or PO every 1 hour is an alternative (longer-acting; self-tapering)
- Chlordiazepoxide 25-50mg PO q6h is widely used (long half-life)
- Symptom-triggered dosing uses less medication and shorter treatment duration than fixed-dose schedules

**Fixed-dose taper — appropriate for predictable low-moderate risk, outpatient:**
- Diazepam 10mg PO q6h x 4 doses (Day 1)
- Diazepam 5mg PO q6h x 8 doses (Days 2-3)
- PRN additional doses for breakthrough symptoms
- Chlordiazepoxide 25mg PO QID tapering over 5-7 days is an alternative

**Lorazepam preferred in:**
- Hepatic failure (does not undergo hepatic oxidative metabolism; glucuronidation only)
- Elderly patients (less accumulation)
- Respiratory compromise (shorter half-life)

#### Phenobarbital

Phenobarbital is an effective alternative or adjunct to benzodiazepines, particularly for BZD-resistant withdrawal.

- Loading dose: 10-20mg/kg IV (max 30mg/kg) administered at rate of 50-75mg/min
- IM alternative: 130-260mg IM (useful in ED without IV access)
- Phenobarbital-based protocols may reduce need for ICU admission
- Mechanism: positive allosteric modulator of GABA-A (different site than benzodiazepines)
- Can be used alongside BZDs for refractory cases

#### Alcohol Withdrawal Seizures

- Typically generalized tonic-clonic, brief, self-limiting
- Risk: peak at 24 hours after last drink
- Benzodiazepines (lorazepam 2-4mg IV) are first-line for seizure management
- Phenytoin and fosphenytoin are NOT effective for alcohol withdrawal seizures (do not address the underlying GABA/NMDA imbalance)
- After first seizure: initiate or escalate BZD therapy to prevent recurrence
- Status epilepticus: treat aggressively with escalating IV BZDs; propofol or phenobarbital for refractory cases

#### ICU Indications for Alcohol Withdrawal
- Active DTs
- Severe autonomic instability
- Temperature above 38.5°C
- Refractory to standard doses of benzodiazepines (requiring >40mg diazepam equivalents/hour)
- Complicating medical illness (GI bleed, infection, hepatic failure)
- Need for intubation

**Dexmedetomidine (Precedex)** as adjunct in ICU:
- Alpha-2 agonist (similar to clonidine, but more potent and titratable)
- Reduces autonomic symptoms and BZD requirements
- Not effective as monotherapy — cannot prevent seizures
- Useful for agitated patients requiring sedation alongside BZDs

---

### Pharmacotherapy for Alcohol Use Disorder

#### Naltrexone

Naltrexone blocks the endogenous opioid system reward response to alcohol, reducing cravings and the reinforcing effects of drinking.

| Parameter | Details |
|-----------|---------|
| Mechanism | Opioid receptor antagonist; blocks alcohol-induced dopamine release in NAc |
| Oral dose | 50mg PO daily |
| IM dose | Vivitrol 380mg IM gluteal once monthly |
| Indication | Reduces heavy drinking days; reduces relapse to heavy drinking |
| Best for | Patients with strong craving, reward-driven drinking; "reward drinkers" |
| Contraindications | Current or anticipated opioid use, acute hepatitis, liver failure |
| Monitoring | LFTs at baseline; caution if ALT/AST >3-5x normal |
| Evidence | NNT approximately 7-12 for preventing relapse to heavy drinking |

The OPRM1 gene (A118G polymorphism — Asn40Asp): patients with the G allele may respond better to naltrexone (Oslin et al., PREDICT study). Not yet standard of care for genetic testing.

#### Acamprosate

Acamprosate modulates NMDA glutamate receptors and GABA activity, normalizing the hyperexcitable state that persists after alcohol cessation and drives alcohol craving and relapse.

| Parameter | Details |
|-----------|---------|
| Mechanism | NMDA antagonist / GABA modulator; reduces dysphoric craving |
| Dose | 666mg PO TID (two 333mg tablets three times daily) |
| Reduced dose | 333mg PO TID if CrCl 30-50 mL/min; contraindicated in severe renal impairment |
| Indication | Maintaining abstinence; reduces withdrawal-mediated craving |
| Best for | Patients who are already abstinent at initiation; anxiety-driven drinking |
| Advantages | Not metabolized hepatically — safe in liver disease |
| Contraindications | Severe renal impairment (CrCl <30) |
| Evidence | Reduces relapse to any drinking; less effective for reducing heavy drinking |

#### Disulfiram

Disulfiram inhibits aldehyde dehydrogenase (ALDH), blocking the metabolism of acetaldehyde (a toxic intermediate of ethanol oxidation). Acetaldehyde accumulation causes an unpleasant aversive reaction.

| Parameter | Details |
|-----------|---------|
| Mechanism | Irreversible ALDH inhibitor; acetaldehyde accumulation |
| Dose | 250mg PO daily (range 125-500mg) |
| Disulfiram-ethanol reaction | Flushing, nausea, vomiting, diaphoresis, palpitations, hypotension, tachycardia; onset 10-30 min; may last several hours |
| Severe reaction | Chest pain, arrhythmia, MI, respiratory depression (rare); can be fatal |
| Duration of effect | 7-14 days after last dose (enzyme takes time to regenerate) |
| Requirements | Patient must be fully abstinent; must understand reaction risk |
| Hidden alcohol sources | Mouthwash, cooking wine, some sauces, cough syrups, hand sanitizer — all can trigger reaction |
| Contraindications | Cardiac disease, psychosis, severe hepatic disease, pregnancy, inability to understand reaction risk |
| Monitoring | LFTs; risk of drug-induced hepatitis |
| Best for | Patients with external motivation/supervision (supervised disulfiram); impulsive drinkers |

#### Gabapentin

| Parameter | Details |
|-----------|---------|
| Mechanism | Alpha-2-delta calcium channel ligand; reduces glutamate activity; GABAergic effects |
| Dose | 300-600mg TID for AUD; up to 1800mg/day |
| Evidence | Mason et al. (JAMA Internal Medicine 2014): superior to placebo for abstinence and no heavy drinking; reduces insomnia and anxiety |
| Withdrawal use | Effective for mild to moderate withdrawal symptoms; reduces seizure threshold less than BZDs |
| Advantages | Treats comorbid anxiety, insomnia, pain; not hepatically oxidized |
| Cautions | Abuse potential (especially at high doses or with opioids); renal dosing required; avoid abrupt discontinuation |

---

## Stimulant Use Disorder (Cocaine and Methamphetamine)

### Epidemiology

Stimulant use disorder is a growing public health problem. Methamphetamine use has surged, and fentanyl-stimulant polysubstance use (especially fentanyl + methamphetamine) now accounts for a growing proportion of overdose deaths.

---

### Cocaine: Pharmacology and Clinical Effects

Cocaine blocks reuptake transporters for dopamine, norepinephrine, and serotonin, causing acute flooding of synaptic monoamines. It also acts as a voltage-gated sodium channel blocker (local anesthetic properties).

**Routes and pharmacokinetics:**
- Intranasal (insufflation): onset 3-5 min, peak 15-30 min, duration 45-90 min
- IV: onset <1 min, duration 20-30 min
- Smoked (crack cocaine): onset <1 min (similar to IV), duration 5-15 min (shorter due to rapid metabolism)

#### Cocaine Intoxication and Toxicity

**Sympathomimetic toxidrome:**
- Cardiovascular: tachycardia, hypertension, coronary vasospasm, myocardial infarction (most common cause of drug-induced MI), aortic dissection, arrhythmias (including VT and VF), myocarditis
- CNS: euphoria, psychomotor agitation, paranoid ideation, seizures, stroke (hemorrhagic or ischemic), hyperthermia
- Systemic: diaphoresis, mydriasis, tremor, hyperthermia, rhabdomyolysis
- Respiratory: pneumothorax (barotrauma from Valsalva maneuver), pulmonary hemorrhage ("crack lung"), bronchospasm

**Management of cocaine intoxication:**
- Benzodiazepines (lorazepam 1-2mg IV q5-10 min) for agitation, anxiety, seizures, and hypertension
- Avoid beta-blockers — may cause unopposed alpha-adrenergic stimulation, worsening coronary vasospasm and hypertension
- Cocaine chest pain: nitroglycerin, aspirin, calcium channel blockers (amlodipine, diltiazem); phentolamine (alpha-blocker) for refractory hypertension
- Hyperthermia: aggressive cooling (ice packs, cooling blankets, cold IV fluids); benzodiazepines reduce thermogenesis
- If ACS develops: standard ACS management; thrombolytics with caution (elevated bleeding risk)

---

### Methamphetamine: Pharmacology and Clinical Effects

Methamphetamine causes massive release (rather than just reuptake blockade) of dopamine, norepinephrine, and serotonin from presynaptic terminals. It also blocks reuptake. The result is prolonged, intense monoamine flooding.

**Pharmacokinetics:** Half-life 10-12 hours; duration of action 8-12 hours (much longer than cocaine).

#### Methamphetamine Intoxication and Toxicity
- Cardiovascular: tachycardia, severe hypertension, cardiomyopathy (with chronic use), pulmonary hypertension
- CNS: intense euphoria, hypervigilance, paranoia, hallucinations (particularly tactile — formication/"meth mites"), violent behavior, seizures, stroke, hyperthermia
- Methamphetamine psychosis: may be clinically indistinguishable from paranoid schizophrenia; can persist weeks to months after last use
- Skin: excoriations from picking (delusional parasitosis), severe dental disease ("meth mouth" — xerostomia + poor hygiene + clenching)
- Rhabdomyolysis: hyperthermia + agitation → muscle breakdown; treat with IV fluids, urine alkalinization

**Management of methamphetamine intoxication:**
- Cooling: ice water immersion, evaporative cooling, cool IV fluids; treat hyperthermia aggressively
- Benzodiazepines: lorazepam or diazepam for agitation, seizures, hypertension
- Antipsychotics for psychosis: haloperidol 5-10mg IM; droperidol 5mg IM/IV; olanzapine 10mg IM; avoid in hyperthermia (impairs heat dissipation)
- IV fluids: 1-2L NS for rhabdomyolysis; monitor CK, creatinine
- Avoid beta-blockers (as with cocaine)

---

### Stimulant Withdrawal

Stimulant withdrawal is not medically dangerous (no seizures, no autonomic instability), but is psychologically significant.

**Cocaine withdrawal ("crash"):**
- Onset: hours to 1-2 days after last use
- Symptoms: profound fatigue, dysphoria, increased appetite, hypersomnia, depression, strong cravings
- Duration: days to 1-2 weeks
- Post-acute phase: persistent depression, anhedonia, cognitive impairment — may last weeks

**Methamphetamine withdrawal:**
- More severe and prolonged than cocaine withdrawal due to longer half-life and greater dopamine depletion
- Profound fatigue, dysphoria, hypersomnia, hyperphagia, severe depression, anhedonia, cravings
- Duration: 1-3 weeks acute; protracted dysphoria may last months

---

### Pharmacotherapy for Stimulant Use Disorder

No FDA-approved medications exist for cocaine or methamphetamine use disorder. This is a major unmet need.

**Evidence-based behavioral treatments:**
- Contingency management (CM): the most evidence-supported intervention; provides incentive prizes for verified abstinence; highest effect sizes in addiction behavioral research
- Cognitive-behavioral therapy (CBT): relapse prevention, coping skills
- Community reinforcement approach (CRA): restructures social/vocational reinforcement to support abstinence

**Investigational and off-label pharmacotherapy:**

| Medication | Evidence Level | Notes |
|-----------|---------------|-------|
| Naltrexone | Moderate (meth) | Some RCT evidence for methamphetamine; may reduce craving via opioid system |
| Bupropion | Moderate | Dopamine/norepinephrine reuptake inhibitor; modest effect in methamphetamine |
| Mirtazapine | Moderate | RCT evidence in methamphetamine use disorder in MSM; reduces use frequency |
| Topiramate | Limited | Modulates GABA/glutamate; some evidence for cocaine; GI side effects limit use |
| N-Acetylcysteine | Limited | Restores glutamate homeostasis in NAc; Phase II trials show modest effect |
| Modafinil | Limited | Wakefullness-promoting; mixed results for cocaine |
| Extended-release amphetamine | Experimental | Agonist substitution approach; under investigation for meth use disorder |

---

## Benzodiazepine Dependence

### Mechanism of Physical Dependence

Benzodiazepines act as positive allosteric modulators of GABA-A receptors, increasing chloride conductance and reducing neuronal excitability. Chronic use leads to:
- Downregulation of GABA-A receptor density
- Decreased receptor sensitivity
- Compensatory upregulation of excitatory (glutamate, norepinephrine) systems

Abrupt discontinuation removes benzodiazepine facilitation of GABA while excitatory systems are upregulated — producing a withdrawal syndrome that can include life-threatening seizures. This is similar in mechanism to alcohol withdrawal and is equally serious.

---

### Benzodiazepine Equivalence Table

Converting to diazepam equivalent is essential for planning tapers, as diazepam has the longest half-life and provides the smoothest pharmacokinetic taper.

| Drug | Approximate Equivalent Dose to Diazepam 5mg | Half-Life | Active Metabolites |
|------|-------------------------------------------|-----------|-------------------|
| Diazepam (Valium) | 5mg | 20-100 hours | Yes (desmethyldiazepam) |
| Chlordiazepoxide (Librium) | 12.5-25mg | 6-30 hours | Yes |
| Clonazepam (Klonopin) | 0.5mg | 20-50 hours | No |
| Lorazepam (Ativan) | 1mg | 10-20 hours | No |
| Alprazolam (Xanax) | 0.5mg | 6-12 hours | No |
| Temazepam (Restoril) | 10mg | 8-22 hours | No |
| Oxazepam (Serax) | 15mg | 5-20 hours | No |
| Triazolam (Halcion) | 0.25mg | 1.5-5 hours | No |
| Midazolam (Versed) | 2-3mg | 1-4 hours | Yes (minimal) |

Clonazepam, lorazepam, and oxazepam undergo glucuronidation only (no hepatic oxidative metabolism) — preferred in elderly and hepatic impairment.

---

### Benzodiazepine Tapering Protocol

**General principles:**
- Never abrupt discontinuation — risk of withdrawal seizures, severe anxiety, psychosis
- Taper rate: generally 5-10% reduction per week (slower for long-term, high-dose users)
- Slow tapers of 6-12 months or longer may be required for patients on high doses for many years
- The Ashton Manual (Heather Ashton, 2002) remains an influential patient and clinician resource

**Protocol:**
1. Convert current benzodiazepine dose to diazepam equivalent
2. Switch to diazepam (or chlordiazepoxide) — provides smoother taper due to long half-life and active metabolites that self-taper
3. Stabilize on equivalent diazepam dose for 1-2 weeks
4. Reduce by 5-10% of current dose every 1-2 weeks, adjusting rate based on symptoms
5. Smaller reductions as dose decreases (last 10-20% of taper often most difficult)

**GABA receptor normalization:** GABA-A receptor density and sensitivity takes approximately 2-4 weeks to normalize after benzodiazepine removal, explaining why withdrawal symptoms can peak days to weeks into taper.

**Adjunctive agents:**

| Medication | Role | Dose |
|-----------|------|------|
| Gabapentin | Reduces anxiety, insomnia, craving | 300-600mg TID; taper separately after BZD taper complete |
| Hydroxyzine | Anxiolytic; non-habit-forming | 25-50mg q6-8h PRN |
| Propranolol | Reduces autonomic symptoms (palpitations, tremor) | 10-20mg TID |
| Melatonin | Sleep support | 0.5-3mg QHS |
| SSRIs/SNRIs | Underlying anxiety disorder | Initiate early; 2-4 weeks lag to onset |
| Carbamazepine | Seizure prophylaxis in high-risk patients | 200-400mg BID; level-monitored |
| Valproate | Adjunct; some evidence for withdrawal | Level-monitored |

---

## Cannabis Use Disorder

### DSM-5 Criteria Application

Cannabis use disorder uses the same 11 DSM-5 criteria as other SUDs. In the United States, cannabis is the most commonly used illicit drug and the second most common SUD after alcohol.

**Prevalence:** Approximately 9% of people who use cannabis develop CUD; 17% of those who start in adolescence; 25-50% of daily users.

### High-THC Products and Risk

- Modern high-potency cannabis products (concentrates, dabs, wax) may contain 60-90% THC compared to 10-15% in traditional cannabis
- Adolescent use during brain development associated with elevated risk for psychosis, cognitive impairment, and SUD
- Frequency and route of administration (smoked vs. edible) affect onset and risk

### Cannabis Withdrawal Syndrome

Cannabis withdrawal is now recognized in DSM-5. It occurs in regular, heavy users (daily/near-daily for months).

**Symptoms (onset 24-72 hours after cessation):**
- Irritability, anger, aggression
- Anxiety, nervousness
- Sleep disturbance, insomnia, disturbing dreams
- Decreased appetite or weight loss
- Restlessness
- Depressed mood
- Physical symptoms: headache, sweating, shakiness, nausea, abdominal pain

**Duration:** Symptoms peak 2-6 days after cessation; most resolve within 1-2 weeks, though sleep disturbance may persist longer.

### Cannabis Hyperemesis Syndrome

- Cyclical episodes of severe nausea, vomiting, and abdominal pain in chronic heavy cannabis users
- Pathognomonic feature: relief with hot showers or baths (compulsive bathing behavior)
- Capsaicin cream applied to abdomen provides relief in some patients (topical TRPV1 agonism)
- Resolution requires cessation of cannabis use; symptoms recur with resumption
- Often misdiagnosed; typical cannabis user may have used for years before onset

### Pharmacotherapy for Cannabis Use Disorder

No FDA-approved medications exist. Evidence-based behavioral treatments:
- Cognitive-behavioral therapy (CBT): most evidence; relapse prevention, coping skills
- Motivational enhancement therapy (MET): 2-4 sessions; effective for ambivalent users
- Contingency management: effective particularly in adolescents

Investigational pharmacotherapy: N-acetylcysteine (NAC) in adolescents showed some benefit in one RCT. Gabapentin for sleep and anxiety symptoms.

---

## Nicotine Dependence

### Assessment: Fagerstrom Test for Nicotine Dependence (FTND)

| Question | Response | Points |
|---------|---------|--------|
| How soon after waking do you smoke? | Within 5 min / 6-30 min / 31-60 min / After 60 min | 3/2/1/0 |
| Do you find it difficult to refrain in non-smoking areas? | Yes / No | 1/0 |
| Which cigarette would be hardest to give up? | First morning / Other | 1/0 |
| How many cigarettes per day? | ≤10 / 11-20 / 21-30 / ≥31 | 0/1/2/3 |
| Do you smoke more in the morning? | Yes / No | 1/0 |
| Do you smoke even when ill in bed? | Yes / No | 1/0 |

- Score 0-2: very low dependence
- Score 3-4: low dependence
- Score 5: moderate dependence
- Score 6-7: high dependence
- Score 8-10: very high dependence (first morning cigarette within 5 minutes is high-dependency marker)

---

### Nicotine Replacement Therapy (NRT)

NRT replaces nicotine from cigarettes to reduce withdrawal while avoiding toxicants in tobacco smoke.

**Nicotine Patch (transdermal)**

| Dose | Duration | For |
|------|---------|-----|
| 21mg/24h | 6-8 weeks | >10 cigarettes/day; first step |
| 14mg/24h | 2 weeks | Second step |
| 7mg/24h | 2 weeks | Third step / <10 cig/day start |

**Nicotine Gum**
- 2mg: fewer than 25 cigarettes/day; or first cigarette >30 min after waking
- 4mg: 25+ cigarettes/day; or first cigarette within 30 min of waking
- Technique: chew until tingling ("park" between cheek and gum; chew again when tingling fades)
- Avoid eating/drinking 15 minutes before and during use
- Maximum 24 pieces/day

**Nicotine Lozenge**
- 2mg and 4mg (same criteria as gum)
- Dissolves over 20-30 min; do not chew or swallow whole
- Maximum 20 lozenges/day; avoid eating/drinking 15 min prior

**Nicotine Inhaler (prescription only)**
- 10mg cartridge; delivers ~4mg per 20-min puffing session
- Mouth/throat irritation common
- 6-16 cartridges/day for 12 weeks, then taper

**Nicotine Nasal Spray (prescription only)**
- 0.5mg per spray (1 dose = 1 spray each nostril = 1mg)
- 1-2 doses/hour; max 5 doses/hour or 40 doses/day
- Fastest delivery of all NRT forms; highest dependence potential
- Significant nasal irritation initially

**Combination NRT:** Patch + short-acting form (gum, lozenge, or inhaler) provides consistently better quit rates than patch alone. Meta-analyses show combination NRT has approximately 15-20% abstinence at 6-12 months vs. 10-12% for monotherapy.

---

### Varenicline (Chantix)

| Parameter | Details |
|-----------|---------|
| Mechanism | Partial agonist at alpha-4-beta-2 nicotinic acetylcholine receptor; reduces withdrawal and blocks reinforcement from smoking |
| Titration | 0.5mg PO daily for 3 days, then 0.5mg BID for 4 days, then 1mg BID |
| Duration | 12 weeks; additional 12 weeks if successful (for total 24 weeks) |
| Quit date | Set 1 week after starting (or up to 35 days into treatment for flexible quitting) |
| Efficacy | Most effective monotherapy for smoking cessation; odds ratio ~3.6 vs. placebo |
| Adverse effects | Nausea (most common; take with food and water), vivid dreams, insomnia, headache |
| Neuropsychiatric | FDA black box warning (added 2009) was REMOVED in 2016 after EAGLES trial showed no increase in neuropsychiatric events in patients without psychiatric history; some residual caution in severe psychiatric illness |
| Renal dosing | Reduce to 0.5mg BID if CrCl <30 mL/min |
| Cardiovascular | Use with caution in recent cardiovascular event (some studies suggest small increased risk) |

---

### Bupropion SR (Zyban)

| Parameter | Details |
|-----------|---------|
| Mechanism | Norepinephrine and dopamine reuptake inhibitor; weak nicotinic receptor antagonist |
| Dosing | 150mg PO daily x 3 days, then 150mg PO BID x 7-12 weeks |
| Quit date | Set 1-2 weeks after starting (allows therapeutic level to establish) |
| Efficacy | Odds ratio ~2.0 vs. placebo; less effective than varenicline |
| Adverse effects | Insomnia, dry mouth, headache, nausea, agitation |
| Contraindications | Seizure disorder, eating disorders (anorexia/bulimia), abrupt discontinuation of alcohol/benzodiazepines, MAOI use within 14 days |
| Seizure risk | Dose-dependent; SR formulation has lower risk than immediate-release; maximum 300mg/day |
| Psychiatric | Can be used in depression (same drug as Wellbutrin); useful when smoking cessation and depression coexist |

---

## Harm Reduction

### Core Principles

Harm reduction is a pragmatic public health approach that accepts drug use as a reality and focuses on reducing the negative health, social, and economic impacts of drug use without necessarily requiring abstinence. It is evidence-based, person-centered, and non-judgmental.

Key principles:
- Meet people where they are — not where we want them to be
- Any reduction in harm is a positive outcome
- People who use drugs have rights to accurate information and services
- Abstinence may be the ultimate goal but is not a prerequisite for receiving services

### Naloxone Access Programs

- Standing orders: state-level prescriptions allowing pharmacists to dispense naloxone to any person without a physician prescription
- Every U.S. state now has some form of naloxone standing order or OTC access
- Intranasal Narcan (4mg) is FDA-approved as OTC (over-the-counter) as of 2023
- Lay rescuer training: how to recognize overdose, call 911, position patient, administer naloxone, provide rescue breathing
- Co-prescribing naloxone: any patient on high-dose opioids or with OUD should receive a prescription

### Fentanyl Test Strips

Fentanyl test strips (FTS) are immunoassay strips that detect fentanyl (and many analogs) in a drug sample. Originally designed for urine drug testing, they have been repurposed as point-of-use harm reduction tools.

- Process: dissolve small amount of drug in water; dip strip for 15 seconds; read at 2-5 minutes
- Positive (fentanyl present): 1 line
- Negative (no fentanyl): 2 lines
- Limitations: do not quantify concentration; do not detect all analogs equally; a negative result is not a guarantee of safety
- States that have removed FTS from drug paraphernalia statutes: most; some states still classify FTS as illegal

### Needle/Syringe Programs (NSPs)

Also called syringe services programs (SSPs) or needle exchange programs.

- Reduce HIV transmission by 50%+ among people who inject drugs
- Reduce hepatitis C incidence by 21-80%
- Entry point for healthcare services: many SSPs offer wound care, STI testing, naloxone, hepatitis A/B vaccination, hepatitis C treatment, and linkage to SUD treatment
- Do NOT increase drug use — multiple systematic reviews confirm
- CDC and SAMHSA support SSPs as evidence-based public health interventions

### Supervised Consumption Sites (Safe Injection Facilities)

Medically supervised facilities where people can use pre-obtained drugs under the observation of trained staff.
- Prevent overdose deaths (no deaths have occurred in a supervised consumption site)
- Provide point-of-care services: wound care, HIV/HCV testing, naloxone
- Operational in Canada (since 2003), Europe, and Australia
- United States: first officially sanctioned sites opened in New York City (2021)
- Federal legality remains contested; Department of Justice has not pursued charges under harm reduction rationale

### Motivational Interviewing (MI)

MI is a person-centered, directive counseling approach to elicit behavior change by exploring and resolving ambivalence.

**OARS core skills:**

| Skill | Description |
|-------|-------------|
| Open-ended questions | Invite elaboration; "What brings you in today?" rather than "Are you using drugs?" |
| Affirmations | Acknowledge strengths and positive steps; builds therapeutic alliance |
| Reflective listening | Reflect back content and emotion; demonstrates understanding without judgment |
| Summaries | Periodic summaries collect and link change talk; reinforce momentum |

**Stages of Change (Transtheoretical Model):**
- Precontemplation: not yet considering change; not recognizing problem
- Contemplation: ambivalent; aware of problem; considering change but not committed
- Preparation: intending to change within 30 days; taking small steps
- Action: actively modifying behavior; requires support and skills
- Maintenance: sustaining change beyond 6 months; relapse prevention focus
- Relapse: return to prior behavior; normalize and re-engage

---

## Neonatal Opioid Withdrawal Syndrome (NOWS)

### Background

Neonatal Opioid Withdrawal Syndrome (NOWS) — formerly Neonatal Abstinence Syndrome (NAS) — occurs in newborns exposed to opioids in utero. Buprenorphine and methadone are the recommended treatments for OUD during pregnancy (untreated OUD during pregnancy poses greater risks than MOUD).

Incidence has grown significantly with the opioid epidemic; occurs in approximately 6 per 1,000 hospital births in the United States.

### Finnegan Neonatal Abstinence Scoring System

A 21-item scoring system assessing three body systems:

**CNS Signs:**
- High-pitched cry, continuous cry
- Sleep (less than 1 hour, less than 2 hours, less than 3 hours after feeding)
- Hyperactive Moro reflex
- Tremors when disturbed (mild, moderate-to-severe)
- Tremors when undisturbed (mild, moderate-to-severe)
- Increased muscle tone
- Excoriation (knees, face)
- Myoclonic jerks
- Generalized convulsions

**Metabolic/Vasomotor/Respiratory:**
- Sweating
- Fever (37.2-38.3 C, >38.4 C)
- Frequent yawning (>3-4 times/scoring interval)
- Mottling
- Nasal stuffiness
- Sneezing (>3-4 times/scoring interval)
- Nasal flaring
- Respiratory rate (60-80/min, >80/min with retractions)

**GI Signs:**
- Excessive sucking
- Poor feeding
- Regurgitation
- Projectile vomiting
- Stools (loose, watery)

**Scoring intervals:** Every 4 hours (may increase to every 2 hours if score is high).

**Treatment threshold:** Score 8 or higher on three consecutive assessments, or score 12 or higher on two consecutive assessments (varies by protocol).

### Non-Pharmacological Treatment (First-Line)

- Rooming-in with mother (reduces severity scores and need for pharmacotherapy)
- Low-stimulation environment: dim lighting, quiet room, minimal handling
- Swaddling and gentle rocking
- Non-nutritive sucking
- Breastfeeding: encouraged if mother is on stable MOUD and not using illicit drugs or contraindicated substances; breastmilk contains small amounts of buprenorphine/methadone that may ease withdrawal

### Pharmacological Treatment for NOWS

**Morphine (most widely used)**
- Starting dose: 0.02-0.05mg/kg PO every 3-4 hours
- Titrate up by 20% increments if scores remain elevated
- Wean by 10% of peak dose every 24-48 hours when scores stabilize
- Typical hospital stay: 2-4 weeks

**Buprenorphine sublingual (increasingly preferred)**
- Starting dose: approximately 5.3-15.9 mcg/kg/day divided every 8 hours
- Multiple RCTs demonstrate shorter hospital stays than morphine (median 15 vs. 28 days)
- Administered as sublingual drops
- More rapid weaning possible

**Methadone (alternative)**
- Used in some centers; long half-life simplifies dosing
- 0.05-0.1mg/kg PO every 12-24 hours

**Phenobarbital (adjunct)**
- 16-20mg/kg IV/PO loading dose, then 5mg/kg/day maintenance
- Indicated for refractory NOWS or maternal polysubstance use (especially with benzodiazepines or alcohol) where neonatal CNS irritability is multifactorial
- Not first-line opioid treatment

---

## Co-Occurring Disorders (Dual Diagnosis)

### Epidemiology

- Approximately 50-60% of individuals with a SUD meet criteria for at least one co-occurring psychiatric disorder
- Approximately 45-50% of individuals with a serious mental illness (SMI) have a co-occurring SUD
- The combination worsens outcomes for both disorders if treated separately
- Integrated treatment (addressing both simultaneously in one setting) is the evidence-based standard

### Common Co-Occurring Disorder Combinations

| Substance | Common Co-Occurring Disorders |
|-----------|------------------------------|
| Alcohol | Major depressive disorder, anxiety disorders, PTSD, bipolar disorder |
| Opioids | Depression, PTSD, chronic pain, anxiety |
| Stimulants | Bipolar disorder, ADHD, schizophrenia spectrum (in chronic methamphetamine use) |
| Cannabis | Anxiety disorders, depression, psychotic disorders |
| Benzodiazepines | Generalized anxiety disorder, panic disorder, insomnia |

### Assessment Considerations

- Primary vs. substance-induced disorder: psychiatric symptoms during active intoxication or acute withdrawal may resolve with abstinence; a minimum observation period of 2-4 weeks of abstinence helps clarify
- PTSD and SUD: PTSD symptoms (hyperarousal, insomnia, nightmares) often drive substance use; must treat PTSD concurrently or SUD treatment fails
- Suicidality: elevated risk at all stages — active use, withdrawal, early recovery; assess at every contact

---

### Depression and SUD

**Selective serotonin reuptake inhibitors (SSRIs):**
- First-line for comorbid depression; safe in SUD
- Sertraline, fluoxetine, escitalopram — comparable efficacy
- 2-4 week onset; set expectations

**Bupropion:**
- Dual-action (norepinephrine + dopamine); useful when fatigue/anhedonia predominate
- Also indicated for smoking cessation (Wellbutrin/Zyban)
- Contraindicated: seizure disorder, eating disorders (anorexia/bulimia), abrupt alcohol/BZD withdrawal, MAOI use
- Reasonable choice when stimulant abstinence is goal (dopaminergic support)

**Mirtazapine:**
- Alpha-2 antagonist; potent antihistamine effects → improves insomnia and appetite
- Useful in opioid or stimulant withdrawal where insomnia and anorexia are prominent
- No serotonin syndrome risk with standard opioid combinations (no serotonergic mechanism)

**TCAs:** Effective but high overdose lethality — avoid or use with caution in active SUD

---

### PTSD and SUD

PTSD and SUD are highly comorbid; trauma history is present in majority of patients in addiction treatment.

**Self-medication hypothesis:** Patients with PTSD use substances to manage hyperarousal, nightmares, and emotional dysphoria — substances provide short-term relief but worsen PTSD over time.

**Evidence-based treatment for PTSD + SUD:**
- Seeking Safety: integrated cognitive-behavioral treatment for PTSD and SUD; does not require prior abstinence; widely studied
- Prolonged Exposure (PE): adapted for SUD populations; can be initiated during active SUD
- Cognitive Processing Therapy (CPT): effective for PTSD; adaptable to SUD setting

**Pharmacotherapy:**
- Prazosin: alpha-1 blocker; reduces PTSD nightmares and sleep disruption; 1-15mg QHS; effective and well-tolerated
- SSRIs (sertraline, paroxetine): FDA-approved for PTSD; treat both PTSD and comorbid depression
- Avoid benzodiazepines for PTSD: increase avoidance, worsen outcomes, high dependence liability in this population; not recommended by VA/DoD PTSD guidelines

---

### ADHD and SUD

ADHD is 5-10 times more prevalent among adults with SUD than in the general population. ADHD is a significant risk factor for SUD development, particularly stimulant use disorder.

**Key clinical challenge:** Stimulant medications are effective for ADHD but have abuse potential.

**Assessment:** Confirm ADHD diagnosis (rule out stimulant intoxication, mood disorder, PTSD as confounders); obtain collateral history; review academic/occupational records.

**Non-stimulant ADHD treatment preferred first in SUD:**

| Medication | Mechanism | Dose | Notes |
|-----------|----------|------|-------|
| Atomoxetine (Strattera) | Selective NRI | 40-100mg daily | No abuse potential; 4-6 week onset; hepatotoxicity (rare) |
| Viloxazine (Qelbree) | Selective NRI | 100-400mg daily | FDA-approved for ADHD; less studied in SUD |
| Bupropion (Wellbutrin) | NRI + weak DRI | 150-300mg daily | Off-label for ADHD; also treats depression and aids smoking cessation |
| Guanfacine ER (Intuniv) | Alpha-2 agonist | 1-4mg daily | FDA-approved ADHD; also reduces cravings/impulsivity in some studies |
| Clonidine (Kapvay) | Alpha-2 agonist | 0.1-0.4mg daily | FDA-approved ADHD; also treats opioid withdrawal symptoms |

**Stimulant ADHD medications in SUD:**
- Consider after non-stimulant trial fails AND SUD is in stable remission
- Use long-acting, non-chewable, abuse-deterrent formulations
- Lisdexamfetamine (Vyvanse): prodrug; requires enzymatic conversion to active amphetamine in gut; lower abuse potential by snorting/injection
- Osmotic methylphenidate (Concerta): OROS delivery system deters extraction
- Close monitoring required: random urine drug screens, prescription monitoring database review, prescribed dose tracking, regular follow-up

---

## Clinical Considerations and Special Populations

### Chronic Pain and OUD

The intersection of chronic pain and OUD is clinically challenging. Both require treatment; neither should be withheld.

**Principles:**
- MOUD (buprenorphine, methadone) provides analgesic effect at appropriate doses — do not withhold based on pain concern
- Buprenorphine is FDA-approved for pain (Belbuca buccal film, Butrans transdermal)
- For patients on buprenorphine who need acute pain management: maximize buprenorphine dose (analgesia); add non-opioid analgesics (NSAIDs, acetaminophen, gabapentin, ketamine); regional anesthesia is preferred
- If full opioid agonists are required (major surgery), do not discontinue buprenorphine; add additional opioid on top
- Methadone addresses both OUD and pain (q8h dosing for pain; once daily for OUD)

### Pregnancy and SUD

**Opioid use disorder in pregnancy:**
- MOUD is recommended over detoxification in pregnancy; detoxification associated with high relapse rates and worse fetal outcomes
- Buprenorphine (mono formulation — without naloxone) and methadone are both acceptable; buprenorphine associated with less severe NOWS
- Avoid naltrexone in pregnancy (insufficient safety data; if fetal opioid exposure occurs due to relapse while on naltrexone, precipitated withdrawal risk)
- Expect dose increases in third trimester (increased volume of distribution, altered metabolism)

**Alcohol use disorder in pregnancy:**
- No safe level of alcohol in pregnancy
- Fetal alcohol spectrum disorders (FASD): ranging from fetal alcohol syndrome to alcohol-related neurodevelopmental disorder
- Thiamine supplementation recommended
- Benzodiazepines for severe withdrawal: risk-benefit favors treatment; neonatal BZD withdrawal possible

### Hepatitis C and SUD

- People who inject drugs account for >70% of new hepatitis C infections
- Direct-acting antivirals (DAAs) achieve >95% cure rate; can be prescribed during active drug use
- Reinfection is possible with continued injection; harm reduction education essential
- MOUD significantly reduces injection-related risk behaviors and HCV transmission
- Integrated HCV treatment in addiction settings is effective

### HIV and SUD

- People who inject drugs account for approximately 10% of new HIV diagnoses in the US
- Syringe services programs reduce HIV transmission
- Pre-exposure prophylaxis (PrEP): highly effective; should be offered to people who inject drugs
- MOUD and retention in SUD treatment associated with HIV medication adherence
- HIV medications and MOUD interactions: multiple pharmacokinetic interactions; consult pharmacy/ID

---

## Reference Tables Summary

### MOUD Comparison at a Glance

| Parameter | Buprenorphine | Methadone | Naltrexone (XR) |
|-----------|--------------|-----------|-----------------|
| Mechanism | Partial mu-agonist | Full mu-agonist | Full antagonist |
| Setting | Office-based; any DEA prescriber | Federally licensed OTP only | Office-based; any prescriber |
| Formulations | SL, buccal, injectable, implant | Oral liquid (OTP); tablets | IM injectable; oral |
| Initiation | Requires withdrawal (or Bernese) | Flexible | Requires full opioid clearance |
| Diversion risk | Moderate | Lower (observed dosing) | None |
| Overdose risk | Low (ceiling effect) | Higher (accumulation) | None (opioid use after can overdose) |
| Hepatic metabolism | Extensive (CYP3A4) | Extensive (CYP3A4/2D6) | Moderate (CYP2E1; NTX-diol) |
| Pregnancy | Acceptable (mono product) | Acceptable | Insufficient safety data; avoid |
| Best for | Most patients; outpatient; pregnant | Complex patients; pregnant; high-dose use | Highly motivated; post-detox; legal requirements |

### Key Scoring Systems in Addiction Medicine

| Tool | Substance | Purpose | Threshold for Action |
|------|-----------|---------|---------------------|
| AUDIT-C | Alcohol | Screening | 3+ men; 2+ women |
| CIWA-Ar | Alcohol | Withdrawal severity | 10+ treat; 18+ aggressive BZD |
| CAGE | Alcohol | Screening | 2+ significant |
| DAST-10 | Drugs (excl. alcohol) | Screening | 3+ intervention |
| COWS | Opioids | Withdrawal severity / bup induction | 8+ for traditional induction |
| Finnegan/NOWS | Opioids (neonatal) | NOWS severity and treatment need | 8+ three consecutive assessments |
| FTND | Nicotine | Dependence severity | 6+ high dependence |

---

*End of Drug Addiction Knowledge Base*
*For RAG ingestion: each ## section is a primary chunk boundary; ### sections are secondary boundaries.*
*Version 1.0 — compiled for Zia Venture Group AI Stack, Open WebUI RAG system.*
