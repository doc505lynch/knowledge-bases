# Session Handoff — 2026-04-03

## What We Did This Session

### 1. AI Stack Status Checks (zia-streaming: 76.13.103.117)

#### SDXL Model Downloads — COMPLETE
- `sd_xl_base_1.0.safetensors` (6.5 GB) — downloaded 3/31
- `sd_xl_refiner_1.0.safetensors` (5.7 GB) — downloaded 3/31
- `sdxl_vae.safetensors` (320 MB) — downloaded 3/31
- ComfyUI is NOT running — needs to be started

#### vLLM — SKIPPED (not viable)
- No GPU on server, only 6GB RAM free
- Ollama already running on 11434 with 25 models + OpenAI-compatible API at /v1/
- Recommendation: only deploy vLLM if GPU is added

#### Portal Auth — DEPLOYED
- nginx basic_auth on ziaventuregroup.cloud
- Credentials: doc505lynch@gmail.com / Ally505?
- Dashboard with 6 service tiles
- Open WebUI at /webui/ bypasses basic_auth (has own login)
- Subdomains (comfyui, n8n) unaffected

#### CivitAI Models — BLOCKED on API key
- Download script at `/opt/ComfyUI/download_models.sh` on server
- 5 models identified: Pony Diffusion V6 XL, Juggernaut XL Ragnarok, CyberRealistic XL v9.0, Big Lust v1.6, NSFW XL LoRA v2.1
- ~27 GB total, 124 GB free
- Need CivitAI API key from https://civitai.com/user/account
- Run: `CIVITAI_TOKEN=<key> nohup bash /opt/ComfyUI/download_models.sh > /opt/ComfyUI/download.log 2>&1 &`

### 2. Compliance Dashboard Backend Gaps — COMPLETE (zia-backend: 72.60.225.132)

#### New Database Tables
- `dmca_requests` — DMCA/takedown tracking
- `content_reviews` — content moderation queue
- Migration: `api/migrations/007_compliance_system.sql`

#### New Route Files
- `api/routes/compliance-dmca.js` — 5 endpoints at /api/v1/compliance/dmca
- `api/routes/compliance-verification.js` — 3 endpoints at /api/v1/compliance/verification-reports
- Updated `api/routes/content.js` — replaced stub with 6 working endpoints
- Updated `api/routes/compliance.js` — added GET /recordings listing
- All 16 endpoints tested and passing

### 3. React Frontend — DEPLOYED (zia-backend: 72.60.225.132)

Live at: http://72.60.225.132:3000/

- React 18 + Vite 5 + Tailwind 3 + React Router 6 + HLS.js
- 11 pages: Landing, Login, Register, Browse, Creator Profile, Live Stream, Subscriber Dashboard, Settings, Creator Dashboard, Creator Settings, Admin Dashboard
- Dark theme with pink (#e91e63) and gold (#ffd700) accents
- JWT auth matching backend middleware
- HLS player pointing at Owncast on zia-streaming
- Legacy routes preserved (/compliance/, old /admin/)
- server.js patched (backup at server.js.bak), zia-api service restarted

### 4. n8n Workflows — DEPLOYED (zia-backend: 72.60.225.132)

5 workflows imported to n8n at https://n8n.srv1163010.hstgr.cloud/ (all INACTIVE — need activation):

1. **Zia: Creator Onboarding** — polls pending apps every 5min, Ollama compliance checklist
2. **Zia: AI Content Moderation** — webhook trigger, Ollama policy analysis, auto-flag
3. **Zia: AI Auto-Tagging** — webhook trigger, Ollama tag generation, auto-apply if confidence >= 0.6
4. **Zia: Email Notifications** — live stream alerts, new subscriber, weekly earnings, daily stats
5. **Zia: Daily Compliance Monitoring** — 6am daily, expiring verifications, DMCA backlog, AI summary

Helper module: `api/utils/n8n.js` (needs to be require'd in route files)
Workflow JSONs: `C:\Users\Owner - PC\.local\bin\zia-n8n-workflows\`

**Manual setup needed:**
- SMTP credentials in n8n UI
- Activate all 5 workflows
- Wire n8n.js into Express routes
- Change timezone to America/Denver in `/docker/n8n/.env`

### 5. Tax Advisor Workspace — DEPLOYED (Open WebUI)

#### Knowledge Base (12 files, 172K total)
| File | Size | Topics |
|------|------|--------|
| tax-brackets-rates.md | 7.0K | Federal brackets, cap gains, AMT, NIIT |
| standard-deductions-exemptions.md | 6.0K | Standard/itemized deductions, SALT cap |
| tax-credits.md | 10K | CTC, EITC, education, energy, EV credits |
| retirement-accounts.md | 8.7K | 401k, IRA, Roth, SEP, SIMPLE, RMDs, SECURE 2.0 |
| self-employment-business.md | 10K | SE tax, QBI, Schedule C, Section 179, bonus depreciation |
| hsa-fsa-medical.md | 7.7K | HSA/FSA limits, HDHP, medical deduction |
| education-tax-benefits.md | 27K | AOTC, LLC, 529, student loans, Coverdell |
| estate-gift-tax.md | 6.6K | Estate/gift exemptions, TCJA sunset |
| filing-procedures.md | 9.5K | Deadlines, penalties, extensions, audit |
| new-mexico-state-tax.md | 14K | NM brackets, GRT, credits, property tax |
| key-changes-by-year.md | 8.2K | 2023→2024→2025 changes, TCJA sunset preview |
| tax-preparation-checklist.md | 32K | Document checklist, filing status, strategies |

#### Workspace Configuration
- **Model:** phi4-mini:latest (2.5 GB, 3.8B params — smallest viable for tax reasoning)
- **Temperature:** 0.3 (low for factual accuracy)
- **Context:** 8192 tokens
- **Knowledge Base ID:** 9651502a-ecdd-47ac-a807-c263b6555c6a
- **Workspace Model ID:** tax-advisor
- **6 suggestion prompts** pre-configured
- **System prompt** with 10 rules for accurate tax advice

Local files: `C:\Users\Owner - PC\.local\bin\tax-knowledge-base\`
Deploy script: `C:\Users\Owner - PC\.local\bin\create-tax-workspace.sh`

### 6. OSINT — jeica11 Username Lookup

**Probable identity:** Jessica Alejandra Gonzalez, Zaragoza, Spain
- Aliases: Jessica Canales (Snapchat), Jessica Ramos (Cash App)
- Emails: jeica11@gmail.com, jeica11@hotmail.com, jeica11@outlook.com, jeica11@proton.me
- 15+ platforms found (Instagram, TikTok, Snapchat, Pinterest, Telegram, YouTube, Freelancer, Roblox, Xbox, XVideos, Cash App, Duolingo, MyFitnessPal, Picsart)
- Facebook linked via Picsart photo (FB ID: 10153524175011101)
- Cash App alternate handle: $jessram0s
- YouTube channel from 2011 (oldest footprint)
- Credits used: 3 (balance: 75)

---

## OSINT Credit Balance
**75 credits** (~25 standard lookups before floor of 12)

---

## Repo Status

| Repo | Branch | Last Commit | Clean? |
|------|--------|-------------|--------|
| blue-team-agent | main | 3a317ad | clean |
| red-team-agent | main | 27d4bdd | clean |
| adultbusiness | master | 20f24b4 | unknown (frontend changes on server, not committed) |
| ai-stack | main | 2a83e0a | clean |

---

## Still Pending

1. **CivitAI API key** — need token to download 5 adult models for ComfyUI
2. **Start ComfyUI** on zia-streaming
3. **n8n manual setup** — SMTP creds, activate workflows, wire helpers, fix timezone
4. **Commit React frontend** to adultbusiness repo
5. **DNS/CDN** — disable CDN on ziaventuregroup.com, .shop, easthamindustrial.com, jaxxxjewels.cloud (hpanel manual)
6. **.org → .com redirect** — htaccess ready, not deployed
7. **claude-code server decommission** (83.136.219.237)
8. **Legal** — NM LLC, EIN, business bank account

---

## Infrastructure

| Server | IP | Role |
|--------|-----|------|
| zia-streaming | 76.13.103.117 | AI stack + Open WebUI + ComfyUI + Ollama (25 models) |
| zia-backend | 72.60.225.132 | Production API + React frontend + n8n |
| claude-code | 83.136.219.237 | Old dev — decommission candidate |

SSH key: ~/.ssh/id_servers (passphrase-free)
