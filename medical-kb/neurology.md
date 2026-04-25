# Neurology Knowledge Base

**Domain:** Clinical Neurology  
**Scope:** Seizure disorders, headache, movement disorders, demyelinating disease, dementia, neuromuscular disease, stroke, coma, CNS infections, neuro-oncology, sleep, autonomic, and peripheral nervous system  
**Intended use:** Open WebUI RAG (chunk size 1500, overlap 200, Top K 5)

---

## Seizures and Epilepsy

### Status Epilepticus

**Definition:** Continuous seizure activity lasting >5 minutes, OR two or more discrete seizures without full return to baseline consciousness between them.

**Why 5 minutes:** Experimental and clinical data show that seizures lasting >5 minutes rarely self-terminate; neuronal injury begins and benzodiazepines remain highly effective at this threshold.

**Phases and Treatment Timeline**

| Time Window | Phase | Action |
|---|---|---|
| 0-5 min | Premonitory / Stabilization | ABCs, O2, IV access, glucose check, thiamine 100mg IV before glucose if alcoholism suspected |
| 0-5 min | First benzodiazepine | Lorazepam 0.1mg/kg IV (max 4mg single dose); repeat once if no IV access use midazolam 10mg IM (>40kg) or 5mg IM (13-40kg) — RAMPART trial showed IM midazolam non-inferior to IV lorazepam for prehospital SE, with higher rate of seizure termination before ED arrival |
| 5-20 min | Urgent control | Second benzodiazepine dose if not already given; prepare 2nd-line agents |
| 20-40 min | Established SE | Fosphenytoin 20 PE/kg IV at 150 PE/min (preferred over phenytoin — water soluble, less cardiac toxicity), OR levetiracetam 60mg/kg IV (max 4500mg) over 10 min, OR valproate 40mg/kg IV (max 3000mg) over 10 min — ESETT trial (2019): all three agents equivalent in efficacy (~47% cessation) and safety |
| 40-60 min | Refractory SE | Anesthetic infusion + intubation + continuous EEG monitoring: propofol 2mg/kg IV bolus then 1-12mg/kg/hr, OR midazolam 0.2mg/kg IV load then 0.1-2mg/kg/hr, OR pentobarbital 5-15mg/kg load then 0.5-3mg/kg/hr (titrate to burst suppression) |
| >60 min | Super-refractory SE | Ketamine infusion (1-5mg/kg/hr), inhaled isoflurane, ketogenic diet, electroconvulsive therapy, therapeutic hypothermia, surgical resection, vagus nerve stimulation |

**EEG goals in refractory SE:** Burst suppression with suppression ratio 50-80% for anesthetic agents (controversial — seizure suppression endpoint vs burst suppression; consult epileptologist).

**Nonconvulsive status epilepticus (NCSE):** Always consider in comatose patients without obvious motor activity; continuous EEG mandatory in altered sensorium post-convulsive SE or unexplained encephalopathy in ICU.

---

### Epilepsy Classification and Diagnosis

**2017 ILAE Classification — Seizure Types:**

Focal seizures (onset in one hemisphere network):
- Focal aware (previously simple partial)
- Focal impaired awareness (previously complex partial)
- Focal to bilateral tonic-clonic

Generalized seizures (onset in bilateral networks from the start):
- Absence (typical vs atypical)
- Myoclonic
- Tonic
- Atonic (drop attacks)
- Tonic-clonic (GTCS)
- Clonic

Unknown onset: applies when insufficient information.

**Epilepsy Syndromes — Key Examples**

| Syndrome | Onset Age | Seizure Types | EEG | Notes |
|---|---|---|---|---|
| Childhood absence epilepsy (CAE) | 4-10 yr | Typical absence (3Hz spike-wave) | 3Hz generalized | Good prognosis; usually remits; ethosuximide first-line |
| Juvenile absence epilepsy (JAE) | 10-17 yr | Absence + occasional GTCS | 3-4Hz spike-wave | Less complete remission than CAE |
| Juvenile myoclonic epilepsy (JME) | 12-18 yr | Morning myoclonus + GTCS + absence | 4-6Hz polyspike-wave, photosensitivity | Lifelong treatment usually needed; avoid sleep deprivation, alcohol |
| Lennox-Gastaut syndrome (LGS) | 1-8 yr | Multiple types including atonic | Slow spike-wave <2.5Hz | Severe, drug-resistant; rufinamide, clobazam, cannabidiol |
| Dravet syndrome | First year | Febrile hemiclonic then intractable | Normal early | SCN1A mutation; avoid sodium channel blockers; fenfluramine, stiripentol |
| Temporal lobe epilepsy (TLE) | Any | Focal impaired awareness with automatisms | Anterior temporal slowing/spikes | Most common focal epilepsy in adults; hippocampal sclerosis on MRI |

---

### Antiseizure Drug (ASD) Selection by Seizure Type

| Seizure Type | First-Line | Second-Line / Adjunct | Drugs to Avoid |
|---|---|---|---|
| Focal (all types) | Levetiracetam, lacosamide, lamotrigine, oxcarbazepine | Carbamazepine, eslicarbazepine, brivaracetam, zonisamide, perampanel | None specifically excluded |
| Generalized tonic-clonic | Valproate, lamotrigine, levetiracetam | Topiramate, zonisamide, perampanel | Carbamazepine, oxcarbazepine, gabapentin (may worsen) |
| Absence | Ethosuximide (pure absence), valproate, lamotrigine | Clobazam, levetiracetam, zonisamide | Carbamazepine, phenytoin, gabapentin, pregabalin, vigabatrin |
| Myoclonic | Valproate, levetiracetam, clonazepam | Zonisamide, topiramate, perampanel | Carbamazepine, lamotrigine (may worsen), phenytoin |
| Atonic / LGS | Valproate, clobazam, rufinamide | Topiramate, felbamate, cannabidiol | — |
| Infantile spasms (West syndrome) | ACTH, vigabatrin (TSC), prednisolone | Pyridoxine trial, topiramate | — |

**Key ASD Pharmacology Points:**
- Carbamazepine, phenytoin, phenobarbital, primidone, oxcarbazepine: strong CYP inducers — reduce efficacy of oral contraceptives, warfarin, antiretrovirals, many other medications; recommend non-hormonal or two methods of contraception
- Valproate: CYP inhibitor + UGT inhibitor — raises lamotrigine and phenobarbital levels; strongly teratogenic (neural tube defects 1-2%, major congenital malformations 6-10%, cognitive effects dose-dependent) — use only when other drugs fail in women of childbearing potential; mandatory REMS enrollment in US (VALREMS)
- Lamotrigine: titrate very slowly (skin rash including SJS risk with rapid titration or valproate co-administration); levels fall 40-60% during pregnancy — monitor levels and increase dose; start at 25mg every other day if on valproate
- Topiramate: cognitive side effects ("dopamax"), weight loss, kidney stones (carbonic anhydrase inhibition), glaucoma (acute angle closure), oligohidrosis/hyperthermia in children; teratogen (oral cleft risk)
- Levetiracetam: minimal drug interactions, renal clearance, no titration requirement; behavioral side effects (irritability, aggression in ~10%) — can pretreat with pyridoxine; first-line in pregnancy (limited teratogenicity data but widely used)
- Phenytoin: zero-order kinetics above therapeutic range — small dose increments cause large level changes; gingival hyperplasia, hirsutism, nystagmus, ataxia, peripheral neuropathy, osteoporosis

**Therapeutic Drug Monitoring (Trough Levels)**

| Drug | Target Range | Notes |
|---|---|---|
| Phenytoin | 10-20 mcg/mL total; 1-2 mcg/mL free | Free level essential in hypoalbuminemia; corrected total = measured / (0.2 x albumin + 0.1) |
| Carbamazepine | 4-12 mcg/mL | Auto-induction — levels fall after first weeks; 10,11-epoxide active metabolite |
| Valproate | 50-100 mcg/mL | Wide range; higher levels (>80) for generalized epilepsy |
| Phenobarbital | 20-40 mcg/mL | Long half-life; loading dose possible |
| Lamotrigine | 3-14 mcg/mL | Must monitor in pregnancy |
| Oxcarbazepine | 12-24 mcg/mL (as MHD metabolite) | — |
| Levetiracetam | 12-46 mcg/mL | Less critical clinically |

**Pregnancy and Epilepsy:**
- Folate supplementation: 4mg/day starting ≥1 month before conception and throughout pregnancy for all women on ASDs
- Safest ASDs in pregnancy: lamotrigine and levetiracetam have best safety data; avoid valproate; avoid polytherapy when possible
- Breastfeeding: generally safe; monitor infant for sedation with phenobarbital, benzodiazepines; avoid primidone
- Seizure-free interval before driving: varies by state (typically 3-12 months); most US states require 6 months; physicians often have reporting obligations — know state law

**Drug-Resistant Epilepsy:** Failure of two appropriate and tolerated ASDs; refer to epilepsy center for video-EEG monitoring, surgical evaluation (temporal lobectomy most successful — 60-70% seizure freedom in TLE), responsive neurostimulation (RNS), vagus nerve stimulation (VNS), deep brain stimulation (anterior thalamic nucleus, FDA-approved)

---

## Headache Disorders

### Migraine

**ICHD-3 Diagnostic Criteria:**
- At least 5 attacks fulfilling B-D
- B: 4-72 hours untreated
- C: At least 2 of: unilateral, pulsating, moderate-severe intensity, aggravated by routine activity
- D: At least 1 of: nausea/vomiting, photophobia AND phonophobia
- Not better explained by another diagnosis

**Migraine with Aura:**
- Fully reversible visual, sensory, language, motor, brainstem, or retinal symptoms
- Each symptom spreads/develops over ≥5 minutes
- Each symptom lasts 5-60 minutes
- At least one aura symptom is unilateral
- Headache onset within 60 minutes of aura (or during aura)
- Common aura: visual (scintillating scotoma, fortification spectra / Teichopsia — expanding arc of flickering lights), sensory (perioral + hand "cheiro-oral"), language (expressive aphasia)
- Hemiplegic migraine (familial/sporadic): motor aura; FHM1 = CACNA1A, FHM2 = ATP1A2, FHM3 = SCN1A; avoid triptans in hemiplegic and basilar-type migraine
- Migraine aura without headache ("acephalgic migraine"): consider TIA in new-onset older patients

**Acute / Abortive Treatment**

| Medication | Dose | Class | Notes |
|---|---|---|---|
| Sumatriptan | 50-100mg PO; 6mg SQ; 20mg nasal | Triptan (5-HT1B/1D) | SQ fastest onset (10-15 min); SQ preferred for severe/vomiting |
| Rizatriptan | 10mg PO (5mg with propranolol) | Triptan | Oral disintegrating wafer available |
| Eletriptan | 40-80mg PO | Triptan | Most potent; higher lipophilicity |
| Frovatriptan | 2.5mg PO | Triptan | Long half-life (26h) — best for menstrual migraine; slower onset |
| Almotriptan | 12.5mg PO | Triptan | Favorable tolerability |
| Triptan contraindications | — | — | CAD, prior MI/stroke/TIA, uncontrolled HTN, hemiplegic/basilar migraine, MAOI use within 14 days, pregnancy (relative) |
| Ubrogepant | 50-100mg PO | CGRP receptor antagonist (gepant) | No vasoconstriction; safe with CVD; re-dose at 2h if needed |
| Rimegepant | 75mg PO (ODT) | CGRP receptor antagonist (gepant) | Dual acute + preventive (every other day) |
| Lasmiditan | 50-100-200mg PO | 5-HT1F agonist (ditan) | No vasoconstriction; CNS sedation/dizziness — NO driving or operating machinery for 8 hours |
| Naproxen sodium | 550-825mg PO | NSAID | Best NSAID evidence in migraine |
| Ketorolac | 30-60mg IM/IV | NSAID | IV/IM for emergency use |
| DHE (dihydroergotamine) | 1mg IV/IM/SQ; 4mg nasal (Migranal) | Ergot alkaloid | CI: similar to triptans; do not combine ergot + triptan (24-48h washout); effective for status migrainosus |
| Prochlorperazine | 10mg IV | Dopamine antagonist | Superior to opioids in ED; akathisia common — pretreat with diphenhydramine |
| Metoclopramide | 10mg IV | Dopamine antagonist | Prokinetic + antiemetic; tardive dyskinesia with chronic use |

**Emergency Department / Status Migrainosus Protocol:**
1. Prochlorperazine 10mg IV + diphenhydramine 25mg IV (akathisia prophylaxis)
2. Ketorolac 30mg IV
3. Magnesium sulfate 2g IV over 15 min (especially effective with aura; also IV in pregnancy when triptans avoided)
4. Dexamethasone 10mg IV (reduces 24-72h recurrence/rebound — single dose)
5. IV DHE 0.5-1mg q8h x3 if above fails
6. Avoid opioids (worsen outcomes, increase medication overuse, risk of ED opioid dependency)

**Migraine Preventive Therapy**

Indications: ≥4 migraine headache days/month, OR severely disabling migraines, OR acute medication overuse, OR hemiplegic/basilar migraine, OR migraine with prolonged aura

| Agent | Dose | Level of Evidence | Notes |
|---|---|---|---|
| Propranolol | 40-160mg/day (divided) | A | Avoid in asthma, depression, diabetes |
| Metoprolol | 50-200mg/day | A | — |
| Topiramate | 25-200mg/day | A | Weight loss, cognitive SE; teratogen |
| Valproate / divalproex | 500-1500mg/day | A | Teratogen; avoid reproductive-age women; LFTs |
| Amitriptyline | 10-100mg QHS | B | Sedation, anticholinergic SE; also for comorbid depression/insomnia |
| Venlafaxine | 75-150mg/day | B | Better tolerated than TCAs; also for anxiety |
| Candesartan | 16mg/day | B | Good tolerability; anti-CGRP independent mechanism |
| Magnesium glycinate | 400-600mg/day | B | Safest in pregnancy; especially for aura |
| Riboflavin (B2) | 400mg/day | B | Very safe; urine turns orange |
| Coenzyme Q10 | 300mg/day | C | — |
| Erenumab (Aimovig) | 70-140mg SQ monthly | A | Anti-CGRP receptor mAb; constipation |
| Fremanezumab (Ajovy) | 225mg monthly or 675mg quarterly | A | Anti-CGRP ligand mAb |
| Galcanezumab (Emgality) | 240mg load x2 then 120mg monthly | A | Anti-CGRP ligand mAb; also cluster headache |
| Eptinezumab (Vyepti) | 100-300mg IV q3 months | A | Fastest onset (IV) |
| Rimegepant (Nurtec) | 75mg every other day | A | Oral gepant — dual acute + preventive |
| Atogepant (Qulipta) | 10-60mg daily | A | Oral gepant — preventive only |
| Onabotulinumtoxin A (Botox) | 155-195 units IM q12 weeks | A | FDA-approved chronic migraine only (≥15 headache days/month, ≥8 migraine features); 31-39 injection sites per session |

**Medication Overuse Headache (MOH):**
- Criteria: headache ≥15 days/month + acute medication use ≥10 days/month (triptans, ergots, opioids, combination analgesics) or ≥15 days/month (simple analgesics) for >3 months
- Treatment: abrupt or gradual withdrawal (abrupt preferred for triptans/opioids except opioid dependence); bridge with naproxen or short steroid course; start preventive ASD; relapse rate 20-30% at 1 year
- Topiramate and CGRP mAbs are effective even during overuse (do not require withdrawal first)

**Menstrual Migraine:**
- Perimenstrual attacks (days -2 to +3 of menses); estrogen withdrawal trigger
- Prevention: frovatriptan 2.5mg BID x6 days perimenstrual, or naproxen 550mg BID, or transdermal estrogen patch (0.1mg) days -3 to +3

---

### Cluster Headache

**Clinical Features:**
- Excruciating unilateral periorbital/temporal pain, 15-180 minutes
- Frequency: 1-8 attacks/day during cluster period (weeks to months); episodic (periods with remission >3 months/year) vs chronic
- Ipsilateral autonomic features: conjunctival injection, lacrimation, nasal congestion/rhinorrhea, miosis, ptosis, eyelid edema, forehead/facial sweating
- Restless agitation (pacing, rocking — contrasts with migraine stillness)
- Strong circadian/circannual pattern (often nocturnal, spring/fall)
- Alcohol triggers attacks during cluster period (not between)

**Acute Treatment:**
- 100% O2 at 12-15 L/min via non-rebreather mask x15-20 min — safest and most effective (NNT ~2); mechanism unclear; useful in elderly and CVD patients
- Sumatriptan 6mg SQ (fastest; 12mg max/24h) or 20mg nasal spray
- Zolmitriptan 5mg nasal spray
- Intranasal civamide or sphenopalatine ganglion (SPG) block (lidocaine soaked cotton tip applicator to posterior nasal wall)

**Preventive Treatment:**
- Verapamil 240-960mg/day (divided TID) — first-line; ECG required before starting and with dose increases (AV block risk above 480mg); benefit within 2-3 weeks
- Prednisone 60mg/day tapered over 3 weeks — rapid bridge while verapamil loading; highly effective short-term
- Lithium 300mg TID (levels 0.6-1.0 mEq/L) — for chronic cluster; thyroid/renal monitoring
- Melatonin 10mg QHS — mild evidence; very safe
- Galcanezumab 300mg SQ monthly (3 consecutive injections at cluster onset) — FDA-approved episodic cluster headache
- Greater occipital nerve (GON) block — 2mL methylprednisolone + 2mL lidocaine; rapid response in cluster period

**SUNCT and SUNA (Short-lasting Unilateral Neuralgiform headache):**
- Very brief attacks 5-240 seconds; conjunctival injection and tearing (SUNCT), autonomic (SUNA)
- Often refractory; lamotrigine, topiramate most effective
- Rule out posterior fossa lesion (MRI mandatory — often secondary)

---

### Trigeminal Neuralgia

- Unilateral lancinating shocks, V2/V3 distribution most common, triggered by light touch (eating, talking, cold wind)
- Classic TN: neurovascular compression of CN V (MRI with FIESTA/CISS sequence to identify)
- Symptomatic TN: MS plaque, tumor — evaluate young patients or bilateral cases
- Treatment:
  - First-line: carbamazepine 200-1200mg/day (NNT ~2; monitor CBC, LFTs, Na; HLA-B*1502 before use in Asian patients — SJS risk); oxcarbazepine (better tolerated)
  - Second-line: lamotrigine, baclofen, gabapentin, pregabalin
  - Surgical: microvascular decompression (MVD — most durable, best outcome in classic TN), percutaneous rhizotomy (glycerol, balloon, radiofrequency — faster, good for elderly), stereotactic radiosurgery (Gamma Knife — delayed response 4-6 weeks)

---

## Parkinson's Disease and Related Disorders

### Parkinson's Disease

**Pathophysiology:**
- Loss of dopaminergic neurons in substantia nigra pars compacta (SNpc) with relative sparing of ventral tegmental area
- Alpha-synuclein misfolding and aggregation into Lewy bodies and Lewy neurites
- Braak staging: olfactory bulb/brainstem pathology precedes SNpc involvement (explains premotor symptoms)
- Dopamine depletion in striatum → loss of direct pathway facilitation + increased indirect pathway inhibition → reduced thalamocortical activation → motor slowing

**Clinical Features:**

Motor (TRAP mnemonic):
- Tremor: resting (4-6 Hz); pill-rolling; asymmetric onset; reduces with action/posture initially
- Rigidity: cogwheel (superimposed tremor) or lead-pipe; tested with passive joint movement; Froment's maneuver (contralateral limb activation enhances rigidity)
- Akinesia/Bradykinesia: slowness, reduced amplitude (finger tapping, foot tapping, handwriting micrographia), hypomimia (masked facies), hypophonia, reduced arm swing
- Postural instability: late feature; pull test (examiner pulls shoulders backward — >2 steps = abnormal retropulsion); predisposes to falls

Nonmotor (often precede motor by years):
- Anosmia (>90% — early marker)
- REM sleep behavior disorder (RBD) — acts out dreams; 80% will develop synucleinopathy
- Constipation (decades before motor onset)
- Depression and anxiety (40-50%)
- Orthostatic hypotension
- Urinary urgency/nocturia
- Cognitive impairment and dementia (mild cognitive impairment in 30% at diagnosis; dementia in 80% by 20 years)
- Psychosis (hallucinations, delusions — especially with advanced disease and dopaminergic therapy)
- Pain and fatigue

**Diagnosis:** Clinical; brain MRI to exclude structural causes; DaTscan (dopamine transporter SPECT) — reduces dopamine transporter in PD/DLB/atypical Parkinson's but NOT in ET, PSP (variable), drug-induced Parkinsonism, or DRD; useful when diagnosis uncertain

**Red Flags for Atypical Parkinsonism (caution against PD diagnosis):**

| Feature | Suggests |
|---|---|
| Early falls (within 1 year) | PSP |
| Early severe dysautonomia | MSA-P |
| Cerebellar ataxia | MSA-C |
| Levator palpebrae supranuclear gaze palsy (downward) | PSP (Richardson's) |
| Alien limb phenomenon, cortical sensory loss | CBD |
| Early dementia (within 1 year) | DLB |
| Antecollis, cerebellar dysarthria | MSA |
| Poor or no levodopa response | All atypical PS |
| Symmetric onset | Drug-induced, vascular, atypical |

**Pharmacotherapy**

| Drug Class | Agent | Dose | Key Points |
|---|---|---|---|
| Levodopa/carbidopa | Immediate release (IR) | Start 25/100 TID with food | Most effective ASD; gold standard; carbidopa inhibits peripheral dopa decarboxylase (prevents nausea, reduces levodopa dose needed) |
| Levodopa/carbidopa | Controlled release (CR/Rytary) | Variable | More sustained levels; Rytary (extended release beads) reduces off time |
| Levodopa/carbidopa | Enteral infusion (Duopa) | Pump via PEG-J | Advanced PD with refractory motor fluctuations |
| Dopamine agonists | Pramipexole | 0.375-4.5mg/day (ER) | Renal dosing; less motor complications than levodopa; impulse control disorders |
| Dopamine agonists | Ropinirole | 0.75-24mg/day (ER) | Similar to pramipexole; hepatic metabolism |
| Dopamine agonists | Rotigotine patch | 2-8mg/24h | Continuous delivery; skin reactions |
| Dopamine agonists | Apomorphine SQ | 2-6mg per injection | Rapid rescue for severe off episodes; continuous infusion pump option; severe nausea — premedicate with trimethobenzamide |
| MAO-B inhibitors | Rasagiline | 1mg daily | Mild symptomatic effect; possible neuroprotection (ADAGIO trial — controversial); avoid meperidine, tramadol, SNRIs, TCAs, SSRIs (serotonin syndrome risk) |
| MAO-B inhibitors | Selegiline | 5mg BID (with breakfast/lunch — avoid insomnia) | Metabolized to amphetamine; drug interactions as above |
| MAO-B inhibitors | Safinamide | 50-100mg daily | Dual MAO-B + glutamate antagonism; add-on to levodopa |
| COMT inhibitors | Entacapone (Comtan) | 200mg with each levodopa dose | Extends levodopa t1/2; orange discoloration of urine; diarrhea |
| COMT inhibitors | Opicapone (Ongentys) | 50mg QHS | Once daily; no hepatotoxicity |
| COMT inhibitors | Tolcapone (Tasmar) | 100-200mg TID | Most potent; rare severe hepatotoxicity — LFTs q2-4 weeks x6 months then periodically; REMS program |
| Amantadine | Amantadine IR | 100mg BID-TID | Reduces dyskinesias; antiviral/glutamate mechanism; also mild PD benefit; SE: livedo reticularis, ankle edema, hallucinations, anticholinergic |
| Amantadine | Gocovri (ER) | 274mg QHS | FDA-approved for dyskinesias in PD; higher dose overnight achieves peak levels coinciding with morning "on" |
| Anticholinergics | Trihexyphenidyl, benztropine | Low dose | Useful for tremor-predominant young-onset PD; avoid in elderly (cognitive, urinary, constipation) |

**Motor Complication Management:**

Wearing-off (end-of-dose deterioration):
- Increase levodopa frequency (q3h instead of q4h)
- Switch to extended-release formulation (Rytary)
- Add COMT inhibitor (entacapone, opicapone)
- Add MAO-B inhibitor
- Add dopamine agonist
- Apomorphine SQ rescue injection

Dyskinesias (peak-dose, biphasic):
- Reduce individual levodopa dose (increase frequency if needed to maintain control)
- Add amantadine (IR or Gocovri)
- Consider DBS

On-off fluctuations (unpredictable):
- Continuous dopaminergic stimulation strategies (enteral levodopa infusion, continuous dopamine agonist infusion, DBS)

**Deep Brain Stimulation (DBS):**
- Targets: subthalamic nucleus (STN) — most common; globus pallidus interna (GPi) — better for dyskinesias
- Indications: motor fluctuations/dyskinesias not controlled by medications; >4 years disease duration; good levodopa response (predicts DBS response — except tremor which may respond even without levodopa response); no significant dementia (MMSE >24); no active psychiatric illness
- Benefits: ~50% reduction in off time; marked dyskinesia reduction; tremor control; may reduce medication doses
- Does NOT improve: cognitive symptoms, falls (axial symptoms), speech (may worsen), autonomic symptoms
- Stimulation can be adjusted non-invasively; battery lasts 3-5 years (rechargeable devices last longer)

**Nonmotor Management in PD:**

| Symptom | First-Line | Second-Line / Notes |
|---|---|---|
| Constipation | Macrogol (PEG laxative), fiber, hydration | Linaclotide, lubiprostone; avoid anticholinergics |
| Orthostatic hypotension | Compression stockings, increased salt/fluid, head-of-bed elevation | Midodrine 2.5-10mg TID, fludrocortisone 0.1-0.2mg/day, droxidopa 100-600mg TID |
| Urinary urgency | Mirabegron (beta-3 agonist — fewer anticholinergic effects on cognition) | Solifenacin; avoid oxybutynin in elderly/cognitive impairment |
| Depression | SSRIs (sertraline, escitalopram), SNRIs | Nortriptyline (also helps pain); avoid paroxetine with MAO-B inhibitors |
| Psychosis (hallucinations, delusions) | Remove offending drugs (anticholinergics, amantadine, dopamine agonists first, then COMT, then levodopa — minimize last) | Clozapine 12.5-50mg (most effective; ANC monitoring weekly x6mo then biweekly — agranulocytosis); quetiapine 25-100mg (less effective but ANC not required); pimavanserin (Nuplazid — 5-HT2A inverse agonist, no D2 blockade) |
| Dementia | Rivastigmine (FDA-approved for PDD) — patch preferred (less GI SE) | Donepezil, memantine; avoid anticholinergics |
| REM sleep behavior disorder | Clonazepam 0.5-1mg QHS | Melatonin 3-12mg QHS; safe sleeping environment |
| Excessive daytime sleepiness | Sleep hygiene, reduce dopamine agonist dose | Modafinil 100-200mg AM; caffeine |
| Sialorrhea (drooling) | Botulinum toxin injection into parotid/submandibular glands | Glycopyrrolate, ipratropium spray |

---

### Atypical Parkinsonism Syndromes

**Multiple System Atrophy (MSA):**
- MSA-P (Parkinson predominant): striatonigral degeneration; poor levodopa response
- MSA-C (cerebellar predominant): olivopontocerebellar atrophy; cerebellar ataxia + parkinsonism
- Both: severe autonomic failure (OH, urinary incontinence/retention, impotence), RBD, stridor (laryngeal dystonia — can cause sudden death); "hot cross bun" sign in pons on MRI
- Alpha-synuclein glial cytoplasmic inclusions
- Survival median 6-9 years; no disease-modifying treatment

**Progressive Supranuclear Palsy (PSP):**
- Richardson's syndrome (most common): early falls backward, vertical supranuclear gaze palsy (downgaze first), axial > appendicular rigidity, square wave jerks, pseudobulbar affect, cognitive impairment
- "Hummingbird sign" (midbrain atrophy) and "morning glory sign" on MRI
- Tau (4R tauopathy)
- No effective treatment; zolpidem may help eye movements; clonazepam for falls; SSRIs for pseudobulbar affect

**Corticobasal Degeneration (CBD):**
- Asymmetric limb apraxia and dystonia, alien limb phenomenon, cortical sensory loss (astereognosis, agraphesthesia), myoclonus, cognitive impairment
- 4R tauopathy; "hummingbird" may be seen
- Often presents as CBS (corticobasal syndrome) — same clinical picture, heterogeneous pathology (also seen with AD, PSP, FTLD)

**Drug-Induced Parkinsonism:**
- Antipsychotics (especially haloperidol, other typical D2 blockers), metoclopramide, prochlorperazine, reserpine, valproate, lithium
- Symmetric, subacute onset, no tremor (or postural > resting)
- DaTscan: normal (no presynaptic dopamine loss) — key distinguisher from PD
- Treatment: stop offending drug; reverses over weeks to months; may unmask underlying PD in some patients

---

## Multiple Sclerosis

### Diagnosis

**McDonald Criteria 2017:**
- Dissemination in space (DIS): ≥2 distinct CNS regions (periventricular, cortical/juxtacortical, infratentorial, spinal cord, optic nerve) — can be clinical or MRI
- Dissemination in time (DIT): ≥2 clinical attacks, OR simultaneous gadolinium-enhancing + non-enhancing lesions, OR new T2/enhancing lesion on follow-up MRI
- CSF OCBs (≥2 oligoclonal bands) + DIS alone = DIT (surrogate)

**Typical Presenting Syndromes (CIS — Clinically Isolated Syndrome):**
- Optic neuritis: monocular vision loss (often color before acuity), periorbital pain worse with eye movement, relative afferent pupillary defect (RAPD — Marcus Gunn pupil), central scotoma; ON + 2+ MRI lesions → 80-90% conversion to MS within 20 years
- Internuclear ophthalmoplegia (INO): impaired adduction ipsilateral eye + abducting nystagmus contralateral; bilateral INO in young adult = MS until proven otherwise (MLF demyelination)
- Transverse myelitis: bilateral motor/sensory/autonomic dysfunction below lesion level; partial (asymmetric) TM more typical of MS; short lesion (<3 vertebral segments) on MRI
- Cerebellar/brainstem syndrome: ataxia, dysarthria, vertigo, diplopia, nystagmus

**MS Mimics (key to exclude):**
- Neuromyelitis optica spectrum disorder (NMOSD): anti-AQP4 or anti-MOG antibodies; longitudinally extensive TM (≥3 segments), area postrema involvement (intractable hiccups/vomiting), bilateral simultaneous ON; NOT treated like MS (IFN-beta may worsen)
- Sarcoidosis, CNS vasculitis, Lyme disease, B12 deficiency, CADASIL, mitochondrial disease
- MOGAD (MOG antibody-associated disease): anti-MOG IgG; recurrent ON, ADEM, LETM; different from AQP4-NMOSD

**MRI Features of MS Lesions:**
- T2/FLAIR hyperintense; T1 hypointense ("black holes") = severe axonal loss
- Periventricular lesions perpendicular to corpus callosum ("Dawson's fingers") on sagittal FLAIR
- Juxtacortical (touching cortex), infratentorial (brainstem/cerebellum), spinal cord lesions
- Gadolinium enhancement = active inflammation (ring or open-ring); fades within 6-8 weeks

---

### MS Clinical Features and Symptoms

| Symptom | Mechanism | Treatment |
|---|---|---|
| Spasticity | Upper motor neuron (corticospinal tract) | Baclofen (oral 5-80mg/day; intrathecal pump for severe), tizanidine (hepatotoxic — LFTs), dantrolene, nabiximols (cannabis spray — UK/Canada), botulinum toxin (focal) |
| Fatigue | Multifactorial (axonal, cytokine, sleep, depression) | Amantadine 100mg BID, modafinil 100-200mg AM, methylphenidate; treat sleep disorders, depression |
| Uhthoff's phenomenon | Heat sensitivity of demyelinated axons | Cooling strategies (vest, fans), amantadine |
| Bladder urgency/frequency | Detrusor hyperreflexia | Oxybutynin, tolterodine, solifenacin, mirabegron; avoid in urinary retention |
| Bladder retention | Detrusor sphincter dyssynergia | Clean intermittent catheterization (CIC) — standard of care |
| Bowel dysfunction | Constipation > incontinence | Fiber, macrogol; bowel program; biofeedback |
| Neuropathic pain | Demyelinated spinothalamic pathways | Gabapentin, pregabalin, duloxetine, amitriptyline |
| Depression | Multifactorial | SSRIs (sertraline, escitalopram), cognitive behavioral therapy |
| Cognitive impairment | Cortical and white matter lesions | Cognitive rehabilitation; no pharmacologic benefit established |
| Walking impairment | Corticospinal demyelination | Dalfampridine (Ampyra) 10mg BID — K channel blocker, prolongs action potential; increases walking speed in ~35%; contraindicated with seizure history (threshold lowered), renal impairment |
| Trigeminal neuralgia | Pontine plaque at CN V REZ | Carbamazepine, oxcarbazepine (as primary TN) |
| Vertigo | Brainstem/vestibulocerebellular lesions | Meclizine, ondansetron; short course |
| Sexual dysfunction | Spinal cord + psychological | PDE5 inhibitors (erectile dysfunction), lubricants, counseling |
| Lhermitte's sign | C-spine demyelination | Reassure; carbamazepine for painful variant |

---

### MS Disease-Modifying Therapies (DMTs)

**Moderate Efficacy**

| Drug | Mechanism | Route | Key Side Effects |
|---|---|---|---|
| IFN beta-1a (Avonex, Rebif) | Immunomodulation (exact unknown) | IM weekly or SQ TIW | Flu-like symptoms (most common); injection site reactions; depression; liver enzyme elevation; leukopenia; neutralizing antibodies reduce efficacy |
| IFN beta-1b (Betaseron, Extavia) | Same | SQ every other day | Same as above; higher injection site reactions |
| Glatiramer acetate (Copaxone) | Altered peptide ligand; Th2 skewing | SQ daily or 3x/week | Injection site reactions, lipoatrophy; immediate post-injection reaction (flushing, palpitation, chest tightness — self-limiting <15min) |
| Dimethyl fumarate (Tecfidera, Vumerity) | Nrf2 pathway activation; lymphocyte reduction | Oral BID | GI (flushing, nausea, diarrhea — take with food; diminish over months); lymphopenia (PML risk if CD4 <200 or lymphocytes <0.5 x10^9/L prolonged) |
| Teriflunomide (Aubagio) | Inhibits DHODH (pyrimidine synthesis) — reduces T and B cell proliferation | Oral daily | Teratogen — REMS program; washout with cholestyramine 8g TID x11 days (accelerated) or 2 years spontaneous; alopecia (transient), GI, hepatotoxicity (LFTs), peripheral neuropathy |
| Siponimod (Mayzent) | S1P 1 and 5 receptor agonist | Oral daily | CYP2C9 genotype determines dose (CYP2C9*3/*3 = absolute CI); cardiac monitoring first dose (bradycardia); macular edema (ophthalmology before); pulmonary function |

**High Efficacy**

| Drug | Mechanism | Route/Frequency | Key Safety Concerns |
|---|---|---|---|
| Natalizumab (Tysabri) | Anti-alpha-4 integrin (blocks lymphocyte CNS entry) | IV q4 weeks | PML — JC virus reactivation; JC antibody index >1.5 + prior immunosuppression + >24 infusions = high risk (>1:50); suspend if JC seroconversion and high risk; IRIS on natalizumab withdrawal |
| Ocrelizumab (Ocrevus) | Anti-CD20 (B cell depletion) | IV 600mg q6 months | Infusion reactions (premedicate with methylprednisolone + antihistamine + acetaminophen); PML (rare); reduced immunoglobulin levels with prolonged use; COVID vaccination timing; hepatitis B reactivation screening; increased breast cancer risk signal |
| Ofatumumab (Kesimpta) | Anti-CD20 (B cell depletion) | SQ weekly x3 then monthly | Similar to ocrelizumab; SQ more convenient; injection site reactions |
| Ublituximab (Briumvi) | Anti-CD20 | IV q6 months | Similar; shorter infusion time (1h maintenance) |
| Alemtuzumab (Lemtrada) | Anti-CD52 (profound lymphocyte depletion, then immune reconstitution) | IV 5 days year 1, 3 days year 2; further courses if needed | Secondary autoimmunity: thyroid disease (30-40% — most common), ITP (thrombocytopenia — monthly CBC x48 months), anti-GBM nephropathy; infections; requires monthly monitoring x48 months after last course; limited to failed ≥2 DMTs in US |
| Cladribine (Mavenclad) | Purine analogue — selectively depletes lymphocytes | Oral short courses year 1 and year 2; then monitor for 2 more years | Lymphopenia (most significant — grade 3/4 risk); infections (viral reactivation — herpes zoster prophylaxis); teratogen; potential malignancy signal; no use year 3-4 (monitoring only) |
| Fingolimod (Gilenya) | S1P receptor modulator (first oral MS DMT) | Oral daily | First-dose bradycardia/AV block (6h monitoring required); macular edema; elevated liver enzymes; infections (VZV); PML (rare, post-natalizumab); teratogen |
| Ponesimod (Ponvory) | S1P1 agonist | Oral daily (14-day titration) | Similar to fingolimod; fewer cardiac effects; cardiac monitoring first dose |

**Treatment Strategy:**
- Escalation approach: start moderate efficacy → escalate if breakthrough activity
- Induction approach: high-efficacy therapy upfront in aggressive disease (high lesion burden, frequent relapses, early disability)
- High efficacy preferred for: ≥2 relapses/year, large lesion burden, disabling relapses, early motor/cerebellar involvement
- Pregnancy: stop DMTs before conception (exception: glatiramer acetate [low risk, often continued]); natalizumab can be continued through second trimester and restarted early postpartum to reduce rebound; leflunomide-derived teriflunomide metabolite persists — early washout essential

**Acute Relapse Management:**
- Methylprednisolone 1g IV daily x3-5 days — shortens relapse duration and severity; does NOT change long-term disability accumulation; oral equivalent (1.25g prednisone) non-inferior for ambulatory patients
- Plasma exchange (PLEX): 5-7 exchanges over 10-14 days; for severe steroid-refractory relapses (loss of vision, paraplegia) — 40-50% show significant recovery

---

## Dementia Syndromes

### Alzheimer's Disease (AD)

**Pathophysiology:**
- Amyloid cascade hypothesis: amyloid-beta (Abeta42) oligomers → plaques → tau hyperphosphorylation → neurofibrillary tangles → neurodegeneration → synaptic loss → clinical syndrome
- APOE genotype: APOE-e4 increases risk (heterozygous ~3-4x; homozygous ~12x); APOE-e2 protective
- Early-onset AD (<65 years): APP, PSEN1, PSEN2 mutations (autosomal dominant)
- Biomarkers: CSF (low Abeta42, elevated p-tau, elevated t-tau); amyloid PET (florbetapir, flutemetamol); tau PET; plasma phospho-tau217 (high sensitivity emerging blood biomarker)

**Clinical Stages:**
1. Preclinical AD: biomarker-positive, no symptoms
2. MCI due to AD: subjective and objective memory impairment, preserved daily function, biomarkers positive
3. Mild AD: memory + at least one other domain (language, visuospatial, executive); MMSE 20-26
4. Moderate AD: needs assistance with ADLs; MMSE 10-20
5. Severe AD: fully dependent; MMSE <10

**Key Features:** Memory loss (episodic > semantic early); word-finding difficulty; visuospatial impairment (getting lost); behavioral changes late; posterior cortical atrophy variant (visuospatial predominant); logopenic variant PPA (language)

**MRI:** Hippocampal and entorhinal cortex atrophy; parietal lobe involvement; hippocampal volume by visual rating scales (MTA score)

**Treatment:**

| Drug | Dose | Indication | Notes |
|---|---|---|---|
| Donepezil (Aricept) | 5mg x4 weeks then 10mg daily; 23mg available (modest additional benefit) | Mild-moderate-severe AD | AChEI; GI SE; bradycardia/syncope; nightmares; do not stop abruptly |
| Rivastigmine (Exelon) | Oral 1.5-6mg BID or patch 4.6-13.3mg/24h | Mild-moderate AD; also PDD | Patch better GI tolerance; nausea with dose increases |
| Galantamine (Razadyne) | 4-12mg BID ER or 8-24mg ER daily | Mild-moderate AD | Nicotinic acetylcholine receptor modulation in addition to AChEI; GI SE |
| Memantine (Namenda) | 5mg weekly titration to 10mg BID or 28mg ER daily | Moderate-severe AD (MMSE 3-14) | NMDA antagonist; modest benefit; SE: dizziness, headache; combine with AChEI |
| Lecanemab (Leqembi) | 10mg/kg IV q2 weeks | Early AD (MCI or mild dementia with amyloid confirmed) | Anti-amyloid monoclonal Ab; slows cognitive decline ~27% over 18 months (CLARITY AD trial); ARIA (amyloid-related imaging abnormalities) — ARIA-E (edema) and ARIA-H (microhemorrhages) — highest risk APOE-e4 homozygous; MRI monitoring required; FDA accelerated + regular approval |
| Donanemab (Kisunla) | 700mg q4 weeks (then 1400mg) until plaque clearance | Early AD | Anti-amyloid mAb; TRAILBLAZER-ALZ2; ARIA monitoring; FDA approved 2024 |

**Behavioral and Psychological Symptoms of Dementia (BPSD):**
- Non-pharmacological first: structured activities, caregiver education, environmental modification, music/art therapy
- Agitation/aggression: citalopram 10-20mg (safety data in AD); mirtazapine; low-dose risperidone or quetiapine (black box warning — increased mortality in elderly dementia patients — informed consent)
- Psychosis: pimavanserin (Nuplazid) 34mg daily — FDA-approved for Alzheimer's disease psychosis (5-HT2A inverse agonist; no D2 blockade)
- Depression: escitalopram, sertraline; avoid TCAs (anticholinergic)
- Sleep: melatonin, trazodone 25-50mg QHS; avoid benzodiazepines (fall risk, delirium)
- Avoid: benzodiazepines (unless acute dangerous agitation, short-term only), anticholinergics, first-generation antihistamines

---

### Vascular Dementia

- Second most common dementia; often overlaps with AD (mixed dementia)
- Stepwise progression after strokes; or insidious with small vessel disease (subcortical)
- Executive dysfunction > memory loss; frontal-subcortical syndrome (psychomotor slowing, apathy, gait impairment, urinary incontinence)
- MRI: periventricular and subcortical white matter hyperintensities (leukoaraiosis), lacunar infarcts, cortical infarcts
- CADASIL: Notch3 mutation; early strokes, migraine with aura, psychiatric symptoms, progressive dementia; no AD amyloid
- Treatment: secondary stroke prevention (antiplatelet, statin, BP control, diabetes management); no specific FDA-approved cognition treatment; AChEI/memantine may modestly help mixed dementia

---

### Lewy Body Dementia (DLB)

**Core Clinical Features (≥2 = probable DLB; 1 = possible):**
1. Fluctuating cognition (attention/alertness variability — minutes to days)
2. Recurrent well-formed visual hallucinations (typically people or animals)
3. REM sleep behavior disorder
4. One or more spontaneous cardinal features of parkinsonism

**Supportive Features:** Severe neuroleptic sensitivity, postural instability, repeated falls, syncope, autonomic dysfunction, hypersomnia, hyposmia, delusions, apathy, depression

**Biomarkers (indicative):** Low dopamine transporter uptake on SPECT/PET (DaTscan); abnormal (low uptake) 123I-MIBG myocardial scintigraphy; polysomnographic confirmation of RBD; amyloid PET (often positive — overlap with AD)

**DLB vs PDD:** 1-year rule — dementia onset within 1 year of parkinsonism = DLB; dementia more than 1 year after parkinsonism = PDD (Parkinson's disease dementia). Same Lewy body pathology.

**Treatment:**
- Rivastigmine — FDA-approved for PDD; used off-label in DLB (largest clinical benefit vs other dementias)
- AVOID typical antipsychotics (haloperidol, chlorpromazine) — severe neuroleptic sensitivity (acute rigidity, drowsiness, NMS-like, accelerated cognitive decline, death)
- Neuroleptics if absolutely needed: quetiapine (lowest D2 blockade), clozapine, pimavanserin
- Parkinsonism: levodopa (modest response in DLB); start low dose; may worsen hallucinations
- RBD: clonazepam, melatonin
- Orthostatic hypotension: non-pharmacological first; midodrine, fludrocortisone

---

### Frontotemporal Dementia (FTD)

**Behavioral Variant FTD (bvFTD):**
- Frontotemporal atrophy (frontal > temporal); TDP-43 or tau pathology; genetic in ~40% (C9orf72, GRN, MAPT)
- Diagnostic criteria (≥3 of 6 features): disinhibition, apathy/inertia, loss of empathy, perseverative/compulsive behavior, hyperorality/dietary changes, executive deficits with relative memory sparing
- "Mirror sign" (does not recognize own reflection as self — severe variant)
- No approved pharmacotherapy; SSRIs (fluvoxamine, sertraline) for behavioral symptoms (modest); trazodone; atypical antipsychotics with caution

**Primary Progressive Aphasia (PPA):**
- Progressive nonfluent aphasia (PNFA): agrammatism, apraxia of speech, effortful halting speech; tau pathology (FTLD-tau), left frontal/perisylvian atrophy
- Semantic dementia (svPPA): fluent speech with severe anomia and loss of word meaning; bilateral anterior temporal atrophy (left > right); TDP-43
- Logopenic variant (lvPPA): word-finding pauses, phonological errors, impaired repetition; usually AD pathology; left posterior temporal/inferior parietal atrophy

---

### Normal Pressure Hydrocephalus (NPH)

**Classic Triad (Hakim's triad):**
- Gait disturbance: "magnetic gait" — wide-based, shuffling, short steps, feet appear glued to floor; difficulty initiating steps; prominent and early
- Urinary incontinence: urge incontinence; often less aware of it
- Cognitive impairment: subcortical pattern (slowing, attention, executive); relatively late and milder than other dementias

**Diagnosis:**
- CT/MRI: ventriculomegaly (Evans ratio > 0.3) out of proportion to sulcal atrophy; tight sulci at vertex; periventricular T2 signal; callosal angle (axial MRI) <90 degrees
- Large-volume LP (tap test): remove 30-50mL CSF; opening pressure normal or low-normal; assess gait before and after (10-min timed up-and-go, 10-meter walk); improvement = positive tap test
- External lumbar drainage (ELD): 3-5 days 150-200mL/day; higher predictive value than tap test

**Treatment:** Ventriculoperitoneal (VP) or lumbar-peritoneal (LP) shunt; programmable valve; improvement most reliable in gait (80%), then incontinence (50%), then cognition (25-30%); shunt complications: infection, subdural hematoma, shunt malfunction

---

## Guillain-Barre Syndrome (GBS)

### Pathophysiology and Subtypes

**Mechanism:** Molecular mimicry — antibodies to gangliosides shared between infectious pathogen lipopolysaccharides and peripheral nerve gangliosides

**Triggering Infections:**
- Campylobacter jejuni (most common — 30%; especially AMAN subtype)
- Cytomegalovirus (CMV)
- Epstein-Barr virus (EBV)
- Mycoplasma pneumoniae
- Influenza A
- COVID-19 (rare)
- Zika virus (association, especially Miller Fisher variant)
- Influenza vaccination (very rare — 1-2 per million; benefit > risk)

**GBS Subtypes:**

| Subtype | Pathology | Antibody | Region | Notes |
|---|---|---|---|---|
| AIDP (Acute inflammatory demyelinating polyradiculoneuropathy) | Demyelinating | Various (anti-GM1, anti-GD1b) | Western countries predominant | Most common overall; NCS shows demyelination |
| AMAN (Acute motor axonal neuropathy) | Pure motor axonal | Anti-GM1, anti-GD1a | Asia, C. jejuni-associated | NCS: axonal; can recover quickly (reversible conduction failure) |
| AMSAN (Acute motor and sensory axonal neuropathy) | Sensorimotor axonal | Anti-GD1a | Rare | Severe; slower recovery |
| MFS (Miller Fisher syndrome) | Cranial nerve/central | Anti-GQ1b (90%+) | All regions | Ophthalmoplegia + ataxia + areflexia; overlap with Bickerstaff brainstem encephalitis |
| Pharyngeal-cervical-brachial | Axonal | Anti-GT1a, anti-GQ1b | — | Throat/arm/neck weakness without legs |
| Bifacial weakness + paresthesias | — | — | — | Bilateral facial palsy + distal paresthesias |

---

### Clinical Features and Diagnosis

**Typical GBS Presentation:**
- Prodrome: infection 1-4 weeks prior
- Onset: bilateral ascending limb weakness (legs before arms), areflexia (hallmark), back and limb pain (often severe, early), sensory symptoms (paresthesias, glove-stocking pattern — less prominent than motor deficits)
- Progression: weakness peaks 2-4 weeks from onset (must reach nadir to diagnose — progressive phase only)
- Autonomic involvement (20-30%): labile blood pressure, sinus tachycardia, bradycardia, cardiac arrhythmias, ileus, urinary retention, anhidrosis — most dangerous complication
- Cranial nerve involvement: facial weakness (bilateral in 50%), dysphagia, ophthalmoparesis
- Respiratory failure: 25-30% require mechanical ventilation

**Respiratory Monitoring (20-30 rule):**
- FVC <20 mL/kg → intubate
- Maximum inspiratory force (MIF) worse than -30 cmH2O → intubate
- Oxygenation may be preserved until just before respiratory arrest — do NOT rely on SpO2 alone
- Monitor FVC, MIF, MEP q4-6h in deteriorating patients; intubate early if trend worsening

**Diagnostic Studies:**

| Test | Findings | Timing |
|---|---|---|
| CSF | Albuminocytologic dissociation — elevated protein (>0.45 g/L) with normal WBC (<10 cells/microL); "cytoalbuminous dissociation" | May be normal in first week; peaks at 4-6 weeks |
| NCS/EMG | Demyelination (prolonged distal latency, reduced conduction velocity, conduction block, prolonged F waves/absent H reflex) in AIDP; axonal (reduced CMAP/SNAP amplitudes) in AMAN/AMSAN | Key to confirm and classify |
| Anti-ganglioside antibodies | Anti-GQ1b (MFS/Bickerstaff), anti-GM1 (AMAN), anti-GD1a (AMAN/AMSAN) | Confirm subtype |
| MRI spine + brain | Rule out spinal cord compression, leptomeningeal enhancement (may see nerve root enhancement) | Early workup |

---

### GBS Treatment and Prognosis

**Immunotherapy:**
- IVIG: 0.4g/kg/day x5 days (total 2g/kg); OR 1g/kg x2 days — equivalent; preferred (ease of administration)
- Plasmapheresis (PLEX): 5 exchanges over 10-14 days (remove ~200-250mL plasma/kg total); equivalent to IVIG; preferred if IVIG contraindicated (IgA deficiency — anaphylaxis risk)
- Do NOT combine IVIG + PLEX (no added benefit; IVIG removes plasmapheresis substrate)
- Corticosteroids: NOT beneficial — multiple RCTs show no benefit and possibly worse outcomes
- Repeat course: if clinical deterioration after initial course (treatment-related fluctuation, TRF) — second course of same treatment

**Supportive Care:**
- DVT prophylaxis (LMWH + compression stockings)
- Pain management: gabapentin, carbamazepine, opioids if needed (pain often severe)
- Cardiac monitoring (telemetry for moderate-severe GBS)
- Autonomic management: treat labile BP conservatively (avoid aggressive antihypertensives); atropine for severe bradycardia; pacemaker rarely needed
- Bladder care: catheterization if retention
- Nutritional support: NG tube or PEG if prolonged intubation/dysphagia
- Aggressive PT/OT from early on; ankle splints to prevent foot-drop contractures
- Psychological support: ICU delirium, depression common in prolonged course

**Prognosis and Prognostic Scores:**
- 80-90% ambulatory by 6 months; 60% full recovery
- 5% mortality (autonomic instability, infection, PE)
- 10-15% significant long-term disability
- Poor prognostic factors: rapid onset-to-nadir <7 days, age >60, NCS axonal pattern, preceding C. jejuni, need for ventilation, very low CMAP amplitudes
- EGRIS (Erasmus GBS Respiratory Insufficiency Score) and IGOS score for ventilation prediction
- CIDP: consider if plateau/progression beyond 8 weeks (conversion rate ~5% of GBS presentations)

---

## Myasthenia Gravis (MG)

### Pathophysiology

**Autoimmune NMJ Failure:**
- Anti-AChR antibodies (85%): bind postsynaptic acetylcholine receptor → complement activation → complement-mediated destruction of postjunctional folds → endplate potential reduction → transmission failure
- Anti-MuSK antibodies (7-8%): muscle-specific kinase; clustering of AChR; predominantly bulbar and respiratory weakness; neck/facial/oropharyngeal weakness; less limb involvement; poor pyridostigmine response
- Anti-LRP4 antibodies (2-5%): low-density lipoprotein receptor-related protein 4; interacts with MuSK; double-seronegative MG subset
- Seronegative MG: antibodies to other NMJ proteins or below assay detection

**Thymus:**
- 65% have thymoma or thymic hyperplasia in AChR+ generalized MG
- Thymoma: associated with more severe MG; paraneoplastic (any antibody may be present); not necessarily malignant (WHO classification A, AB, B1, B2, B3)
- Thymic hyperplasia: germinal centers (ectopic lymphocyte sensitization against AChR)

---

### Clinical Features and Diagnosis

**Clinical Pattern:**
- Fatigable, fluctuating weakness — hallmark
- Worse with activity, heat, illness, stress, certain medications; better with rest and cold
- Ocular: ptosis (unilateral or bilateral), diplopia (extraocular muscle weakness, not pupil-sparing [unlike CN III palsy of pupil]) — first symptoms in 50%; 15% remain purely ocular (ocular MG); rest generalize within 2 years
- Bulbar: dysphagia (liquids worse than solids — contrast with ALS), dysarthria (nasal voice, dysphonia), jaw fatigues with chewing, facial weakness
- Limb: proximal > distal; deltoid, hip flexors, neck flexors (neck drop); hand/foot usually preserved
- Respiratory: diaphragm weakness (SOB supine); intercostal weakness (unable to count to 20 in single breath)
- No autonomic involvement (except MuSK — some autonomic symptoms); no cognitive changes; reflexes preserved

**Myasthenic Crisis:** Respiratory failure requiring intubation; usually precipitated by:
- Infections (respiratory infection most common)
- Surgery/anesthesia
- Medications (see below)
- Pregnancy (first trimester, peripartum)
- Rapid tapering of immunosuppression
- Aspiration

**Medications to Avoid in MG:**

| Class | Agents | Risk |
|---|---|---|
| Neuromuscular blocking agents | Succinylcholine (prolonged block), vecuronium (marked sensitivity) | Avoid if known MG — inform anesthesia |
| Aminoglycosides | Gentamicin, tobramycin, amikacin | Impair NMJ (presynaptic) |
| Fluoroquinolones | Ciprofloxacin, levofloxacin | Worsen MG |
| Beta-blockers | Propranolol, atenolol, eye drops (timolol) | Worsen |
| Calcium channel blockers | Verapamil, diltiazem | Worsen |
| Magnesium | IV magnesium sulfate | Blocks NMJ — avoid in crisis (except eclampsia with careful monitoring) |
| Lithium | — | Worsen |
| D-penicillamine | — | Can induce MG |
| Statins | — | Occasional case reports; may worsen |
| Procainamide, quinidine | — | Worsen |

**Diagnostic Testing:**

| Test | Sensitivity | Notes |
|---|---|---|
| Anti-AChR antibody | 85% generalized; 50% ocular | Highly specific (>99%); binding, modulating, blocking subtypes |
| Anti-MuSK antibody | 40% of AChR-seronegative | IgG4 subclass; different mechanism |
| Repetitive nerve stimulation (RNS) | 60-80% generalized | Decremental response ≥10% at 3Hz (most sensitive at proximal muscles: trapezius, nasalis, orbicularis oculi) |
| Single-fiber EMG (SFEMG) | 92-99% | Most sensitive; increased jitter; blocking; useful in ocular MG and seronegative |
| CT chest | — | Mandatory to exclude thymoma |
| Ice pack test | 80% for ptosis | Apply ice pack to closed eyelid x2 min — ptosis improves in MG (cold improves transmission) |
| Edrophonium (Tensilon) test | 80-90% ocular | Rarely used (cardiac risk, need atropine available); acetylcholinesterase inhibitor — brief improvement; positive if ptosis or diplopia improves within 1 min |

---

### MG Treatment

**Symptomatic:**
- Pyridostigmine (Mestinon): acetylcholinesterase inhibitor; standard dose 60mg q4-6h while awake (max 600mg/day); extended-release 180mg QHS if nocturnal symptoms; titrate to effect; cholinergic excess/crisis: SLUDGE (Salivation, Lacrimation, Urination, Defecation, GI cramping, Emesis) + bradycardia, bronchospasm, miosis — treat with atropine; HOLD during crisis (excess secretions impair ventilator management)
- 3,4-Diaminopyridine (DAP/amifampridine): primarily for Lambert-Eaton MG (voltage-gated calcium channel antibodies) — enhances presynaptic ACh release; some use in MG

**Immunosuppression:**

| Agent | Dose | Onset | Key Points |
|---|---|---|---|
| Prednisone | Initiate 10-20mg/day, increase by 5-10mg every 1-2 weeks to 60-80mg/day | Weeks | NEVER start high dose acutely (causes transient worsening in 50% due to acute effect on NMJ); taper slowly (years); osteoporosis prophylaxis; monitor glucose, BP, eyes, bone density |
| Azathioprine | 2-3mg/kg/day | 6-18 months | Check TPMT genotype before (homozygous deficient = toxic doses); CBC monitoring (leukopenia); hepatotoxicity; interactions with allopurinol (reduce dose 75%); steroid-sparing |
| Mycophenolate mofetil (MMF) | 1-1.5g BID | 6-12 months | Better tolerated than azathioprine; GI SE; teratogen; CBC monitoring |
| Cyclosporine | 3-5mg/kg/day | 3-6 months | Nephrotoxic, hypertensive; monitor levels; many drug interactions |
| Tacrolimus | 3mg/day | 3-6 months | Nephrotoxic; less evidence than cyclosporine but used in MuSK-MG |
| Rituximab | 375mg/m² weekly x4 or 1g x2 (2 weeks apart) | 3-6 months | Anti-CD20 B cell depletion; most evidence for MuSK-MG; refractory AChR+ MG; PML risk |

**Biologic/Novel Therapies:**

| Agent | Target | Indication | Notes |
|---|---|---|---|
| Eculizumab (Soliris) | C5 complement | Generalized refractory AChR+ MG | IV q2 weeks then q3 weeks; meningococcal vaccine required ≥2 weeks before AND prophylactic antibiotics; rare but fatal meningococcemia risk |
| Ravulizumab (Ultomiris) | C5 complement | Generalized refractory AChR+ MG | Long-acting eculizumab; q8 weeks after loading |
| Efgartigimod alfa (Vyvgart) | FcRn receptor blocker | Generalized AChR+ MG | Reduces IgG (including AChR Ab); IV 10mg/kg weekly x4 cycles; cycles PRN; rapid onset |
| Rozanolixizumab (Rystiggo) | FcRn receptor blocker | Generalized AChR+ and MuSK+ MG | SQ weekly; similar mechanism to efgartigimod |
| Nipocalimab | FcRn blocker | Generalized MG | IV; longer dosing interval |
| Zilucoplan | C5 complement inhibitor | Generalized AChR+ MG | SQ daily self-injection; convenience advantage |

**Thymectomy:**
- Indication: all non-thymoma generalized AChR+ MG patients age 18-60 (MGTX trial — significantly improved clinical outcomes at 3 years regardless of thymoma; reduced medication requirements)
- Thymoma: surgical regardless of MG control (oncologic necessity)
- Route: extended transsternal thymectomy (complete thymus removal) preferred over VATS/robotic (less complete — debated)
- MuSK-MG: thymectomy not routinely recommended (no thymic involvement)
- >60 years: may benefit but evidence less clear

---

## Stroke

### Ischemic Stroke — Acute Management

**Time-Critical Interventions:**

| Intervention | Window | Criteria | Key Points |
|---|---|---|---|
| IV alteplase (tPA) | 0-4.5 hours from last known well (LKW) | NIHSS, BP <185/110, blood glucose 50-400, CT no bleed | Extended to 4.5h (ECASS III); 0.9mg/kg (max 90mg), 10% bolus then 60-min infusion; door-to-needle <60 min target; hemorrhagic transformation risk ~6% symptomatic |
| IV tenecteplase | 0-4.5 hours | Same as tPA | 0.25mg/kg (max 25mg) single bolus — AHA 2024 guidelines: may be preferred over alteplase (easier administration, similar efficacy, emerging evidence of superiority) |
| Mechanical thrombectomy (MT) | 0-24 hours | Large vessel occlusion (ICA, M1, M2, basilar), CT perfusion mismatch | DAWN/DEFUSE-3: extended window (6-24h) with perfusion mismatch; modified Rankin scale improvement; access to stroke center with neurointerventionalist |

**Contraindications to IV tPA:**
- Active internal bleeding; recent (3 months) severe head trauma, intracranial surgery, stroke
- Intracranial neoplasm, AVM, aneurysm
- Uncontrolled hypertension >185/110 at time of treatment
- Platelet count <100,000; INR >1.7; heparin within 48h with elevated aPTT
- Blood glucose <50 or >400
- Relative: minor/rapidly improving symptoms, seizure at onset, prior stroke within 3 months (absolute)

**Blood Pressure Management in Stroke:**
- Ischemic, not treated with tPA: allow permissive hypertension up to 220/120; only treat if >220/120 or end-organ damage
- Before and during tPA: maintain <185/110 before infusion; <180/105 during and 24h after
- Hemorrhagic stroke: target SBP 130-140mmHg within 1 hour (INTERACT2, ATACH-2 — aggressive lowering to <140 now standard)
- After thrombectomy: avoid hypotension; SBP goal varies by reperfusion status

**TOAST Classification — Ischemic Stroke Subtypes:**

| Subtype | Prevalence | Features | Secondary Prevention |
|---|---|---|---|
| Large artery atherosclerosis | 25% | Stenosis ≥50% ICA/MCA/vertebrobasilar; crescendo TIAs, hemodynamic pattern | Antiplatelet + statin (high-intensity) + risk factor control; carotid endarterectomy (CEA) if ≥70% symptomatic stenosis |
| Cardioembolic | 25% | AF, valvular, LV thrombus, cardiomyopathy; sudden onset, maximal at onset, multiple territory | Anticoagulation (AF: DOAC preferred over warfarin); cardioversion |
| Small vessel (lacunar) | 20% | Hypertension + diabetes; pure motor, pure sensory, ataxic hemiparesis, dysarthria-clumsy hand syndromes; basal ganglia/pons/thalamus/internal capsule | Antiplatelet; aggressive BP, glucose, lipid control |
| Other determined | 5% | Arterial dissection, hypercoagulable, vasculitis, migrainous, drugs | Anticoagulation for dissection (3-6 months); treat underlying |
| Cryptogenic (undetermined) | 25% | No clear mechanism; ≥2 potential causes; or inadequate workup | Antiplatelet; long-term cardiac monitoring (implantable loop recorder) for paroxysmal AF; PFO closure if cryptogenic + PFO + high-risk features (RoPE score >6) |

**TIA (Transient Ischemic Attack):**
- Duration typically <1 hour (tissue-based definition: no infarct on DWI)
- ABCD2 score (Age ≥60 = 1, BP ≥140/90 = 1, Clinical features [unilateral weakness=2, speech without weakness=1], Duration [≥60min=2, 10-59min=1], Diabetes = 1) — max 7; >4 = high risk
- POINT trial / CHANCE trial: dual antiplatelet (aspirin + clopidogrel) for 21 days after minor stroke/high-risk TIA, then single antiplatelet — reduces 90-day stroke risk from ~13% to ~9%
- Admit TIA with ABCD2 >3, DWI lesion, AF, symptomatic carotid stenosis; complete workup within 24h

**Secondary Prevention:**

| Indication | Agent | Evidence |
|---|---|---|
| Non-cardioembolic stroke/TIA | Aspirin 81-325mg/day, OR clopidogrel 75mg/day, OR aspirin + dipyridamole (Aggrenox) | Aspirin vs clopidogrel equivalent; dual therapy for 21 days post minor stroke then single |
| AF | Apixaban (ARISTOTLE), rivaroxaban, dabigatran, edoxaban — all DOACs preferred over warfarin (AVERROES, ARISTOTLE, ROCKET-AF) | Start within 4-14 days of ischemic stroke (timing depends on size/hemorrhagic risk) |
| PFO with cryptogenic stroke | PFO closure device (CLOSE, REDUCE, GORE REDUCE trials) if age <60-65, no other etiology, high-risk PFO features (large shunt, ASA) | Post-closure aspirin; short-term antiplatelet |
| Carotid stenosis (symptomatic 70-99%) | CEA within 2 weeks of stroke/TIA; CAS alternative if high surgical risk | 5-year NNT ~6; benefit decreases with time since event |
| Statin | High-intensity (atorvastatin 40-80mg, rosuvastatin 20-40mg) | All ischemic stroke/TIA regardless of LDL at presentation |

---

### Hemorrhagic Stroke

**Intracerebral Hemorrhage (ICH):**
- Most common locations by etiology: hypertensive (putamen > thalamus > pons > cerebellum > subcortical WM); cerebral amyloid angiopathy (lobar — posterior > frontal; multiple microbleeds on GRE/SWI; recurrence risk high)
- ICH Score (mortality predictor): GCS, volume (>30mL), intraventricular extension, infratentorial location, age >80
- Management: SBP target 130-140mmHg; correct coagulopathy emergently (INR reversal: 4F-PCC + Vitamin K; dabigatran: idarucizumab; Xa inhibitors: andexanet alfa); ICP management; surgical hematoma evacuation controversial (STICH trial negative except superficial lobar and cerebellar >3cm)
- Avoid anticoagulation/antiplatelet for 4-8 weeks minimum; restart if cardioembolic risk high (AF)

**Subarachnoid Hemorrhage (SAH):**
- Most common cause: ruptured saccular aneurysm (75%); also AVM, trauma, perimesencephalic SAH (benign variant)
- "Worst headache of life" (thunderclap headache — maximal at onset within 1 second to 1 minute); can have sentinel headache weeks prior
- CT non-contrast: hyperintense blood in basal cisterns; sensitivity >98% within 6h; if negative, LP for xanthochromia (bilirubin) after 12h (spectrophotometry preferred) or blood > tube 4 (traumatic tap vs SAH)
- Complications: rebleeding (10-20% in first 24h without treatment — highest risk; nimodipine does not prevent rebleeding), vasospasm/delayed cerebral ischemia (DCI — peaks days 4-14; transcranial Doppler monitoring), hydrocephalus (communicating — 25%), hyponatremia (SIADH or cerebral salt wasting)
- Aneurysm treatment: surgical clipping or endovascular coiling (ISAT trial — coiling superior in suitable anatomy; clipping better for MCA aneurysms, young patients)
- Nimodipine 60mg q4h x21 days: reduces DCI (does NOT reduce vasospasm radiographically — clinical benefit only); IV nimodipine if oral not tolerated
- Vasospasm management: euvolemia (do NOT triple-H therapy HHH — hypervolemia/hemodilution fallen out of favor); normovolemia; induced hypertension if DCI; intra-arterial vasodilators (verapamil, nicardipine) or balloon angioplasty for refractory vasospasm

---

## Coma and Disorders of Consciousness

### Approach to Coma

**Definition:** Eyes closed, no arousal to stimulation, no purposeful movement.

**ARAS (Ascending Reticular Activating System):** Arousal maintained by ARAS projecting from upper pons/midbrain through thalamus to cortex bilaterally; impaired by lesions of: (1) both cerebral hemispheres (diffuse), (2) upper brainstem (ARAS), (3) thalamus bilaterally.

**Emergency Assessment (DONT mnemonic):**
- D — Dextrose (glucose <70 → give 50% dextrose)
- O — Oxygen (hypoxia → oxygen)
- N — Naloxone (opioids — 0.4-2mg IV; titrate to avoid withdrawal)
- T — Thiamine (100mg IV before glucose in alcoholism)
- +Flumazenil: benzodiazepine reversal (0.2mg IV, repeat q1min max 1mg; caution — may precipitate seizures in benzodiazepine-dependent)

**Glasgow Coma Scale (GCS):**

| Component | Score | Response |
|---|---|---|
| Eye opening (E) | 4 | Spontaneous |
| | 3 | To voice |
| | 2 | To pain |
| | 1 | None |
| Verbal (V) | 5 | Oriented |
| | 4 | Confused |
| | 3 | Words only |
| | 2 | Sounds only |
| | 1 | None |
| Motor (M) | 6 | Follows commands |
| | 5 | Localizes pain |
| | 4 | Withdraws |
| | 3 | Flexion (decorticate) |
| | 2 | Extension (decerebrate) |
| | 1 | None |

GCS ≤8 = coma (or intubation needed); GCS 9-12 = moderate; ≥13 = mild

**Structural vs Metabolic Coma:**

| Feature | Structural | Metabolic / Toxic |
|---|---|---|
| Onset | Sudden (vascular) or progressive | Variable |
| Pupil response | Asymmetric, fixed (herniation), pinpoint (pontine) | Symmetric, reactive (preserved until late); exception: opioids (pinpoint) |
| Eye movements | Asymmetric, deviated, INO | Symmetric, conjugate deviation absent; roving if intact brainstem |
| Motor | Asymmetric, lateralizing, posturing | Symmetric, multifocal myoclonus, tremor, asterixis |
| Reflexes | Asymmetric, Babinski | Symmetric; hyporeflexia |
| CT head | Lesion | Usually normal |

**Herniation Syndromes:**

| Syndrome | Mechanism | Features |
|---|---|---|
| Central transtentorial | Bilateral hemisphere or central mass pushing brainstem down | Diencephalic (small pupils, Cheyne-Stokes breathing) → midbrain (midsize pupils, central hyperventilation) → pontine (pinpoint pupils, apneustic breathing) |
| Uncal (lateral) | Temporal lobe mass → uncus compresses CN III then PCA then midbrain | Ipsilateral CN III palsy (fixed dilated pupil) FIRST; then contralateral hemiplegia; Kernohan's notch — ipsilateral hemiplegia (false localizing sign) |
| Tonsillar | Cerebellar mass → tonsils through foramen magnum | Neck pain, stiff neck, apnea, cardiovascular collapse |
| Subfalcine | Frontal mass → cingulate under falx | Contralateral leg weakness (ACA territory); may be asymptomatic |

**Locked-In Syndrome:** Bilateral pontine infarction (basilar artery); preserved consciousness; vertical eye movements and blinking only motor function; EEG normal (awake); distinguish from coma

**Vegetative State (VS) / Unresponsive Wakefulness Syndrome (UWS):** Eyes open (sleep-wake cycles); no purposeful behavior; no reproducible voluntary responses; brainstem reflexes intact

**Minimally Conscious State (MCS):** Inconsistent but reproducible minimal signs of awareness (follows simple commands, visual pursuit, yes/no responses); better prognosis than VS; fMRI/EEG may detect covert consciousness

---

## CNS Infections

### Bacterial Meningitis

**Epidemiology and Common Pathogens:**

| Age Group | Most Common Organisms |
|---|---|
| Neonates (<1 month) | Group B Streptococcus, E. coli, Listeria monocytogenes |
| Infants 1-3 months | GBS, E. coli, Listeria, H. influenzae, S. pneumoniae, N. meningitidis |
| Children/Young adults | N. meningitidis, S. pneumoniae |
| Adults | S. pneumoniae (most common overall in adults), N. meningitidis |
| Elderly/Immunocompromised | S. pneumoniae, Listeria monocytogenes (ampicillin coverage needed), gram-negatives |

**Empiric Antibiotic Regimens:**

| Situation | Antibiotics |
|---|---|
| Adults 18-50 years | Vancomycin + ceftriaxone 2g IV q12h |
| Adults >50, immunocompromised, alcoholism | Vancomycin + ceftriaxone + ampicillin 2g IV q4h (Listeria coverage) |
| Penicillin allergy | Vancomycin + chloramphenicol OR meropenem (for most organisms); aztreonam for gram-negatives |
| Suspected HSV encephalitis (altered mental status, temporal involvement) | Add acyclovir 10mg/kg IV q8h |

**Dexamethasone:** 0.15mg/kg IV q6h x4 days — give BEFORE or WITH first dose of antibiotics; reduces mortality and neurological sequelae especially for S. pneumoniae (NNT ~8 for death); benefit less clear for other organisms; do NOT delay antibiotics for LP or CT if contraindicated

**LP CSF Interpretation in Meningitis:**

| Parameter | Bacterial | Viral (Aseptic) | TB/Fungal | Normal |
|---|---|---|---|---|
| Opening pressure | Elevated (>25 cmH2O) | Normal-mildly elevated | Elevated | 6-18 cmH2O |
| WBC | >1000 (PMN predominant) | 10-1000 (lymphocyte) | 100-500 (lymphocyte) | <5 |
| Protein | >100 mg/dL (often 200-500) | 50-100 | 100-500 | 15-45 mg/dL |
| Glucose | <40 mg/dL; CSF:serum ratio <0.4 | Normal | <45; ratio <0.5 | 60-70% serum glucose |
| Other | Positive culture, gram stain | PCR for virus | AFB smear/culture, cryptococcal Ag, India ink |  |

**When to CT Before LP:**
- Immunocompromised (HIV/AIDS, transplant, steroids)
- New-onset seizures
- Papilledema
- Focal neurological deficits
- Altered mental status (GCS <15)
- Do NOT delay empiric antibiotics + dexamethasone while awaiting CT or LP

**Complications of Bacterial Meningitis:**
- SIADH (hyponatremia)
- Subdural effusion/empyema
- Cerebral venous sinus thrombosis
- Hydrocephalus
- Seizures (30%)
- Waterhouse-Friderichsen syndrome (N. meningitidis septicemia → bilateral adrenal hemorrhage → adrenal crisis)
- Hearing loss (most common long-term sequel — audiogram post-recovery)

---

### Herpes Simplex Encephalitis (HSE)

- Most common cause of fatal sporadic encephalitis in US; HSV-1 (adults, reactivation); HSV-2 (neonates, primary)
- Predilection for temporal lobes and orbitofrontal cortex (limbic encephalitis pattern); fever + headache + altered mental status + personality change + seizures; olfactory hallucinations
- MRI: T2/FLAIR hyperintensity in medial temporal lobes, insular cortex; DWI restriction; hemorrhagic changes (late)
- EEG: temporal periodic lateralized epileptiform discharges (PLEDs / LPDs)
- CSF: lymphocytic pleocytosis, elevated protein, normal glucose; HSV-1 PCR (sensitivity 98%, specificity 94%)
- Treatment: acyclovir 10mg/kg IV q8h x14-21 days (minimum 21 days if severe); dose adjustment for renal impairment; do not wait for PCR result — treat empirically
- Outcomes: 70% mortality untreated; with acyclovir ~20-30% mortality; neuropsychiatric sequelae common (memory impairment, seizures)
- Anti-NMDAR autoimmune encephalitis can follow HSE by 4-6 weeks (HSV triggers immune response against NR1) — second deterioration after initial improvement

---

### Cryptococcal Meningitis

- Cryptococcus neoformans (immunocompromised, especially AIDS); Cryptococcus gattii (immunocompetent, Pacific Northwest)
- Subacute onset, headache, meningismus (may be absent), elevated ICP (50% ICP >20 cmH2O)
- Diagnosis: serum and CSF cryptococcal antigen (sensitivity >95%); India ink (50-75%); CSF culture
- Treatment (AIDS):
  - Induction (2 weeks): liposomal amphotericin B 3-4mg/kg/day IV + flucytosine 25mg/kg q6h (COAT trial — superior to amphotericin B alone)
  - Consolidation (8 weeks): fluconazole 400mg/day PO
  - Maintenance: fluconazole 200mg/day PO lifelong (until CD4 >200 x6 months on ART)
- ICP management: serial therapeutic LPs (target opening pressure <20 cmH2O); VP shunt for refractory elevated ICP; acetazolamide ineffective; steroids NOT routinely recommended (may worsen in HIV)

---

## Neuromuscular Diseases

### ALS (Amyotrophic Lateral Sclerosis)

**Pathophysiology:**
- Combined upper (UMN) and lower (LMN) motor neuron degeneration
- TDP-43 proteinopathy in 97% (sporadic and most familial); SOD1 (20% familial), C9orf72 (most common familial and some sporadic ALS/FTD overlap)
- El Escorial criteria: UMN signs (spasticity, hyperreflexia, Babinski), LMN signs (weakness, wasting, fasciculations, EMG evidence of active/chronic denervation) in ≥2 of 4 regions (bulbar, cervical, thoracic, lumbar)

**Clinical:**
- Limb onset (70%): asymmetric distal weakness with fasciculations, wasting; both UMN + LMN in same regions
- Bulbar onset (25%): dysarthria, dysphagia, tongue fasciculations + emotional lability (UMN)
- Respiratory onset (5%): orthopnea, respiratory failure
- Purely UMN = primary lateral sclerosis (PLS — better prognosis, may convert to ALS)
- Purely LMN = progressive muscular atrophy (PMA)
- Cognition: ~50% have some executive dysfunction; 5-15% develop ALS-FTD

**Management:**

| Intervention | Details |
|---|---|
| Riluzole | 50mg BID; modestly prolongs survival ~3 months (glutamate antagonism); monitor LFTs; fatigue, nausea |
| Edaravone (Radicava) | IV 60mg daily x14d, then 14d off, then 10 days on x30d cycles; modestly slows functional decline; IV or oral suspension; oxidative stress mechanism |
| Tofersen (Qalsody) | Anti-SOD1 ASO (antisense oligonucleotide); intrathecal monthly; SOD1-ALS; reduces neurofilament light chain and SOD1 protein |
| Noninvasive ventilation (NIV) | BiPAP when FVC <50% or symptomatic; prolongs survival and quality of life |
| PEG/RIG feeding tube | Place when FVC >50% (safer procedure) but swallowing impaired; nutritional support extends survival |
| Spasticity | Baclofen, tizanidine |
| Sialorrhea | Glycopyrrolate, amitriptyline, Botox to salivary glands |
| Pseudobulbar affect | Dextromethorphan/quinidine (Nuedexta) 20/10mg BID |
| Cramps | Mexiletine, quinine (limited evidence) |
| Multidisciplinary clinic | Respiratory, nutrition, physical/occupational/speech therapy, palliative care — monthly follow-up |

---

### Peripheral Neuropathy — Approach

**Classification by Fiber Type Affected:**

| Neuropathy Type | Features | Causes |
|---|---|---|
| Large fiber motor | Weakness, wasting, absent reflexes, footdrop | GBS, CIDP, vasculitis, hereditary (CMT) |
| Large fiber sensory | Vibration/proprioception loss, sensory ataxia, pseudoathetosis, Romberg + | B12 deficiency, paraneoplastic (anti-Hu, anti-CV2), Sjogren's, CIDP |
| Small fiber | Burning pain, allodynia, normal NCS, skin biopsy (reduced intraepidermal nerve fiber density) | Diabetes (most common), amyloid, Fabry's, HIV, idiopathic |
| Autonomic | Orthostasis, gastroparesis, ED, anhidrosis | Diabetes, amyloid, autoimmune autonomic ganglionopathy (anti-ganglionic AChR Ab) |

**Electrodiagnostic Pattern:**

| Pattern | Interpretation |
|---|---|
| Axonal (reduced amplitude, normal velocity) | Metabolic, toxic, genetic; more common in distal symmetrical polyneuropathies |
| Demyelinating (prolonged latency, slow velocity, conduction block) | GBS, CIDP, CMT (hereditary), anti-MAG, paraprotein neuropathy |
| Mixed axonal + demyelinating | Diabetes, uremia |
| Mononeuropathy multiplex | Vasculitis, leprosy, sarcoid, HNPP |

**CIDP (Chronic Inflammatory Demyelinating Polyradiculoneuropathy):**
- Symmetric proximal + distal weakness, sensory loss, areflexia; progression >8 weeks (distinguishes from GBS)
- CSF elevated protein; NCS: demyelinating multifocal
- Treatment: IVIG 2g/kg over 2-5 days then 1g/kg q3-4 weeks maintenance; plasmapheresis q2 weeks; prednisone; azathioprine/MMF steroid-sparing; efgartigimod recently studied
- Anti-CNTN1 and anti-NF155 subtypes: IgG4 mediated; IVIG less effective; rituximab effective

**Common Mononeuropathies:**

| Nerve | Site | Etiology | Clinical | Treatment |
|---|---|---|---|---|
| Median (CTS) | Carpal tunnel | Repetitive strain, pregnancy, hypothyroid, rheumatoid | Hand numbness (lateral 3.5 fingers), thenar atrophy, Tinel's + Phalen's sign | Wrist splint, steroid injection, surgical release |
| Ulnar | Cubital tunnel (elbow) | Prolonged elbow flexion, trauma | Ring/little finger numbness, intrinsic hand wasting, Froment's sign (thumb flexion with paper grip) | Elbow padding, avoid prolonged flexion; transposition surgery |
| Radial | Spiral groove (humerus) | Saturday night palsy, fracture | Wrist drop (extensor weakness), spared triceps usually, preserved thumb sensation (superficial radial) | Splinting; recovery usually 3-6 months |
| Peroneal (fibular) | Fibular head | Leg crossing, prolonged squatting, casts, weight loss | Foot drop (dorsiflexion weakness), toe extension weakness; sensory loss dorsum of foot | Remove compressive cause; AFO; 80% recovery; surgery if traumatic |
| Femoral | Inguinal ligament | Diabetes (diabetic amyotrophy), lithotomy position, hematoma | Quadriceps weakness, knee buckles, absent knee jerk, anterior thigh sensory loss | Address cause; PT |

---

## Sleep Disorders

### Obstructive Sleep Apnea (OSA)

- Definition: ≥5 apneas/hypopneas per hour of sleep (AHI ≥5 with symptoms; ≥15 without); apnea = cessation of airflow ≥10 seconds
- Risk factors: obesity (most important), male sex, age, retrognathia, large neck circumference (>40cm women, >43cm men), alcohol/sedatives, hypothyroidism, acromegaly
- Symptoms: snoring, witnessed apneas, non-restorative sleep, excessive daytime sleepiness (Epworth scale), morning headaches, nocturia, cognitive impairment
- Diagnosis: polysomnography (PSG — gold standard) or home sleep apnea testing (HSAT — adequate for moderate-high pretest probability uncomplicated OSA)
- Severity: mild AHI 5-14, moderate 15-30, severe >30
- Complications: hypertension (most common comorbidity — 50%), atrial fibrillation, stroke, coronary artery disease, type 2 diabetes, pulmonary hypertension, depression
- Treatment:
  - CPAP (continuous positive airway pressure): first-line for all severity; eliminates apneas, reduces cardiovascular risk; adherence challenge; mask interface selection critical
  - APAP (auto-adjusting): equivalent to CPAP, adjusts dynamically; preferred by some for comfort
  - Oral appliance (mandibular advancement device): mild-moderate OSA or CPAP intolerant; less effective than CPAP
  - Positional therapy: if predominantly supine OSA (AHI in supine >2x non-supine)
  - Weight loss: definitive if OSA related to obesity; bariatric surgery for severe
  - Hypoglossal nerve stimulation (Inspire): FDA-approved for moderate-severe OSA with CPAP intolerance, no concentric palate collapse on DISE (drug-induced sleep endoscopy); implanted device
  - Surgery: uvulopalatopharyngoplasty (UPPP) — modest long-term efficacy; maxillomandibular advancement (MMA) — most effective surgical option; tonsillectomy in children

---

### REM Sleep Behavior Disorder (RBD)

- Dream enactment: vocalizations, limb movements, walking during REM sleep; injury to self or bed partner
- Diagnosis: PSG with REM without atonia (RWOA); muscle activity during REM sleep
- Isolated RBD: 80-90% develop alpha-synucleinopathy (PD, MSA, DLB) within 10-15 years — strongest prodromal marker
- Treatment: clonazepam 0.5-1mg QHS (most effective); melatonin 3-12mg QHS (safer, preferred in elderly or cognitive impairment)
- Safety environment: remove sharp objects, pad floor, consider bed rails

---

### Narcolepsy

**Type 1 (with cataplexy):**
- Orexin (hypocretin) deficiency — autoimmune destruction of hypothalamic orexin neurons
- CSF orexin <110 pg/mL (diagnostic)
- Pentad: Excessive daytime sleepiness (EDS), Cataplexy, Sleep paralysis, Hypnagogic/hypnopompic hallucinations, Fragmented nocturnal sleep

**Type 2 (without cataplexy):**
- No cataplexy; normal or intermediate orexin levels; less severe; may convert to type 1

**Cataplexy:** Sudden loss of muscle tone triggered by strong emotion (laughter most specific, anger, surprise); brief (seconds to minutes); consciousness preserved; bilateral, may be partial (facial, neck, knees); can be subtle in children (facial drooping with laughter)

**Diagnosis:** MSLT (Multiple Sleep Latency Test): mean sleep latency ≤8 min + ≥2 sleep-onset REM periods (SOREMPs); preceded by overnight PSG

**Treatment:**

| Symptom | Drug | Dose |
|---|---|---|
| EDS | Modafinil | 100-400mg AM (or split AM and noon) |
| EDS | Armodafinil | 75-250mg AM |
| EDS | Solriamfetol | 75-150mg AM |
| EDS | Pitolisant | 8.9-35.6mg AM (H3 antagonist) |
| EDS | Sodium oxybate (GHB) | Taken at bedtime and 2.5-4h later — also treats cataplexy and consolidates nocturnal sleep |
| Cataplexy | Sodium oxybate | 6-9g/night divided |
| Cataplexy | Venlafaxine/fluoxetine | Off-label; REM-suppressant effect; second-line |
| Cataplexy | Pitolisant | FDA-approved for cataplexy |
| All symptoms | Sodium oxybate | Most comprehensive; Schedule III/IV REMS program; avoid with alcohol/sedatives |

---

## Neuro-Oncology

### Primary Brain Tumors

**WHO 2021 Classification — Key Gliomas:**

| Tumor | WHO Grade | Key Molecular Features | Prognosis |
|---|---|---|---|
| Astrocytoma, IDH-mutant | 2, 3, 4 | IDH1/2 mutation; ATRX loss; no 1p/19q codeletion | Grade 2: median survival 10-15 yr; Grade 4: ~2 yr |
| Oligodendroglioma, IDH-mutant, 1p/19q codeleted | 2, 3 | IDH mutation + 1p/19q codeletion (defining); TERT mutation | Better prognosis; radiation + PCV chemotherapy; Grade 2: 15+ yr |
| Glioblastoma (GBM), IDH-wildtype | 4 | IDH wildtype + EGFR amplification/TERT/+7/-10 | 14-16 months with treatment |
| Diffuse midline glioma, H3 K27M-mutant | 4 | H3 K27M mutation; thalamus, brainstem, spinal cord | <1 year; pediatric predominantly; ONC201 for H3K27M+ diffuse intrinsic pontine glioma |
| Ependymoma | 2, 3 | RELA fusion (supratentorial); YAP1; C11orf95 | Variable by grade and location |

**GBM Standard Treatment (Stupp Protocol):**
- Surgery: maximal safe resection (extent of resection correlates with survival)
- Concurrent RT + temozolomide: 60Gy/30 fractions + temozolomide 75mg/m² daily
- Adjuvant temozolomide: 150-200mg/m² days 1-5 of 28-day cycles x6 cycles
- Tumor treating fields (Optune): alternating electric fields via scalp electrodes; improved OS in MGMT-unmethylated; FDA-approved
- MGMT promoter methylation: predicts TMZ response; methylated = better prognosis/response (~50%)
- Bevacizumab: FDA-approved 2nd line GBM; improves PFS but not OS; reduces peritumoral edema (steroid-sparing)
- IDH inhibitor: vorasidenib (IDH1/2 inhibitor) for grade 2 IDH-mutant glioma (INDIGO trial — improved PFS, delays need for radiation/chemo)

**Meningioma:**
- Most common primary brain tumor (benign in 90%); WHO grade 1 (typical), 2 (atypical — higher recurrence), 3 (anaplastic — rare)
- Gross total resection curative in grade 1; grade 2-3: adjuvant radiation
- NF2 gene mutations most common; radiation-induced meningiomas (latency 20-25 years)

**Metastatic Brain Tumors:**
- Most common brain tumors overall; lung > breast > melanoma > colon > renal cell carcinoma
- Treatment: resection (single large accessible lesion), stereotactic radiosurgery (SRS — multiple small metastases ≤4 lesions or selected ≤10), whole brain radiation therapy (WBRT — multiple metastases, leptomeningeal disease — cognitive toxicity concern — memantine + hippocampal avoidance WBRT reduces neurocognitive effects)
- Systemic targeted therapy: EGFR+ NSCLC (osimertinib, erlotinib — cross BBB), BRAF V600E melanoma (dabrafenib + trametinib)
- Dexamethasone: reduces peritumoral edema; use minimum effective dose; taper as able
- Leptomeningeal metastases: IT methotrexate or cytarabine; intrathecal targeted therapy emerging; median survival 2-4 months

---

## Autonomic Nervous System

### Orthostatic Hypotension (OH)

- Definition: drop in SBP ≥20mmHg or DBP ≥10mmHg within 3 minutes of standing (or 60-degree head-up tilt)
- Neurogenic OH: sympathetic failure — diabetes, PD, MSA, pure autonomic failure, amyloid neuropathy; inadequate norepinephrine release; heart rate does NOT increase appropriately (distinguishes from hypovolemic OH where HR increases >15 bpm)
- POTS (Postural Orthostatic Tachycardia Syndrome): HR increase ≥30 bpm (≥40 in adolescents) on standing without significant BP drop; predominantly young women; symptoms: lightheadedness, palpitations, fatigue, brain fog; treatment: volume expansion (salt loading 2-3g/day, 2-3L fluids), compression stockings, exercise reconditioning, fludrocortisone, beta-blockers (propranolol low dose), ivabradine, midodrine

**Neurogenic OH Management:**

| Intervention | Details |
|---|---|
| Non-pharmacological | Compression stockings (waist-high preferred), abdominal binder, elevated head of bed 30 degrees (reduces nocturnal supine hypertension and renal sodium loss), bolus cold water 500mL before activity, avoid triggers (large meals, heat, straining) |
| Fludrocortisone | 0.1-0.2mg/day — mineralocorticoid; increases plasma volume; supine hypertension risk; hypokalemia; weight gain |
| Midodrine | 2.5-10mg TID (alpha-1 agonist; avoid within 4h of bedtime — supine hypertension) |
| Droxidopa (Northera) | 100-600mg TID (norepinephrine prodrug); approved for neurogenic OH in MSA, PD, diabetic neuropathy, non-diabetic autonomic neuropathy |
| Pyridostigmine | 30-60mg TID (modest effect; particularly for standing BP; less supine hypertension risk) |
| Atomoxetine | 18mg daily (norepinephrine reuptake inhibitor; useful in autonomic ganglia failure where pyridostigmine less effective) |

---

## Neuroimmunology

### Autoimmune Encephalitis

**Anti-NMDAR Encephalitis (Most Common Autoimmune Encephalitis):**
- Anti-NR1 (GluN1) IgG antibodies against NMDA receptor
- Demographics: young women predominate; 50% associated with ovarian teratoma (young women); also post-HSE
- Clinical stages: prodrome (flu-like) → psychiatric symptoms (psychosis, agitation, anxiety) → seizures → movement disorders (orofacial dyskinesias, stereotypies) → decreased consciousness and autonomic instability → coma
- CSF: lymphocytic pleocytosis in 80%; antibodies in CSF more sensitive than serum
- Treatment: tumor removal (ovarian teratoma) + first-line immunotherapy (methylprednisolone 1g IV x5 days, IVIG 2g/kg, or plasmapheresis x5 cycles) → second-line (rituximab, cyclophosphamide) for no improvement in 10-14 days
- Recovery often prolonged (months to years) but generally good with treatment; relapses possible (especially without tumor)

**Other Autoimmune Encephalitis Antibodies:**

| Antibody | Association | Clinical Features |
|---|---|---|
| Anti-LGI1 | Rare (male >50); rarely thymoma | FBDS (faciobrachial dystonic seizures — brief unilateral arm/face jerks — pathognomonic), limbic encephalitis, hyponatremia |
| Anti-CASPR2 | Male >50; thymoma 20% | Limbic encephalitis, Morvan syndrome (insomnia, autonomic, cognitive, peripheral nerve hyperexcitability), neuromyotonia |
| Anti-AMPAR | Lung, breast, thymoma | Limbic encephalitis; frequent relapses |
| Anti-GABA-B | Lung cancer (SCLC) | Limbic encephalitis with prominent early seizures |
| Anti-DPPX | Lymphoma (DLBCL) | Hyperekplexia, PERM, autonomic |
| Anti-Hu | SCLC | Encephalomyelitis/sensory neuropathy; paraneoplastic |
| Anti-Yo | Breast, ovarian | Cerebellar degeneration; paraneoplastic |
| Anti-Ri | Breast, SCLC | Brainstem encephalitis, cerebellar, opsoclonus-myoclonus |
| Anti-Ma2 | Testicular (young men) | Limbic + diencephalic + brainstem; sleep-wake disruption |

---

## Neurodevelopmental Disorders

### Neural Tube Defects

- Spina bifida aperta (myelomeningocele): most severe; L2-L5 typically; lower limb paralysis, bowel/bladder dysfunction, Chiari II malformation (hindbrain herniation → hydrocephalus requiring VP shunt in 80-90%); latex allergy risk
- Prevention: folic acid 0.4mg/day for general population; 4mg/day for high-risk (prior NTD, AED use, MTHFR mutations)
- Valproate, carbamazepine, methotrexate: increase NTD risk

---

## Vestibular Disorders

### Benign Paroxysmal Positional Vertigo (BPPV)

- Most common cause of vertigo; posterior semicircular canal most common (90%); free-floating canalith (otoconia)
- Diagnosis: Dix-Hallpike maneuver → upbeat-torsional nystagmus (beats toward affected ear when lower), onset after 5-20 second latency, lasts <60 seconds, fatigable
- Treatment: Epley maneuver (posterior canal BPPV) — highly effective (NNT ~2); Barbecue roll (Lempert) for horizontal canal BPPV (geotropic horizontal nystagmus on roll test)
- Resolution spontaneous in weeks-months; Epley accelerates; avoid vestibular suppressants as they impair central compensation

### Vestibular Neuritis / Labyrinthitis

- Acute prolonged vertigo (days to weeks), nausea/vomiting, unsteadiness; no hearing loss (neuritis) or with hearing loss (labyrinthitis)
- Viral or post-viral inflammation of CN VIII (HSV-1 reactivation suspected)
- Spontaneous horizontal nystagmus beating away from lesion (fast phase to healthy side); Head impulse test positive (ipsilateral catch-up saccade)
- HINTS exam distinguishes from posterior fossa stroke (Head Impulse Normal + direction-changing nystagmus + Test of Skew deviation = central origin — highly sensitive for stroke)
- Treatment: short-term vestibular suppressants (meclizine, diazepam — only first 2-3 days; prolonged use delays compensation); oral methylprednisolone improves recovery (controversial); vestibular rehabilitation essential

### Meniere's Disease

- Endolymphatic hydrops; episodic vertigo (20 min to 12 hours) + fluctuating sensorineural hearing loss (low-frequency early) + tinnitus + aural fullness
- Low-sodium diet (<2g/day), diuretics (hydrochlorothiazide + triamterene), betahistine (European; not FDA-approved)
- Intratympanic gentamicin (ablative — controls vertigo but risks hearing) or steroids (non-ablative) for refractory
- Endolymphatic sac decompression surgery; labyrinthectomy (last resort)

---

## Key Drug Tables

### Common Drug-Induced Neurological Conditions

| Condition | Offending Drugs |
|---|---|
| Drug-induced Parkinsonism | Haloperidol, risperidone, metoclopramide, prochlorperazine, valproate, lithium, reserpine |
| Tardive dyskinesia | Antipsychotics (typical > atypical), metoclopramide (prolonged); tx: valbenazine (Ingrezza) or deutetrabenazine (VMAT2 inhibitors) |
| Serotonin syndrome | SSRIs + triptans, SSRIs + MAOIs, linezolid + SSRIs, tramadol + SSRIs; tx: cyproheptadine, benzodiazepines |
| Neuroleptic malignant syndrome | Antipsychotics, abrupt dopaminergic withdrawal; tx: dantrolene, bromocriptine, benzodiazepines |
| Peripheral neuropathy | Vincristine, cisplatin, paclitaxel, metronidazole, isoniazid (give B6), nitrofurantoin, thalidomide |
| Myopathy/rhabdomyolysis | Statins (especially high-dose + CYP3A4 inhibitors), colchicine, chloroquine, corticosteroids (chronic), zidovudine |
| Seizures | Tramadol, bupropion, cocaine, amphetamines, imipenem, FQ at high dose, isoniazid, theophylline, lithium toxicity |
| Encephalopathy | Methotrexate, ifosfamide, tacrolimus (PRES), cyclosporine (PRES), lithium toxicity, opioids |

---

## Neurological Emergencies Summary Table

| Emergency | Key Diagnosis Points | Critical Initial Steps |
|---|---|---|
| Status epilepticus | Seizure >5 min or recurrent without recovery | Airway, lorazepam IV, glucose, thiamine; escalate to fosphenytoin/LEV/VPA at 20 min |
| Ischemic stroke | Sudden focal deficit; time of onset | CT head (no bleed), glucose, BP; tPA if eligible; thrombectomy referral if LVO |
| SAH | Thunderclap headache | CT head; LP if CT negative; neurosurgery + endovascular |
| ICH | Focal deficit + CT bleed | BP control; reverse anticoagulation; neurosurgery |
| Bacterial meningitis | Fever + headache + meningismus | Blood cultures; empiric antibiotics + dexamethasone IMMEDIATELY; LP if safe |
| Myasthenic crisis | Respiratory failure in MG | Intubate (early); IVIG or PLEX; hold pyridostigmine |
| Herniation (uncal) | Fixed dilated pupil + decreasing GCS | Mannitol 1g/kg IV or hypertonic saline; hyperventilate; emergent neurosurgery |
| Spinal cord compression | Bilateral weakness + sensory level + bowel/bladder | Dexamethasone; emergent MRI; radiation +/- surgery |
| GBS respiratory failure | FVC <20mL/kg or MIF > -30 | Intubate; IVIG 2g/kg or PLEX x5 |
| Posterior fossa stroke | Sudden ataxia/dysarthria/diplopia + HINTS exam | CT (normal early); MRI DWI; cerebellar infarct → monitor for edema, suboccipital craniectomy |

---

*End of neurology.md — Zia Venture Group Medical Knowledge Base*
