# Infectious Disease — Clinical Reference

Knowledge base for infectious disease diagnosis, treatment, prophylaxis, and antimicrobial stewardship. Intended for Open WebUI RAG system. Chunk size 1500, overlap 200, Top K 5.

---

## Table of Contents

1. HIV/AIDS
2. Tuberculosis
3. Sexually Transmitted Infections
4. Bacterial Meningitis and Encephalitis
5. Clostridioides difficile Infection
6. Infective Endocarditis
7. Osteomyelitis and Septic Arthritis
8. Lyme Disease
9. Influenza
10. Antimicrobial Stewardship

---

## 1. HIV/AIDS

### CD4 Count Staging and Clinical Correlates

CD4 count is the primary marker of immune function in HIV infection. Viral load reflects disease activity and treatment efficacy.

| CD4 Count (cells/mm3) | Stage | Clinical Significance |
|---|---|---|
| >500 | Stage 1 (CDC) | Normal immune function; asymptomatic or constitutional symptoms |
| 200–499 | Stage 2 (CDC) | Increased susceptibility to bacterial infections, thrush, herpes zoster |
| <200 | Stage 3 (AIDS) | High risk for AIDS-defining opportunistic infections |
| <100 | Advanced AIDS | Toxoplasmosis, Cryptococcus, CMV retinitis risk |
| <50 | Severe immunosuppression | MAC, CMV, PML risk markedly elevated |

AIDS is defined by CD4 <200 cells/mm3 OR the presence of an AIDS-defining condition regardless of CD4 count.

### AIDS-Defining Conditions (CDC Category C)

- Pneumocystis jirovecii pneumonia (PCP)
- Toxoplasma gondii encephalitis
- Cryptococcal meningitis
- Cytomegalovirus (CMV) retinitis or end-organ disease
- Mycobacterium avium complex (MAC) disseminated disease
- Mycobacterium tuberculosis (pulmonary or extrapulmonary)
- Candida esophagitis (NOT oral thrush alone)
- Recurrent bacterial pneumonia (>=2 episodes in 12 months)
- Recurrent Salmonella septicemia
- Cryptosporidiosis (>1 month duration)
- Isosporiasis (>1 month duration)
- Progressive multifocal leukoencephalopathy (PML) — JC virus
- Primary CNS lymphoma
- Kaposi sarcoma
- Invasive cervical carcinoma
- Burkitt lymphoma or immunoblastic lymphoma
- HIV encephalopathy (AIDS dementia complex)
- HIV wasting syndrome (>10% body weight loss)
- Histoplasmosis disseminated
- Coccidioidomycosis disseminated
- Lymphoid interstitial pneumonia (in children)

### Antiretroviral Drug Classes

| Class | Abbreviation | Mechanism | Key Agents |
|---|---|---|---|
| Nucleoside/Nucleotide Reverse Transcriptase Inhibitors | NRTI | Competitive inhibitor of RT; chain termination | Tenofovir (TDF/TAF), emtricitabine (FTC), abacavir (ABC), lamivudine (3TC), zidovudine (ZDV) |
| Non-Nucleoside Reverse Transcriptase Inhibitors | NNRTI | Non-competitive allosteric inhibition of RT | Efavirenz, rilpivirine, doravirine, etravirine |
| Protease Inhibitors | PI | Block HIV protease; prevent viral maturation | Darunavir, atazanavir, lopinavir (all boosted with ritonavir or cobicistat) |
| Integrase Strand Transfer Inhibitors | INSTI | Block integration of viral DNA into host genome | Dolutegravir (DTG), bictegravir (BIC), raltegravir, elvitegravir, cabotegravir |
| CCR5 Antagonists | CCR5 | Block CCR5 co-receptor; prevent viral entry | Maraviroc (requires tropism testing) |
| Fusion Inhibitors | FI | Block gp41-mediated fusion | Enfuvirtide (T-20) — subcutaneous injection, reserved for salvage |
| Post-Attachment Inhibitors | PAI | Block gp120-CD4 binding | Ibalizumab (IV, salvage) |
| Capsid Inhibitor | CAI | Inhibits HIV capsid protein | Lenacapavir (injectable, q6mo, salvage or prevention) |

### Preferred First-Line ART Regimens (DHHS Guidelines 2024)

**Preferred regimen for most treatment-naive adults:**
- **Biktarvy** (bictegravir 50mg / tenofovir alafenamide 25mg / emtricitabine 200mg) — one tablet once daily with food
- **Dolutegravir-based regimens:**
  - Dolutegravir 50mg + tenofovir alafenamide 25mg/emtricitabine 200mg (Descovy backbone)
  - Dolutegravir 50mg + tenofovir disoproxil fumarate 300mg/emtricitabine 200mg (Truvada backbone, preferred when cost is a factor)

**Alternative regimens:**
- Doravirine/TDF/3TC (Delstrigo) — NNRTI-based, once daily
- Darunavir/cobicistat + TAF/FTC — PI-based, for patients with concern for INSTI resistance
- Rilpivirine/TAF/FTC (Odefsey) — only when pre-ART VL <100,000 and CD4 >200

**Specific populations:**
- Pregnancy: dolutegravir preferred (safety data now supports use in first trimester; efavirenz acceptable alternative); avoid unboosted regimens
- Renal impairment (CrCl <30): use TAF over TDF; avoid TDF if CrCl <50
- HBV coinfection: regimen must contain TDF or TAF + FTC or 3TC (dual HBV coverage)
- TB coinfection: rifampin interaction — use dolutegravir 50mg BID (standard dose BID) or efavirenz; rifabutin preferred over rifampin with PI-based regimens

### Treatment Goals

- Viral suppression to undetectable (<20–50 copies/mL depending on assay) within 24 weeks
- CD4 recovery (aim >200; immunologic non-responders plateau despite VLS)
- Viral load monitoring: at initiation, 2–4 weeks, then every 3–6 months when stable
- U=U (Undetectable = Untransmittable): sustained VL <200 copies/mL eliminates sexual transmission risk

### Opportunistic Infection Prophylaxis

| Infection | Indication (CD4 threshold) | First-Line Prophylaxis | Alternative |
|---|---|---|---|
| Pneumocystis jirovecii pneumonia (PCP) | CD4 <200 cells/mm3 OR oropharyngeal candidiasis | TMP-SMX DS (160/800mg) 1 tab PO daily | TMP-SMX SS daily; dapsone 100mg daily; atovaquone 1500mg daily; aerosolized pentamidine 300mg monthly |
| Toxoplasma gondii (primary prophylaxis) | CD4 <100 AND seropositive (IgG+) | TMP-SMX DS 1 tab PO daily (also covers PCP) | TMP-SMX SS daily; dapsone 50mg + pyrimethamine 50mg weekly + leucovorin 25mg weekly |
| Mycobacterium avium complex (MAC) | CD4 <50 cells/mm3 (if ART not started or not suppressed) | Azithromycin 1200mg PO weekly | Clarithromycin 500mg BID; rifabutin 300mg daily |
| CMV (secondary prophylaxis/maintenance) | CD4 <50 — surveillance with ophthalmology | Dilated fundoscopic exam q3–6 months; valganciclovir for active disease | — |
| Cryptococcus neoformans (primary) | Not routinely recommended in US; consider in endemic regions if CD4 <100 | Fluconazole 200mg daily (in high-prevalence settings) | — |
| Histoplasma (primary) | CD4 <150 + high-exposure risk in endemic area | Itraconazole 200mg daily | — |
| Coccidioidomycosis | CD4 <250 in endemic area with + serology | Fluconazole 400mg daily | — |
| Tuberculosis (LTBI) | Positive TST (>=5mm in HIV) or IGRA regardless of CD4 | Isoniazid 300mg daily x9mo + pyridoxine 25mg daily | 3HP weekly x12 doses; rifampin 4mo (check ART interactions) |

**Discontinuing prophylaxis:**
- PCP prophylaxis can be discontinued when CD4 >200 for >=3 months on ART with suppressed VL
- MAC prophylaxis can be discontinued when CD4 >100 for >=3 months
- Toxoplasma secondary prophylaxis can be discontinued when CD4 >200 for >=6 months

### Opportunistic Infection Treatment

#### Pneumocystis jirovecii Pneumonia (PCP)

**Diagnosis:** CT ground-glass bilateral infiltrates; LDH elevated; induced sputum or BAL with GMS stain; beta-D-glucan elevated

**First-line treatment:**
- Trimethoprim-sulfamethoxazole (TMP-SMX): **15–20 mg/kg/day** of TMP component IV or PO divided every 6–8 hours x 21 days
- Dose calculation example: 75kg patient = TMP 1125–1500mg/day = approximately 4 DS tabs PO every 8 hours

**Adjunctive corticosteroids (mandatory when PaO2 <70 mmHg on room air OR A-a gradient >35 mmHg):**
- Prednisone 40mg PO BID days 1–5 → 40mg daily days 6–10 → 20mg daily days 11–21
- Reduces mortality by approximately 50% in moderate-severe disease

**Alternatives:**
- Pentamidine 4mg/kg IV daily x21 days (significant toxicity: hypoglycemia, nephrotoxicity, arrhythmia)
- Primaquine 30mg PO daily + clindamycin 600mg IV q8h or 450mg PO q6h x21 days (check G6PD first)
- Atovaquone 750mg PO BID x21 days (mild disease only)

**ART timing in PCP:** Start ART within 2 weeks of PCP diagnosis (improves outcomes)

#### Toxoplasma Encephalitis

**Diagnosis:** Ring-enhancing lesions on MRI (multiple, basal ganglia common); seropositive (IgG+); empiric treatment trial if CD4 <200

**Treatment:**
- **Pyrimethamine** 200mg PO loading dose, then 50mg (<60kg) or 75mg (>=60kg) PO daily
- **Sulfadiazine** 1000mg (<60kg) or 1500mg (>=60kg) PO every 6 hours
- **Leucovorin** 10–25mg PO daily (prevents pyrimethamine-induced bone marrow toxicity; increase to 50mg if cytopenias)
- Duration: Minimum 6 weeks (acute induction), then maintenance therapy

**Maintenance (secondary prophylaxis):**
- Pyrimethamine 25–50mg + sulfadiazine 2000–4000mg/day + leucovorin 10–25mg daily
- Discontinue when CD4 >200 for >=6 months on ART

**Alternative (sulfa allergy):**
- Pyrimethamine + leucovorin + clindamycin 600mg IV/PO q6h

**Clinical response:** Improvement on MRI expected by day 14; failure to improve = biopsy for primary CNS lymphoma

#### Cryptococcal Meningitis

**Diagnosis:** CSF India ink, cryptococcal antigen (CrAg) serum/CSF — high sensitivity; fungal culture

**Induction (2 weeks):**
- **Liposomal amphotericin B 3–4mg/kg IV daily** + **flucytosine (5-FC) 25mg/kg PO QID**
- Alternative induction: amphotericin B deoxycholate 0.7–1mg/kg/day (more nephrotoxic) + flucytosine
- Monitor: BMP daily (K, Cr, Mg); CBC for 5-FC bone marrow suppression; 5-FC levels if renal impairment

**Consolidation (8 weeks):**
- Fluconazole 400mg PO daily

**Maintenance (secondary prophylaxis, minimum 12 months):**
- Fluconazole 200mg PO daily
- Discontinue when CD4 >100 for >=3 months, VL suppressed, symptoms resolved

**ICP management (critical):**
- Increased ICP is a major cause of morbidity/mortality
- Lumbar puncture to drain CSF if opening pressure >25 cmH2O
- Daily LPs until opening pressure <20 cmH2O for 2 consecutive days
- Lumbar drain or Ommaya reservoir for refractory elevated ICP
- Do NOT use steroids (worsen outcomes in Cryptococcal meningitis)

#### Cytomegalovirus (CMV) Disease

**CMV Retinitis (most common AIDS-defining CMV manifestation):**
- Presentation: painless vision changes, floaters, decreased acuity; CD4 typically <50
- Diagnosis: ophthalmology exam (hemorrhagic retinal lesions — "pizza pie" or "scrambled eggs" pattern)
- **Valganciclovir 900mg PO BID x21 days** (induction), then 900mg daily (maintenance)
- Intravitreal ganciclovir injections for immediate sight-threatening lesions (zone 1)
- Discontinue maintenance when CD4 >100 for >=3–6 months

**CMV Esophagitis/Colitis:**
- Valganciclovir 900mg PO BID x3–6 weeks (colitis 3–4 weeks, esophagitis 3 weeks)
- IV ganciclovir 5mg/kg q12h if unable to take oral medications

**CMV Encephalitis:**
- IV ganciclovir 5mg/kg q12h + foscarnet 90mg/kg q12h (combination)
- Prognosis poor; ART initiation critical

#### Disseminated Mycobacterium avium Complex (MAC)

**Diagnosis:** Blood cultures (lysis-centrifugation); bone marrow biopsy; AFB smear/culture of tissue

**Treatment (minimum 12 months, until immune recovery):**
- Clarithromycin 500mg PO BID + ethambutol 15mg/kg/day PO
- Add rifabutin 300mg daily for severe disease or high MAC burden
- Azithromycin 500–600mg daily can substitute clarithromycin

**Monitoring:** Monthly CBC, LFTs, visual acuity (EMB)

### Immune Reconstitution Inflammatory Syndrome (IRIS)

IRIS occurs when ART restores immune function and causes paradoxical worsening of a previously treated or subclinical OI.

**Types:**
- **Paradoxical IRIS:** Known OI, treated, then worsens after ART initiation
- **Unmasking IRIS:** Subclinical OI becomes apparent after ART initiation

**Common presentations:**
- TB-IRIS: fever, lymphadenopathy, worsening pulmonary infiltrates (most common)
- Cryptococcal IRIS: meningitis, lymphadenitis
- MAC-IRIS: fever, lymphadenitis, hepatosplenomegaly
- CMV-IRIS: vitritis, uveitis

**Risk factors:** Low pre-ART CD4 (<50), high viral load, early ART initiation (<2 weeks of OI therapy)

**Management:**
- Continue ART (do NOT stop ART in most cases)
- Continue OI treatment
- NSAIDs for mild-moderate IRIS
- Prednisone 1mg/kg/day for severe IRIS (not for Cryptococcal IRIS without careful consideration)
- Defer ART in Cryptococcal meningitis to 4–6 weeks post-treatment initiation (paradoxical IRIS mortality risk)

### Pre-Exposure Prophylaxis (PrEP)

**Indications:**
- HIV-negative individuals at substantial risk: MSM with condomless anal sex, heterosexual with HIV+ partner or multiple partners, PWID sharing needles

**Regimens:**

| Regimen | Dosing | Notes |
|---|---|---|
| Tenofovir disoproxil fumarate / emtricitabine (Truvada) | 1 tablet PO daily (continuous) | Original FDA-approved; generic available; renal monitoring required |
| Tenofovir alafenamide / emtricitabine (Descovy) | 1 tablet PO daily | Better renal/bone profile; approved for anal sex risk; NOT approved for receptive vaginal sex |
| Cabotegravir (Apretude) | 600mg IM q2 months (after 2 loading doses 4 weeks apart) | Long-acting injectable; superior efficacy to oral TDF/FTC in trials; no pills; requires clinic visits |

**Monitoring (oral PrEP):** HIV test q3mo, STI screen q3mo, renal function q6mo (TDF-based) or q12mo (TAF-based), HBV status at baseline

**Efficacy:** Oral TDF/FTC reduces HIV acquisition risk by 99% with perfect adherence; cabotegravir may be slightly superior

**On-demand PrEP (2-1-1 / event-driven):** TDF/FTC only; 2 tablets 2–24h before sex, 1 tablet 24h after, 1 tablet 48h after; validated in MSM only (IPERGAY trial)

### Post-Exposure Prophylaxis (PEP)

**Initiation window:** Within **72 hours** of exposure (the sooner the better; do not delay)

**Duration:** 28 days

**Preferred regimen:**
- **Tenofovir disoproxil fumarate 300mg / emtricitabine 200mg (Truvada) + dolutegravir 50mg** PO daily x28 days
- Alternative: TDF/FTC + raltegravir 400mg BID

**Occupational exposures:** Same regimen; assess source patient HIV status if possible

**Follow-up testing:** HIV test at baseline, 4–6 weeks, 3 months

**Consultation:** PEP hotline available 24/7 (1-888-448-4911, US)

---

## 2. Tuberculosis

### Diagnosis

**Tuberculin Skin Test (TST) — Mantoux Method:**

| Induration Threshold | Population |
|---|---|
| >=5 mm | HIV-positive; recent close contact of active TB case; organ transplant or other immunosuppressed (>15mg prednisone/day >1mo); prior abnormal CXR consistent with TB |
| >=10 mm | Recent immigrants (<5 years) from high-prevalence countries; injection drug users; residents/employees of high-risk settings (prisons, nursing homes, homeless shelters); mycobacteriology lab workers; children <4 years; children exposed to adults in high-risk categories |
| >=15 mm | All other persons with no known risk factors |

**Interferon-Gamma Release Assay (IGRA):**
- QuantiFERON-TB Gold Plus (QFT-Plus) or T-SPOT.TB
- Preferred over TST in BCG-vaccinated individuals (no false positives from BCG)
- Single visit (no return for reading)
- Preferred for: BCG-vaccinated, unlikely to return, prior false-positive TST
- Indeterminate result: repeat testing; if persistent, treat as positive in high-risk individuals

**Note:** Two-step TST recommended for initial testing of healthcare workers (rules out boosting effect from prior TST)

### Active TB Diagnosis

- Acid-fast bacilli (AFB) smear: rapid, low sensitivity (~50%); three sputum samples
- Culture: gold standard; 2–6 weeks for results; speciation and DST
- NAAT (nucleic acid amplification test): rapid (hours); Xpert MTB/RIF — simultaneously detects TB and rifampin resistance (proxy for MDR-TB)
- Symptom triad: productive cough >3 weeks + night sweats + weight loss; hemoptysis, fever
- CXR: upper lobe infiltrates, cavitation, hilar adenopathy; miliary pattern in disseminated disease

### Active TB Treatment — RIPE Regimen

**Phases:**
- **Intensive phase:** 2 months (RIPE — all 4 drugs)
- **Continuation phase:** 4 months (RI — rifampin + isoniazid)
- Total duration: **6 months** for drug-susceptible pulmonary TB

| Drug | Abbreviation | Daily Dose (standard) | Monitoring | Key Adverse Effects |
|---|---|---|---|---|
| Rifampin | R (RIF) | 10mg/kg (max 600mg) PO daily | LFTs baseline and monthly if abnormal; drug interactions | Orange discoloration of body fluids; drug-drug interactions (CYP450 inducer — reduces levels of warfarin, OCPs, PIs, methadone, etc.); hepatotoxicity; flu-like syndrome |
| Isoniazid | I (INH) | 5mg/kg (max 300mg) PO daily | LFTs monthly; peripheral neuropathy symptoms | Hepatotoxicity (monitor AST/ALT; hold if >3x ULN with symptoms or >5x ULN); peripheral neuropathy (prevented by pyridoxine 25–50mg daily); drug-induced lupus; CNS effects |
| Pyrazinamide | Z (PZA) | 25–35mg/kg (max 2000mg) PO daily | LFTs, uric acid baseline and monthly | Hepatotoxicity; hyperuricemia (gout); arthralgia; rash |
| Ethambutol | E (EMB) | 15–20mg/kg (max 1600mg) PO daily | Visual acuity and color discrimination monthly (Snellen chart + Ishihara plates) | Optic neuritis (dose-dependent; usually reversible if caught early; avoid in young children unable to report visual changes); peripheral neuropathy |

**Pyridoxine (Vitamin B6) supplementation:**
- Isoniazid 25–50mg daily with INH to prevent peripheral neuropathy
- Mandatory in: pregnancy, malnutrition, alcoholism, HIV, diabetes, CKD, elderly

**Directly Observed Therapy (DOT):** Recommended for all active TB patients to ensure adherence and prevent resistance

**Monitoring parameters:**
- LFTs monthly (or at baseline, 2 weeks, then monthly)
- Hold hepatotoxic drugs if: AST/ALT >3x ULN with symptoms; >5x ULN without symptoms
- Hold pyrazinamide if jaundice or significant LFT elevation
- Visual acuity before EMB initiation and monthly during therapy

### Special TB Situations

#### CNS Tuberculosis (TB Meningitis)

- Duration: **9–12 months** (vs. 6 months for pulmonary)
- RIPE x2 months, then RI x7–10 months
- Rifampin penetrates CSF; INH excellent CSF penetration
- **Adjunctive dexamethasone** (ALL patients): 0.4mg/kg/day tapered over 6–8 weeks — reduces mortality
- Dexamethasone: weeks 1–2: 0.4mg/kg/day → weeks 3–4: 0.3mg/kg/day → weeks 5–6: 0.2mg/kg/day → weeks 7–8: 0.1mg/kg/day → then taper off over 1–2 weeks

#### Bone/Joint TB

- Duration: **9 months** (RIPE x2 months + RI x7 months)

#### Miliary/Disseminated TB

- Standard 6-month RIPE regimen; some experts extend to 9 months
- Consider meningitis protocol if CSF involvement

### Latent TB Infection (LTBI) Treatment

| Regimen | Abbreviation | Duration | Dosing | Notes |
|---|---|---|---|---|
| Isoniazid daily | 9H | 9 months | INH 300mg PO daily + pyridoxine 25mg daily | Oldest regimen; most evidence; low pill burden |
| Isoniazid + rifapentine weekly | 3HP | 12 weeks | INH 15mg/kg (max 900mg) + rifapentine 900mg PO once weekly under DOT + pyridoxine 50mg | Preferred; high completion rates; NOT for HIV on ART (rifapentine interactions), pregnancy, children <2 |
| Rifampin daily | 4R | 4 months | Rifampin 10mg/kg (max 600mg) PO daily | Preferred when INH resistant; numerous drug interactions; acceptable in HIV if ART adjusted |
| Isoniazid + rifampin daily | 3HR | 3 months | INH 300mg + rifampin 600mg PO daily | Acceptable alternative |

**Exclusions before LTBI treatment:** Rule out active TB (symptoms, CXR); prior treatment for LTBI; significant hepatic disease

### Drug-Resistant Tuberculosis

**Definitions:**
- **MDR-TB:** Resistant to at least rifampin + isoniazid (the two most important first-line drugs)
- **Pre-XDR-TB:** MDR/RR-TB + resistance to any fluoroquinolone
- **XDR-TB:** MDR/RR-TB + resistance to fluoroquinolone + at least one of bedaquiline or linezolid

**MDR-TB preferred regimen (BPaL or BPaLM):**
- **Bedaquiline** 400mg PO daily x2 weeks → 200mg 3x/week x22 weeks
- **Pretomanid** 200mg PO daily x26 weeks
- **Linezolid** 600mg PO daily x26 weeks
- +/- **Moxifloxacin** (if susceptible) — BPaLM regimen (6 months total)
- QTc monitoring required (bedaquiline + moxifloxacin both prolong QTc)
- Clofazimine as alternative backbone agent

**Duration:** Minimum 6 months (with new regimens); previously 18–24 months with older regimens

### TB-HIV Coinfection

- **ART timing:** Start ART **within 2 weeks** of TB treatment initiation for patients with CD4 <50; within 8–12 weeks if CD4 >50 (WHO/DHHS)
- Exception: TB meningitis — delay ART 4–8 weeks (early ART increases TB-IRIS-related mortality in CNS TB)
- **Drug interactions:**
  - Rifampin is a potent CYP450 inducer — reduces plasma levels of most PIs by 75–90%
  - **Rifabutin** preferred over rifampin when using PI-based ART (less induction)
  - Rifabutin dose with boosted darunavir: 150mg every other day (reduced due to PI-mediated CYP3A4 inhibition raising rifabutin levels)
  - Dolutegravir: increase to 50mg BID with rifampin; standard dose with rifabutin
  - Efavirenz: standard dose with rifampin (efavirenz is a CYP inducer itself; some guidelines increase to 800mg/day in patients >60kg)

---

## 3. Sexually Transmitted Infections

### Gonorrhea

**Pathogen:** Neisseria gonorrhoeae

**Presentation:**
- Males: urethritis (dysuria, purulent discharge), epididymitis
- Females: cervicitis (mucopurulent cervical discharge), often asymptomatic; PID, Bartholin gland abscess
- Both: pharyngitis, proctitis, conjunctivitis

**Uncomplicated Urogenital/Rectal/Pharyngeal Gonorrhea:**
- **Ceftriaxone 500mg IM single dose** (CDC 2021 guidelines; if weight >=150kg: 1g IM)
- If chlamydia coinfection NOT ruled out: add doxycycline 100mg BID x7d
- Test of cure at pharyngeal site only (pharynx is more difficult to clear; 1–2 weeks post-treatment)

**Disseminated Gonococcal Infection (DGI):**
- Triad: tenosynovitis, dermatitis (petechial/pustular skin lesions), polyarthralgia (bacteremic phase)
- Or septic monoarthritis (localized phase)
- **Ceftriaxone 1g IV q24h** until improvement (minimum 24–48h after clinical improvement)
- Then step down to oral cefixime 400mg BID to complete 7-day total course
- Ophthalmology consultation if gonococcal conjunctivitis (ophthalmia neonatorum in neonates)

**Ceftriaxone allergy (true IgE-mediated):**
- Consult ID; gentamicin 240mg IM + azithromycin 2g PO (only if susceptibility confirmed)

**Resistance monitoring:** Gonococcal Isolate Surveillance Project (GISP); fluoroquinolone resistance widespread — NOT recommended empirically

### Chlamydia

**Pathogen:** Chlamydia trachomatis (D–K serovars)

**Presentation:** Often asymptomatic; urethritis, cervicitis, epididymitis, proctitis, reactive arthritis (Reiter syndrome)

**Treatment:**
- **Doxycycline 100mg PO BID x7 days** (preferred for urogenital and rectal)
- Azithromycin 1g PO single dose (alternative; lower efficacy for rectal chlamydia)
- Levofloxacin 500mg PO daily x7 days (alternative if doxycycline intolerable)

**Pregnancy:**
- Azithromycin 1g PO single dose (preferred; doxycycline contraindicated in pregnancy)
- Amoxicillin 500mg PO TID x7 days (alternative)

**Lymphogranuloma venereum (LGV) — L1–L3 serovars:**
- Doxycycline 100mg PO BID x21 days

**Test of cure:** Not routinely recommended except in pregnancy (retest 3–4 weeks after treatment)

### Syphilis

**Pathogen:** Treponema pallidum

**Serology interpretation:**

| Test | Type | Notes |
|---|---|---|
| RPR (Rapid Plasma Reagin) | Non-treponemal | Quantitative titer; used for screening and treatment monitoring; can be false-positive (pregnancy, autoimmune, viral infections) |
| VDRL | Non-treponemal | Similar to RPR; used in CSF for neurosyphilis diagnosis |
| FTA-ABS (Fluorescent Treponemal Antibody Absorbed) | Treponemal | Confirmatory; remains positive for life after infection |
| TP-PA | Treponemal | Confirmatory; equivalent to FTA-ABS |
| CIA/EIA | Treponemal | Used in reverse sequence screening algorithm |

**Stages and Treatment:**

| Stage | Clinical Features | Treatment | Notes |
|---|---|---|---|
| Primary | Painless chancre (genital, oral, anal); regional lymphadenopathy; heals spontaneously | Benzathine penicillin G 2.4 million units IM x1 dose | Highly infectious; multiple chancres possible |
| Secondary | Diffuse rash (palms/soles); condyloma lata; mucous patches; systemic (fever, malaise, lymphadenopathy) | Benzathine penicillin G 2.4 million units IM x1 dose | Most infectious stage; resolves without treatment |
| Early latent (<1 year duration) | No symptoms; reactive serology; exposure within past year | Benzathine penicillin G 2.4 million units IM x1 dose | |
| Late latent (>1 year or unknown duration) | No symptoms; reactive serology | Benzathine penicillin G 2.4 million units IM weekly x3 doses | Treat if cannot exclude late latent |
| Tertiary (gummatous, cardiovascular, or neurosyphilis) | Granulomatous lesions; aortic regurgitation/aneurysm; tabes dorsalis; general paresis | Aqueous crystalline penicillin G 18–24 million units/day IV x10–14 days | CSF evaluation recommended before tertiary treatment; CSF-VDRL may be negative |
| Neurosyphilis | Meningitis, cranial nerve palsies, uveitis, dementia, tabes dorsalis; can occur at any stage | Aqueous crystalline penicillin G 3–4 million units IV q4h x14 days | Always check CSF before designating neurosyphilis; follow-up LP at 6 months |
| Ocular syphilis | Uveitis, panuveitis; vision changes | Same as neurosyphilis (IV penicillin) | Ophthalmology co-management; incidence rising |

**Monitoring:** RPR titer should decline 4-fold (2 dilutions) by 6–12 months post-treatment; failure = retreatment or neurosyphilis workup

**Jarisch-Herxheimer Reaction:**
- Occurs 2–8 hours after first penicillin dose (especially secondary syphilis)
- Fever, chills, myalgia, tachycardia, transient hypotension
- Self-limited (resolves in 12–24 hours)
- Management: antipyretics (acetaminophen), hydration; do NOT stop penicillin
- Warn patients before treatment; may precipitate preterm labor in pregnant patients

**Penicillin allergy:**
- **Penicillin desensitization preferred** (especially for neurosyphilis and pregnancy)
- Doxycycline 100mg BID x14 days (primary/secondary/early latent — non-pregnant only; less evidence)
- No reliable alternative to penicillin for neurosyphilis or pregnancy

### Genital Herpes (HSV-1 and HSV-2)

**Diagnosis:** Clinical + PCR of ulcer base (gold standard); type-specific serology (IgG)

**Treatment regimens:**

| Indication | Drug | Dose | Duration |
|---|---|---|---|
| First episode (primary) | Acyclovir | 400mg PO TID or 200mg PO 5x/day | 7–10 days (extend if incomplete healing) |
| First episode (primary) | Valacyclovir | 1000mg PO BID | 7–10 days |
| First episode (primary) | Famciclovir | 250mg PO TID | 7–10 days |
| Recurrent episode | Acyclovir | 400mg PO TID | 5 days |
| Recurrent episode | Valacyclovir | 500mg PO BID | 3 days |
| Recurrent episode | Valacyclovir | 1000mg PO daily | 5 days |
| Recurrent episode | Famciclovir | 125mg PO BID | 5 days |
| Daily suppressive therapy | Valacyclovir | 500mg PO daily (if <=9 recurrences/year) or 1000mg daily (>=10 recurrences/year) | Ongoing |
| Daily suppressive therapy | Acyclovir | 400mg PO BID | Ongoing |
| Daily suppressive therapy | Famciclovir | 250mg PO BID | Ongoing |
| Severe/disseminated (immunocompromised) | Acyclovir | 5–10mg/kg IV q8h | 2–7 days, then PO to complete 10 days |

**Suppressive therapy indications:**
- Frequent recurrences (>=6/year)
- Psychological distress
- Reduction of transmission to serodiscordant partner (reduces transmission ~50%)

### Pelvic Inflammatory Disease (PID)

**Diagnostic criteria (CDC):** Minimum criteria = uterine tenderness OR adnexal tenderness OR cervical motion tenderness in a sexually active woman with no other identified cause

**Additional criteria (increase specificity):**
- Oral temperature >38.3 degrees C; mucopurulent cervical discharge; elevated ESR/CRP; laboratory documentation of cervical gonorrhea or chlamydia; WBC on saline microscopy

**Outpatient Regimen (mild-moderate PID):**
- Ceftriaxone 500mg IM x1 PLUS doxycycline 100mg PO BID x14 days PLUS metronidazole 500mg PO BID x14 days
- Alternative: cefoxitin 2g IM + probenecid 1g PO (single dose) + doxycycline 100mg BID x14 days + metronidazole 500mg BID x14 days

**Inpatient Regimen (indications: surgical emergency not excluded, severe illness, tubo-ovarian abscess, unable to tolerate oral, no outpatient response at 72h, pregnancy):**

Regimen A (parenteral):
- Cefoxitin 2g IV q6h (or cefotetan 2g IV q12h) + doxycycline 100mg IV/PO q12h
- Transition to oral doxycycline 100mg BID when clinical improvement (usually 24–48h IV)
- Add metronidazole 500mg PO BID if TOA present

Regimen B (parenteral, alternative):
- Clindamycin 900mg IV q8h + gentamicin 2mg/kg IV loading dose, then 1.5mg/kg q8h (or 5mg/kg daily)
- Transition to oral clindamycin 450mg QID or doxycycline 100mg BID

**Total duration (outpatient + inpatient combined):** 14 days

**Tubo-ovarian abscess (TOA):**
- Inpatient IV antibiotics; surgical drainage if no improvement at 72h; laparoscopy or IR-guided drainage

### Bacterial Vaginosis (BV)

**Diagnosis (Amsel criteria — 3 of 4):** Thin, gray-white homogeneous discharge; clue cells on wet prep; vaginal pH >4.5; positive whiff test (10% KOH → fishy amine odor)

**Treatment:**
- Metronidazole 500mg PO BID x7 days (first-line)
- Metronidazole 0.75% gel intravaginal daily x5 days
- Clindamycin 2% cream intravaginal at bedtime x7 days
- Tinidazole 2g PO daily x2 days or 1g PO daily x5 days (alternative)
- Secnidazole 2g PO single dose (alternative)

**Recurrent BV:**
- Metronidazole 0.75% gel intravaginally 2x/week x4–6 months (suppressive)
- Boric acid 600mg intravaginal daily x21 days (compounded)

### Trichomonas vaginalis

**Presentation:** Frothy, yellow-green vaginal discharge; vulvar pruritis; "strawberry cervix" (punctate hemorrhages); often asymptomatic in males

**Treatment:**
- **Females:** Metronidazole 500mg PO BID x7 days (preferred; superior efficacy over single dose)
- **Males:** Metronidazole 2g PO single dose
- Tinidazole 2g PO single dose (alternative; better tolerated)
- Treat sex partners
- Avoid alcohol during treatment and 48h after metronidazole; 72h after tinidazole

**Metronidazole resistance:** Tinidazole 2g PO daily x7 days; consultation with CDC STI hotline

### HPV (Human Papillomavirus)

**Vaccination — ACIP Recommendations:**
- Gardasil-9 (9-valent, types 6, 11, 16, 18, 31, 33, 45, 52, 58)
- Routine vaccination: age 11–12 years (can start at age 9)
- Catch-up vaccination: through age 26 for all; ages 27–45 (shared clinical decision-making)
- 2-dose series if starting before age 15; 3-dose series if starting age 15 or older, or immunocompromised
- Schedule (3-dose): 0, 1–2, 6 months

**External genital warts (condyloma acuminata):**
- Provider-applied: trichloroacetic acid (TCA) 80–90% weekly; podophyllin 10–25%; cryotherapy
- Patient-applied: imiquimod 5% cream 3x/week up to 16 weeks; podofilox 0.5% solution BID x3 days, repeat weekly up to 4 cycles
- Sinecatechins 15% ointment (patient-applied alternative)

---

## 4. Bacterial Meningitis and Encephalitis

### Organisms by Patient Population

| Population | Most Common Organisms |
|---|---|
| Neonates (<1 month) | Group B Streptococcus, E. coli, Listeria monocytogenes, Klebsiella |
| Infants 1–3 months | Group B Strep, E. coli, Listeria, N. meningitidis, S. pneumoniae |
| Children 3 months–18 years | N. meningitidis, S. pneumoniae |
| Young adults 18–50 years | N. meningitidis, S. pneumoniae |
| Adults >50 years | S. pneumoniae, N. meningitidis, Listeria monocytogenes, gram-negative bacilli |
| Immunocompromised/HIV | S. pneumoniae, Listeria, Cryptococcus neoformans, Mycobacterium tuberculosis |
| Post-neurosurgery/trauma/CSF shunt | Staphylococcus aureus, coagulase-negative staph, gram-negative bacilli (Pseudomonas, Acinetobacter) |
| Healthcare-associated (nosocomial) | Gram-negative bacilli, S. aureus, Enterococcus |

### CSF Interpretation Table

| Parameter | Normal | Bacterial | Viral | Fungal/TB | HSV Encephalitis |
|---|---|---|---|---|---|
| Opening pressure (cmH2O) | 10–20 | >20 (often >30) | Normal or mildly elevated | Elevated (esp. Crypto) | Normal to elevated |
| Appearance | Clear | Turbid/purulent | Clear | Clear or xanthochromic | Clear to bloody/xanthochromic |
| WBC (cells/mm3) | <5 | 1000–10000+ (PMN predominance) | 10–500 (lymphocytic) | 50–500 (lymphocytic) | 10–500 (lymphocytic) |
| Protein (mg/dL) | 15–45 | >100 (often 100–500) | 50–100 | >100 | Mildly elevated |
| Glucose (mg/dL) | 50–80 (>60% serum) | <45 (often <40); low CSF:serum ratio | Normal or mildly low | Low | Normal |
| Gram stain | Negative | Positive 60–80% | Negative | Negative (India ink for Crypto) | Negative |
| Culture | Negative | Positive (gold standard) | Negative | Positive (fungal) | Negative |
| Special tests | — | Blood cultures x2; latex agglutination; PCR (meningococcal/pneumococcal) | Enterovirus PCR; HSV PCR | Cryptococcal antigen; AFB smear/culture; adenosine deaminase (TB) | HSV-1/2 PCR (high sensitivity/specificity) |

**Lumbar puncture contraindications (relative):**
- Mass lesion with midline shift or herniation risk → CT head first
- Thrombocytopenia <50,000 or coagulopathy → correct before LP
- Infection at LP site
- Do NOT delay antibiotics for CT if LP cannot be done immediately

### Empiric Treatment of Bacterial Meningitis

**Always start antibiotics as soon as meningitis is suspected — do not delay for LP or CT if feasible**

| Patient Population | Empiric Regimen |
|---|---|
| Adults 18–50 (immunocompetent) | Dexamethasone + ceftriaxone 2g IV q12h + vancomycin 15–20mg/kg IV q8–12h |
| Adults >50 OR immunocompromised OR alcoholism | Dexamethasone + ceftriaxone 2g IV q12h + vancomycin + **ampicillin 2g IV q4h** (for Listeria) |
| Post-neurosurgery or CSF shunt | Vancomycin + cefepime 2g IV q8h (or meropenem if Pseudomonas risk) |
| Neonates | Ampicillin + cefotaxime (preferred over ceftriaxone in neonates due to bilirubin displacement) |
| Penicillin allergy | Chloramphenicol + TMP-SMX (for Listeria); moxifloxacin for Strep/meningococcus |

**Dexamethasone:** 0.15mg/kg IV q6h x4 days; give 15–20 minutes BEFORE or with first antibiotic dose; most benefit for S. pneumoniae (reduces mortality, hearing loss, neurological sequelae); benefit less established for gram-negative or meningococcal meningitis

### Treatment Duration by Organism

| Organism | Duration |
|---|---|
| N. meningitidis (meningococcus) | 5–7 days |
| H. influenzae | 7 days |
| S. pneumoniae (pneumococcus) | 10–14 days |
| Group B Streptococcus | 14–21 days |
| Listeria monocytogenes | 21 days |
| Gram-negative bacilli (E. coli, Klebsiella) | 21 days |
| TB meningitis | 9–12 months |
| Cryptococcal meningitis | See HIV/AIDS section |

### Meningococcal Prophylaxis

**Indications for chemoprophylaxis (close contacts):**
- Household members and those who slept in same dwelling in past 7 days
- Childcare/preschool contacts
- Direct exposure to patient secretions (kissing, mouth-to-mouth resuscitation, intubation without mask)
- Seated within 3 feet for >8 hours on airplane (index case infectiousness high)

**Regimen (all adults, non-pregnant):**
- Rifampin 600mg PO q12h x2 days (4 doses)
- Ciprofloxacin 500mg PO single dose (preferred in adults; not for children <1 month or pregnant)
- Ceftriaxone 250mg IM single dose (preferred in pregnancy; also safe in all age groups)

**Vaccination:** Meningococcal conjugate vaccine (MenACWY) recommended for close contacts after rifampin or ciprofloxacin; does not replace chemoprophylaxis

### HSV Encephalitis

**Pathogen:** HSV-1 (most common cause of sporadic viral encephalitis in adults); HSV-2 (neonatal, immunocompromised)

**Presentation:** Fever + altered mental status + focal neurological signs (temporal lobe involvement → behavioral changes, aphasia, seizures); headache; prodrome of pharyngitis/fever 1–4 days prior

**Diagnosis:**
- MRI brain (FLAIR/DWI): T2 hyperintensity in temporal lobes, insula — pathognomonic pattern
- CSF HSV PCR: sensitivity 98%, specificity 94%; may be negative in first 72h
- EEG: temporal lobe slowing or periodic lateralized epileptiform discharges (PLEDs)

**Treatment:**
- **Acyclovir 10mg/kg IV q8h x14–21 days** (immunocompetent)
- **Acyclovir 10–15mg/kg IV q8h x21 days** (immunocompromised)
- Renally dosed; ensure adequate hydration to prevent crystalluria/nephropathy
- Do NOT wait for PCR result — empirical treatment should start immediately upon clinical suspicion
- Step-down to valacyclovir 1g TID x90 days post-IV in immunocompromised or severe disease

**Mortality:** 70% without treatment; ~20–30% with treatment; significant neurological sequelae in survivors

---

## 5. Clostridioides difficile Infection (CDI)

### Risk Factors

- Antibiotics (clindamycin, fluoroquinolones, cephalosporins, carbapenems — ANY antibiotic)
- Age >65
- Hospitalization, nursing home residence
- Proton pump inhibitor use
- Inflammatory bowel disease
- Immunosuppression
- Prior CDI

### Diagnosis

- Stool GDH (glutamate dehydrogenase) EIA + toxin A/B EIA (two-step algorithm) OR
- NAAT (PCR) for toxin B gene — high sensitivity; may detect colonization without active disease
- Cell cytotoxicity assay: gold standard for toxin detection (rarely used clinically)
- Do NOT test formed stool
- Colonoscopy (pseudomembranes) if ileus or negative stool test with high suspicion

### CDI Severity and Treatment (IDSA/SHEA 2021 Guidelines)

| Severity | Definition | First Episode Treatment |
|---|---|---|
| Non-severe | WBC <=15,000 AND serum Cr <1.5mg/dL | **Fidaxomicin 200mg PO BID x10 days** (preferred); Vancomycin 125mg PO QID x10 days (alternative) |
| Severe | WBC >15,000 OR serum Cr >=1.5mg/dL | **Fidaxomicin 200mg PO BID x10 days** (preferred); Vancomycin 125mg PO QID x10 days |
| Fulminant | Hypotension/shock OR ileus OR megacolon | **Vancomycin 500mg PO/NG QID + IV metronidazole 500mg q8h**; Vancomycin 500mg PR q6h if ileus; surgical consultation (colectomy if progressive deterioration) |

**Key points:**
- Fidaxomicin preferred over vancomycin for first episode: lower recurrence rate (~12% vs ~25%)
- Metronidazole is no longer recommended as primary therapy (inferior to vancomycin and fidaxomicin)
- Discontinue offending antibiotic as soon as possible
- Contact precautions; hand washing with soap and water (alcohol hand sanitizer does NOT kill C. diff spores)
- Do NOT test for cure — patients may remain PCR-positive for weeks after successful treatment

### Recurrent CDI

**First recurrence:**
- Fidaxomicin 200mg BID x10 days (preferred if vancomycin was used for first episode)
- Vancomycin taper + pulse: 125mg QID x10d → 125mg BID x7d → 125mg daily x7d → 125mg every 2–3 days x2–8 weeks
- Bezlotoxumab 10mg/kg IV single dose + standard antibiotics: monoclonal antibody against toxin B; reduces recurrence in high-risk patients (age >65, severe disease, prior recurrence, immunocompromised)

**Second recurrence:**
- Fidaxomicin 200mg BID x10 days (extended pulsed: 200mg daily every other day x20 days alternative)
- Vancomycin taper and pulse
- **Fecal microbiota transplantation (FMT)** — highly effective (~85–90% cure); colonoscopic, enema, or oral capsule delivery; approved via RBX2660 (Rebyota) or SER-109 (Vowst) FDA-approved products
- Ridinilazole (investigational, promising in trials)

**FMT:** Preferred for multiply recurrent CDI; screen donors for pathogens; FDA-approved microbiome therapeutics available; clinical trial enrollment if available

---

## 6. Infective Endocarditis (IE)

### Duke Criteria for Diagnosis

**Definite IE:** 2 major criteria; 1 major + 3 minor; or 5 minor criteria
**Possible IE:** 1 major + 1 minor; or 3 minor criteria
**Rejected:** Firm alternative diagnosis; resolution in <=4 days of antibiotic therapy; pathology findings not consistent

**Major Criteria:**
1. Positive blood cultures (two separate cultures with typical organism, or persistently positive cultures, or single culture for Coxiella burnetii)
2. Evidence of endocardial involvement: vegetation, abscess, new partial dehiscence of prosthetic valve on echocardiography; new valvular regurgitation

**Minor Criteria:**
1. Predisposing condition (IV drug use, cardiac condition)
2. Fever >38 degrees C
3. Vascular phenomena (arterial emboli, septic pulmonary infarcts, Janeway lesions)
4. Immunologic phenomena (glomerulonephritis, Osler nodes, Roth spots, rheumatoid factor)
5. Microbiological evidence not meeting major criteria

**Echocardiography:**
- Transthoracic echo (TTE): initial; sensitivity 60–80%
- Transesophageal echo (TEE): preferred for prosthetic valve IE, S. aureus bacteremia, indeterminate TTE, suspected perivalvular extension, ICU setting; sensitivity >90%

### Organisms by Source and Risk Factor

| Source / Risk Factor | Likely Organisms |
|---|---|
| Community-acquired (native valve) | Viridans group streptococci (oral flora); Streptococcus bovis/gallolyticus (associated with colon cancer) |
| IV drug use | Staphylococcus aureus (MRSA or MSSA); tricuspid valve most commonly |
| Healthcare-associated (central line, hemodialysis) | S. aureus (MRSA), coagulase-negative staph, Enterococcus, gram-negative bacilli |
| Prosthetic valve — early (<1 year post-surgery) | Coagulase-negative staph, S. aureus, gram-negative bacilli, Candida |
| Prosthetic valve — late (>1 year post-surgery) | Viridans streptococci, coagulase-negative staph, Enterococcus |
| HACEK organisms | Haemophilus, Aggregatibacter, Cardiobacterium, Eikenella, Kingella — culture-negative; slow-growing gram-negatives |
| Dental procedures | Viridans streptococci |
| Culture-negative IE | Coxiella burnetii (Q fever); Bartonella quintana/henselae; Brucella; Tropheryma whipplei |

### Treatment Table

| Organism | Preferred Regimen | Duration | Notes |
|---|---|---|---|
| Viridans streptococci (PCN MIC <=0.12) | Penicillin G 12–18 million units/day IV continuous OR ceftriaxone 2g IV daily | 4 weeks (native valve); 6 weeks (prosthetic) | Shorter 2-week regimen with gentamicin in select uncomplicated cases |
| Streptococcus (PCN MIC >0.12–0.5) | Penicillin G 24 million units/day + gentamicin 3mg/kg/day divided q8h | 4 weeks | Synergy dosing gentamicin |
| MSSA (methicillin-susceptible S. aureus) | Nafcillin or oxacillin 12g/day IV divided q4h | 6 weeks (native valve); >=6 weeks (prosthetic) | Add rifampin + gentamicin for prosthetic valve IE; cefazolin acceptable alternative to nafcillin |
| MRSA (methicillin-resistant S. aureus) | Vancomycin 15–20mg/kg IV q8–12h (target AUC/MIC 400–600) | 6 weeks (native valve); >=6 weeks (prosthetic) | Add rifampin 300mg PO q8h + gentamicin 1mg/kg q8h x2 weeks for prosthetic |
| Enterococcus faecalis | Ampicillin 12g/day IV divided q4h + ceftriaxone 2g IV q12h (preferred synergy doublet) | 6 weeks | Ampicillin + ceftriaxone equally effective as amp + gentamicin with less nephrotoxicity; use amp + gentamicin if not tolerating or cephalosporin resistant |
| Enterococcus (VRE) | Linezolid 600mg IV/PO q12h or daptomycin 10–12mg/kg IV daily | 8 weeks (minimum) | Consult ID; complex management |
| HACEK organisms | Ceftriaxone 2g IV daily | 4 weeks (native); 6 weeks (prosthetic) | Ampicillin-sulbactam if beta-lactamase negative; fluoroquinolone if beta-lactam intolerant |
| Candida IE | Micafungin or liposomal amphotericin B (induction) → fluconazole step-down (if susceptible) | Indefinite suppression with fluconazole (if valve replacement not performed) | Surgery strongly recommended; chronic suppression required |

### Surgical Indications for IE

**Emergent/urgent (within 24 hours):**
- Acute regurgitation with hemodynamic instability/refractory pulmonary edema
- Severe aortic/mitral regurgitation with hemodynamic compromise not responsive to medical therapy
- Obstruction from large vegetation

**Urgent (within 7 days):**
- Persistent bacteremia or fever >5–7 days despite appropriate antibiotic therapy
- Perivalvular abscess, fistula, or destructive penetrating lesion
- Valve perforation or dehiscence
- Large (>10mm) mobile vegetations on anterior mitral leaflet (high embolic risk)
- Fungal IE

**Elective:**
- Prosthetic valve endocarditis (most cases benefit from surgery)
- Staphylococcal prosthetic valve IE
- Recurrent embolism despite antibiotics

### Endocarditis Prophylaxis

**Cardiac conditions with highest risk (prophylaxis indicated for dental procedures with gingival manipulation):**
- Prosthetic cardiac valves (including transcatheter-implanted)
- Prior IE
- Congenital heart disease: unrepaired cyanotic CHD; repaired with prosthetic material (within 6 months); repaired with residual defects adjacent to prosthetic patch/device
- Cardiac transplant recipients with valvulopathy

**Procedure:** Dental procedures involving manipulation of gingival tissue, periapical region of teeth, or perforation of oral mucosa

**Prophylaxis regimen:**
- Amoxicillin 2g PO single dose 30–60 minutes before procedure
- Ampicillin 2g IM/IV if unable to take oral
- Cephalexin 2g PO (beta-lactam allergy, non-IgE-mediated)
- Azithromycin or clarithromycin 500mg PO (penicillin allergy)
- Cefazolin or ceftriaxone 1g IM/IV (penicillin allergy, unable to take oral)

---

## 7. Osteomyelitis and Septic Arthritis

### Osteomyelitis

#### Organisms by Population and Mechanism

| Population / Mechanism | Predominant Organisms |
|---|---|
| Children (hematogenous) | S. aureus (most common); Group A Streptococcus; Kingella kingae (young children); S. pneumoniae |
| Adults (hematogenous) | S. aureus; gram-negative bacilli (in elderly, urinary source, IVDU) |
| IV drug users | S. aureus; Pseudomonas aeruginosa; Candida |
| Sickle cell disease | Salmonella species; S. aureus |
| Diabetic foot / peripheral vascular disease | Polymicrobial (S. aureus, streptococci, anaerobes, gram-negative bacilli); MRSA increasingly common |
| Post-surgical / prosthetic joint | Coagulase-negative staph; S. aureus; gram-negative bacilli |
| Vertebral (spondylodiscitis) | S. aureus; Mycobacterium tuberculosis (Pott's disease); Brucella in endemic areas |
| Contiguous focus (pressure ulcer, diabetic ulcer) | Mixed flora — S. aureus, Enterococcus, Pseudomonas, anaerobes, Enterobacterales |
| Bite wounds (cat/dog) | Pasteurella multocida; Capnocytophaga canimorsus; Fusobacterium; Bacteroides |

#### Diagnosis

**MRI (imaging of choice):**
- T1: decreased signal (marrow edema replaces fat); T2/STIR: increased signal
- Sensitivity 90–100%, specificity 80–95%
- Preferred for vertebral osteomyelitis, diabetic foot, prosthetic joint
- CT: useful when MRI contraindicated; better cortical bone detail
- Nuclear medicine (bone scan Tc-99m): sensitive but less specific; useful for multifocal disease
- PET-CT: excellent for prosthetic device infection

**Biopsy/Culture:**
- Bone biopsy (CT-guided or surgical) is gold standard for causative organism identification
- Blood cultures: positive in ~60% of hematogenous osteomyelitis
- Surface swab cultures from sinus tracts are unreliable and should NOT guide antibiotic choice
- ESR and CRP: elevated; monitor for treatment response (CRP normalizes faster than ESR)

#### Treatment

**Surgical principles:**
- Adequate debridement of necrotic bone (sequestrectomy)
- Source control: drainage of abscess, removal of infected hardware if necessary
- Coverage with vascularized tissue for diabetic foot/chronic osteomyelitis

**Duration:** Standard course is **6 weeks** of antibiotics (total; parenteral + oral step-down)

| Organism | IV Regimen | Oral Step-Down | Notes |
|---|---|---|---|
| MSSA | Nafcillin 2g IV q4h OR cefazolin 2g IV q8h | Dicloxacillin 500mg QID or cephalexin 1g QID | Oral step-down after 1–2 weeks IV if clinical improvement |
| MRSA | Vancomycin 15–20mg/kg IV q8–12h (target AUC/MIC 400–600) | TMP-SMX DS 1–2 tabs BID + rifampin 300–450mg BID; or doxycycline 100mg BID | Rifampin added for biofilm-forming organisms on hardware |
| Gram-negative bacilli | Cefepime 2g IV q12h or ertapenem 1g IV daily (Pseudomonas: cefepime/piperacillin-tazobactam) | Ciprofloxacin 750mg PO BID (if susceptible) | Fluoroquinolone oral bioavailability nearly equivalent to IV |
| Anaerobes | Ampicillin-sulbactam 3g IV q6h or ertapenem | Amoxicillin-clavulanate 875mg BID or metronidazole 500mg BID | Diabetic foot commonly polymicrobial |
| Streptococcus | Penicillin G 3–4 million units IV q4h or ceftriaxone 2g IV daily | Amoxicillin 1g TID | |

**IDSA OVIVA trial:** Oral antibiotics non-inferior to IV for chronic/sub-acute osteomyelitis when appropriate oral agent available — supports early oral step-down after initial IV debulking

### Septic Arthritis

#### Diagnosis

**Synovial Fluid Analysis:**

| Parameter | Normal | Septic Arthritis | Crystal Arthritis (Gout/CPPD) | Inflammatory (RA, etc.) |
|---|---|---|---|---|
| Appearance | Clear, yellow | Opaque, purulent | Cloudy to opaque | Cloudy |
| WBC (cells/mm3) | <200 | **>50,000** (often >100,000) | 2000–50,000 | 2000–50,000 |
| % PMN | <25% | **>75%** (often >90%) | >50% | >50% |
| Glucose | Equal to serum | Decreased | Normal | Normal/decreased |
| Culture | Negative | Positive 70–80% | Negative | Negative |

**Key diagnostic threshold:** Joint fluid WBC >50,000 cells/mm3 with PMN predominance is highly suspicious for septic arthritis; values >100,000 almost diagnostic. However, crystal arthritis can overlap — Gram stain and culture are essential.

**Note:** Septic arthritis and crystal arthritis (gout, pseudogout) can coexist — do NOT assume positive crystals rules out infection.

**Blood cultures:** Positive in 50–70% of hematogenous septic arthritis — always obtain before antibiotics

**Organisms by population:**

| Population | Predominant Organisms |
|---|---|
| Sexually active adults (most common in adults <40) | Neisseria gonorrhoeae |
| Adults >40 | S. aureus (most common overall); streptococci |
| Children <2 years | S. aureus; Kingella kingae |
| Children 2–15 years | S. aureus; Group A Streptococcus |
| Elderly, debilitated, rheumatoid arthritis | S. aureus; gram-negative bacilli |
| IV drug users | S. aureus; Pseudomonas aeruginosa; gram-negative enteric |
| Immunocompromised | Fungal (Candida, dimorphic fungi); atypical mycobacteria |

#### Treatment

**Surgical drainage (joint washout):**
- **Arthroscopic or open surgical drainage and irrigation is standard of care** for most native joint septic arthritis
- Serial needle aspiration (daily) acceptable for knee joint in appropriate patients; generally inferior to surgical drainage for hip, shoulder, sternoclavicular
- Prosthetic joint infection: retain or remove prosthesis based on chronicity and organism virulence

**Antibiotic duration:**
- Native joint: **2–4 weeks** (gonococcal: 7 days; gram-negative bacilli: 3–4 weeks; S. aureus: 3–4 weeks)
- Prosthetic joint: **6 weeks** (see endocarditis section for organism-specific guidance)

**Gonococcal arthritis:** Ceftriaxone 1g IV daily x7 days (step down to cefixime 400mg PO BID or ciprofloxacin 500mg BID after 24–48h improvement if susceptible); treat chlamydia coinfection

---

## 8. Lyme Disease

### Pathogen and Epidemiology

- **Borrelia burgdorferi** (North America); B. afzelii, B. garinii (Europe)
- Transmitted by Ixodes scapularis (black-legged/deer tick) — nymph stage most infectious (May–September)
- Tick attachment >36 hours required for transmission
- Endemic regions: northeastern and north-central United States; upper Midwest

### Clinical Stages

**Stage 1 — Early Localized (3–30 days post-bite):**
- Erythema migrans (EM): expanding erythematous rash >5cm, often with central clearing (bull's-eye pattern in 20%); may be uniformly red; single lesion at bite site
- Systemic: fever, myalgia, headache, malaise, lymphadenopathy
- EM is pathognomonic — no serology required for diagnosis in endemic area with classic rash

**Stage 2 — Early Disseminated (days to weeks):**
- Multiple secondary EM lesions (hematogenous spread)
- **Carditis:** atrioventricular block (first-degree to complete heart block); usually reversible; syncope, palpitations
- **Neurological (Lyme neuroborreliosis):** facial nerve palsy (bilateral); meningitis; radiculopathy; encephalopathy
- Migratory arthralgia, myalgia

**Stage 3 — Late Disseminated (months to years):**
- **Lyme arthritis:** Intermittent then persistent monoarthritis or oligoarthritis; knee most common; joint fluid WBC 10,000–50,000
- **Neurological (late):** Encephalopathy, peripheral neuropathy (rare)
- Acrodermatitis chronica atrophicans (Europe, B. afzelii)

### Two-Tier Serology

**Step 1:** ELISA (IgM + IgG combined; or IgG-only if >30 days of symptoms)
**Step 2 (if ELISA positive or equivocal):** Western blot (IgM: 2 of 3 bands; IgG: 5 of 10 bands)

**Modified two-tier testing (MTTT):** Two sequential ELISAs (more sensitive than IgM Western blot for early disease)

**Seronegative early Lyme:** Possible in first 1–2 weeks (antibodies not yet formed); treat clinically if EM present; repeat serology in 4–6 weeks if negative

**Important:** Serology may remain positive for years after successful treatment — do NOT use serology to assess treatment response or diagnose retreatment need

### Lyme Disease Treatment by Stage

| Stage / Manifestation | First-Line Treatment | Alternative | Duration |
|---|---|---|---|
| Erythema migrans (early localized) | Doxycycline 100mg PO BID | Amoxicillin 500mg TID; cefuroxime 500mg BID | 10 days (doxy); 14 days (alternatives) |
| Early disseminated — multiple EM, mild carditis (PR <300ms) | Doxycycline 100mg PO BID | Amoxicillin 500mg TID; cefuroxime 500mg BID | 14–21 days |
| Facial nerve palsy (without meningitis) | Doxycycline 100mg PO BID | Amoxicillin 500mg TID; cefuroxime 500mg BID | 14–21 days |
| Carditis — high-degree AV block, hospitalized | Ceftriaxone 2g IV daily (until stable) → step down to doxycycline | Penicillin G 18–24 million units/day IV | Total 14–21 days; pacemaker if needed (temporary) |
| Lyme meningitis / radiculopathy | Ceftriaxone 2g IV daily | Penicillin G 18–24 million units/day IV; doxycycline 200mg BID PO (select cases) | 14 days |
| Lyme arthritis (without neurological disease) | Doxycycline 100mg PO BID | Amoxicillin 500mg TID | 28 days oral |
| Lyme arthritis — refractory after 2 oral courses | Ceftriaxone 2g IV daily | Penicillin G 18–24 million units/day IV | 14–28 days IV |
| Late neurological Lyme | Ceftriaxone 2g IV daily | Penicillin G IV | 14–28 days |

**Prophylaxis (single tick bite):**
- Single dose doxycycline 200mg PO within 72 hours of tick removal
- Indications: I. scapularis tick, >36 hours attached, endemic area, not pregnant
- Reduces risk by ~87% (NEJM study)

**Post-treatment Lyme Disease Syndrome (PTLDS):**
- Persistent symptoms (fatigue, cognitive difficulties, musculoskeletal pain) >6 months post-treatment
- Does NOT respond to additional antibiotics (RCTs show no benefit)
- Pathophysiology unclear; supportive management
- Distinguish from reinfection (new exposure, new EM)

---

## 9. Influenza

### Virology and Epidemiology

- Influenza A (H1N1, H3N2) and Influenza B (Yamagata and Victoria lineages)
- Annual antigenic drift → seasonal epidemics; antigenic shift → pandemic potential (Influenza A)
- Seasonal peak: December–February in Northern Hemisphere
- Transmission: respiratory droplets + contact; infectious 1 day before symptoms to 5–7 days after

### High-Risk Groups for Severe Influenza

- Age >=65 or <2 years
- Pregnancy and up to 2 weeks postpartum
- BMI >=40
- Chronic pulmonary disease (asthma, COPD)
- Cardiovascular disease (except isolated hypertension)
- Chronic renal, hepatic, hematologic, or metabolic disorders (including diabetes mellitus)
- Immunosuppression (HIV, malignancy, transplant, steroids)
- Residents of nursing homes or long-term care facilities
- American Indian/Alaska Native populations

### Treatment

**Antiviral treatment (most effective when started within 48 hours of symptom onset; still benefit in high-risk groups or hospitalized patients regardless of timing):**

| Drug | Route | Dose | Duration | Notes |
|---|---|---|---|---|
| Oseltamivir (Tamiflu) | PO | 75mg BID | 5 days | Standard adult dose; renally dosed (CrCl 10–30: 30mg BID); preferred in most situations |
| Zanamivir (Relenza) | Inhaled | 10mg (2 inhalations) BID | 5 days | Bronchospasm risk — avoid in asthma/COPD; no renal adjustment; alternative if oseltamivir not tolerated |
| Baloxavir marboxil (Xofluza) | PO | 40mg (<80kg) or 80mg (>=80kg) | Single dose | Endonuclease inhibitor; single dose convenient; NOT for pregnancy, nursing, <1 year; resistance emerging |
| IV Peramivir | IV | 600mg single dose | 1 dose | Option for hospitalized unable to take oral/inhaled; not superior to oseltamivir |

**Hospitalized patients:** Oseltamivir 75mg BID x5 days (can extend to 10 days for severe cases or immunocompromised); IV peramivir if unable to take oral

**High-dose oseltamivir:** 150mg BID x10 days for severely immunocompromised patients — some expert opinion, limited evidence

### Influenza Prophylaxis

**Post-exposure chemoprophylaxis:**
- Oseltamivir 75mg PO once daily x10 days (within 48 hours of exposure)
- Zanamivir 10mg inhaled once daily x10 days
- Baloxavir single dose (within 48h, post-exposure prophylaxis trial data emerging)

**Pre-exposure (seasonal) prophylaxis:**
- Oseltamivir 75mg PO once daily for duration of influenza season — for high-risk patients who cannot receive vaccine or vaccinated <2 weeks prior during active outbreak

**Annual vaccination (primary prevention):**
- Recommended for ALL persons >=6 months of age
- High-dose influenza vaccine (Fluzone HD) preferred for age >=65 (4x antigen; improved immunogenicity)
- Recombinant influenza vaccine (Flublok) for egg allergy
- Quadrivalent formulations (4-valent): protect against two Influenza A and two Influenza B strains
- Timing: ideally before end of October; still beneficial later in season

### Complications of Influenza

- Primary viral pneumonia (especially H1N1, H3N2, Influenza B)
- Secondary bacterial pneumonia (S. aureus including MRSA, S. pneumoniae, Group A Strep — often follows viral period)
- Exacerbation of underlying cardiopulmonary disease
- Myositis, myocarditis, pericarditis
- Neurological: encephalopathy, Reye syndrome (aspirin + Influenza B in children)
- ARDS, multi-organ failure in severe cases

---

## 10. Antimicrobial Stewardship

### Core Principles

Antimicrobial stewardship programs (ASP) aim to optimize antibiotic selection, dose, route, and duration to improve patient outcomes, reduce adverse effects, minimize resistance selection, and reduce costs.

**The 4 Ds of stewardship:** Right Drug, right Dose, right De-escalation, right Duration

### Recommended Antibiotic Duration by Infection

| Infection | Duration | Evidence / Notes |
|---|---|---|
| Community-acquired pneumonia (non-severe, outpatient) | 5 days (if clinical response achieved) | IDSA 2019; minimum 5 days if afebrile and clinically improved |
| Community-acquired pneumonia (severe, ICU) | 5–7 days (re-evaluate daily) | Extend for Pseudomonas, Staph aureus, or cavitary disease |
| Hospital-acquired / ventilator-associated pneumonia | 7 days | Most organisms; 8 days total if Pseudomonas (some experts) |
| Uncomplicated urinary tract infection (UTI), women | Nitrofurantoin 5 days or TMP-SMX 3 days or fosfomycin 3g x1 dose | Avoid fluoroquinolones for uncomplicated UTI |
| Complicated UTI / pyelonephritis | 7 days (fluoroquinolone or TMP-SMX); 10–14 days (beta-lactam) | Based on fluoroquinolone susceptibility |
| Catheter-associated UTI | 7 days (remove catheter if possible) | 14 days if slow response |
| Skin and soft tissue (non-purulent cellulitis) | 5 days (extend if slow response) | |
| Skin and soft tissue (purulent, drained abscess) | 5–7 days post-drainage (MSSA); 7–14 days (MRSA) | Incision and drainage is primary treatment; antibiotics adjunctive |
| Intra-abdominal infection (adequate source control) | 4 days | IDSA/SIS guidelines; stopping at day 4 non-inferior to longer |
| Sepsis (adequate source control, clinical improvement) | 7 days | Procalcitonin-guided discontinuation reduces exposure |
| Bacteremia (uncomplicated, gram-positive cocci) | 14 days (S. aureus: minimum 14 days; longer if IE, osteomyelitis concern) | Echocardiogram for S. aureus bacteremia |
| Bacteremia (gram-negative, source controlled) | 7–14 days | |
| Osteomyelitis | 6 weeks | See section 7 |
| Endocarditis | 4–6 weeks | See section 6 |
| C. difficile | 10 days | See section 5 |
| SSTI (necrotizing fasciitis) | Until debridement complete + 48–72h afebrile | Surgical emergency — antibiotics secondary to surgery |

### Oral Step-Down Therapy

Intravenous to oral conversion should occur when the patient is:
1. Hemodynamically stable (no vasopressors, no septic shock)
2. Tolerating oral medications
3. Normal GI absorption (no ileus, malabsorption)
4. Appropriate oral option available with adequate bioavailability

| IV Agent | Oral Equivalent | Bioavailability | Notes |
|---|---|---|---|
| Ciprofloxacin 400mg IV | Ciprofloxacin 500–750mg PO | ~70–80% | Excellent oral bioavailability; IV to PO switch preferred |
| Levofloxacin 500mg IV | Levofloxacin 500mg PO | ~99% | Near-complete bioavailability; no dose change needed |
| Moxifloxacin 400mg IV | Moxifloxacin 400mg PO | ~91% | Same dose |
| Metronidazole 500mg IV | Metronidazole 500mg PO | ~90–100% | Same dose; oral preferred when GI function intact |
| Fluconazole 400mg IV | Fluconazole 400mg PO | ~90% | Same dose; oral equivalent |
| Linezolid 600mg IV | Linezolid 600mg PO | ~100% | Same dose; IV reserved for inability to take oral |
| TMP-SMX IV | TMP-SMX DS PO | ~90–100% | Same dose (by TMP component) |
| Ampicillin-sulbactam IV | Amoxicillin-clavulanate PO | ~75–90% | Amoxicillin-clavulanate covers similar spectrum |
| Ceftriaxone 2g IV | Cefdinir / cefpodoxime / cefixime PO | Variable | Cephalosporins: oral generics have narrower spectrum; consider resistance |
| Vancomycin IV | Linezolid PO; TMP-SMX (MRSA SSTIs) | 100% (linezolid) | No oral vancomycin for systemic infections (oral VAN not absorbed — only used for C. diff) |
| Daptomycin IV | Linezolid PO | — | Daptomycin has no oral form |

### Beta-Lactam Allergy Assessment

**True penicillin allergy prevalence:** ~1–10% of patients report allergy; <1% have true IgE-mediated reactions

**Allergy classification:**

| Category | Description | Cross-Reactivity Risk with Other Beta-Lactams | Management |
|---|---|---|---|
| IgE-mediated (immediate) | Urticaria, angioedema, bronchospasm, anaphylaxis within 1h | Low (<2%) with cephalosporins if different side chains; higher same-side-chain | Skin testing; penicillin challenge; allergy consultation |
| Non-IgE-mediated (accelerated) | Urticaria/rash 1–72h after dose | Low | Can often use cephalosporins cautiously |
| Delayed maculopapular rash (>72h) | Common; often amoxicillin + viral infection | Very low | Can usually use other penicillins and cephalosporins safely |
| Severe delayed (SJS/TEN/DRESS/AGEP) | Desquamating/blistering reaction; drug hypersensitivity syndrome | Avoid all beta-lactams (absolute contraindication) | Permanent avoidance; consult allergy |
| Serum sickness-like | Urticaria + arthralgia; 7–21 days into therapy | Low | Avoid same drug; other beta-lactams usually okay |

**Penicillin-cephalosporin cross-reactivity:**
- Historical estimate of 10% was inflated; true cross-reactivity <2%
- Based on R1 side chain similarity, not the beta-lactam ring
- Aminopenicillins (ampicillin, amoxicillin) share R1 chains with cefadroxil, cefprozil, cefatrizine
- Patients with non-severe, non-immediate penicillin allergy can generally use cephalosporins safely

**Penicillin skin testing:**
- PPL (Pre-Pen, major determinant) + minor determinants + penicillin G
- Negative skin test: low risk (~1–3% chance of any reaction; <0.001% anaphylaxis)
- Available at allergy clinics; direct oral challenge increasingly used in low-risk patients

**Carbapenem cross-reactivity with penicillin:**
- Very low (approximately 1%); structural differences from penicillin
- Carbapenems can generally be used in penicillin-allergic patients without documented severe immediate reactions

### Antibiotic Resistance Mechanisms

| Mechanism | Example Organisms | Antibiotics Affected |
|---|---|---|
| Beta-lactamase production | Staphylococci, H. influenzae, many gram-negatives | Penicillins (overcome by beta-lactamase inhibitors) |
| Extended-spectrum beta-lactamase (ESBL) | Klebsiella, E. coli | Most cephalosporins, penicillins; carbapenems retain activity |
| Carbapenemase (KPC, NDM, OXA-48) | Klebsiella pneumoniae carbapenemase (KPC); NDM (New Delhi metallo-beta-lactamase) | Carbapenems; options: ceftazidime-avibactam, meropenem-vaborbactam, imipenem-cilastatin-relebactam |
| AmpC beta-lactamase | Enterobacter, Citrobacter, Serratia, Pseudomonas | Cephalosporins (inducible; use carbapenems for serious infections) |
| mecA/mecC (PBP2a) | MRSA, coagulase-negative staph | All beta-lactams; treat with vancomycin, daptomycin, linezolid, ceftaroline |
| vanA/vanB | Vancomycin-resistant Enterococcus (VRE) | Glycopeptides; treat with linezolid, daptomycin, tigecycline |
| Efflux pumps | Pseudomonas, Acinetobacter | Multiple classes including carbapenems |
| Porin loss | Pseudomonas, Acinetobacter | Carbapenems (reduced uptake) |
| Target modification (23S rRNA) | Macrolide-resistant Streptococcus | Macrolides; use beta-lactams |

### Procalcitonin-Guided Antibiotic Therapy

- Procalcitonin (PCT) rises rapidly in bacterial infections; low in viral infections, autoimmune, and non-infectious inflammation
- Guides antibiotic initiation and discontinuation:
  - PCT <0.25 ng/mL: antibiotic initiation discouraged (likely non-bacterial)
  - PCT <0.5 ng/mL or decrease >80% from peak: antibiotic discontinuation supported
- Validated in: community-acquired pneumonia, lower respiratory tract infections, sepsis
- Reduces antibiotic exposure by ~2 days without adverse outcomes in RCTs
- Limitations: not useful for HAP/VAP, post-surgical state, severe immunosuppression (blunted response), fungal infections

### Key Stewardship Interventions

**Prospective audit and feedback:** Pharmacist or ID physician review of broad-spectrum antibiotics on day 2–3 with recommendations; most impactful intervention

**Formulary restriction and pre-authorization:** Require approval for carbapenems, glycopeptides, antifungals — reduces use and costs

**Rapid diagnostics:** Blood culture ID panels (BioFire FilmArray), Xpert resistance testing, T2 Candida — enables rapid de-escalation

**De-escalation:** Narrow spectrum once susceptibilities known; shift from empiric to definitive therapy within 48–72 hours

**Duration bundling:** Automatic stop dates or reassessment triggers built into electronic prescribing

**Antibiotic time-out:** Routine reassessment at 48–72 hours of any antibiotic course — does patient still need antibiotics? Is the spectrum appropriate? What is the planned duration?

---

## Quick Reference Tables

### Empiric Antibiotic Selection by Common Syndrome

| Syndrome | Likely Organisms | Empiric Regimen |
|---|---|---|
| Community-acquired pneumonia (outpatient, mild) | S. pneumoniae, Mycoplasma, Chlamydophila, Haemophilus | Amoxicillin 1g TID or doxycycline 100mg BID (low-risk); azithromycin/clarithromycin (if true CAP without co-morbidities) |
| CAP (inpatient, non-ICU) | As above + S. aureus | Beta-lactam (ampicillin-sulbactam or ceftriaxone) + macrolide (azithromycin) or respiratory fluoroquinolone monotherapy |
| CAP (ICU, severe) | As above + Legionella, Pseudomonas (risk factors) | Ceftriaxone + azithromycin; add antipseudomonal beta-lactam if structural lung disease, recent antibiotics, or hospitalization |
| Sepsis (unknown source) | Gram-negative enteric, S. aureus, Enterococcus | Vancomycin + piperacillin-tazobactam (common regimen); adjust based on source |
| Septic shock (immunocompromised) | All above + Pseudomonas, Candida, resistant gram-negatives | Vancomycin + antipseudomonal carbapenem + consider micafungin |
| Uncomplicated cellulitis | Group A, B, C, G Streptococcus | Cephalexin 500mg QID or dicloxacillin 500mg QID x5 days |
| Purulent SSTI (abscess) | MSSA/MRSA | Incision and drainage primary; TMP-SMX DS 1–2 tabs BID or doxycycline 100mg BID x5–7 days (MRSA coverage) |
| Necrotizing fasciitis | Polymicrobial or Group A Strep | Piperacillin-tazobactam + vancomycin + clindamycin (anti-toxin) PLUS URGENT SURGERY |
| Urinary tract infection (uncomplicated) | E. coli, Klebsiella, Staph saprophyticus | Nitrofurantoin macrocrystal 100mg BID x5d; TMP-SMX DS BID x3d; fosfomycin 3g x1 |
| Pyelonephritis (outpatient) | E. coli, Klebsiella | Ciprofloxacin 500mg BID x7d (if <10% local resistance); TMP-SMX BID x14d |
| Spontaneous bacterial peritonitis (SBP) | E. coli, Klebsiella, S. pneumoniae | Cefotaxime 2g IV q8h x5 days; albumin 1.5g/kg at diagnosis + 1g/kg on day 3 (reduces renal impairment and mortality) |
| Neutropenic fever | Gram-negative (Pseudomonas, Enterobacterales), S. aureus, Streptococcus, Candida | Cefepime 2g IV q8h (antipseudomonal monotherapy); add vancomycin if hemodynamically unstable or suspected catheter or skin infection |

### Common Drug Interactions in Infectious Disease

| Antibiotic | Interacting Drug | Effect | Management |
|---|---|---|---|
| Rifampin | Warfarin | Reduced warfarin levels (CYP induction) → subtherapeutic anticoagulation | Increase warfarin dose; monitor INR closely |
| Rifampin | Oral contraceptives | Reduced OCP levels → contraceptive failure | Alternative contraception during + 1 month after rifampin |
| Rifampin | Most HIV PIs and NNRTIs | Reduced antiretroviral levels | Substitute rifabutin; or use efavirenz/dolutegravir |
| Fluoroquinolones | Divalent cations (antacids, Ca, Mg, Fe, Zn) | Chelation → reduced fluoroquinolone absorption | Separate administration by 2–4 hours |
| Metronidazole | Alcohol | Disulfiram-like reaction (flushing, nausea, tachycardia) | Avoid alcohol during + 48h after completion |
| TMP-SMX | Warfarin | Increased warfarin effect (CYP2C9 inhibition + displacement from protein binding) | Monitor INR; may need dose reduction |
| TMP-SMX | ACE inhibitors / ARBs / K-sparing diuretics | Hyperkalemia (TMP inhibits tubular K+ secretion) | Monitor potassium; avoid combination in CKD |
| TMP-SMX | Methotrexate | Increased methotrexate toxicity; additive folate antagonism | Avoid; use alternative prophylaxis |
| Azithromycin | QTc-prolonging agents | Additive QTc prolongation | ECG monitoring; avoid combination with antipsychotics, antiarrhythmics |
| Daptomycin | Statins | Myopathy risk | Hold statins during daptomycin therapy |
| Linezolid | SSRIs/SNRIs/MAOIs | Serotonin syndrome risk | Avoid combination; if unavoidable, monitor closely; discontinue serotonergic agents |
| Voriconazole | Rifampin/rifabutin | Profoundly decreased voriconazole levels | Contraindicated with rifampin; rifabutin requires dose adjustment |

---

*Last updated: 2026. Based on DHHS, IDSA, CDC, and WHO guidelines current as of knowledge cutoff. Always verify against the most current institutional and national guidelines for clinical decision-making.*
