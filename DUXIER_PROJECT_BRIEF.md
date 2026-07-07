# Duxier Tax Recruitment — Project Brief & Build Handoff

**Status:** Pre-launch. Brochureware site built and committed locally, not yet pushed to GitHub. No backend exists yet. This doc is the single source of truth to hand to Claude Code to pick up the build.

---

## 1. The Concept

UK tax recruitment agencies charge 20–30% of first-year salary per hire (often £15,000+ per appointment) for a service that increasingly reduces to "access to a database of candidates." Duxier removes the agency fee by letting:

- **Firms** search a pool of anonymised tax-professional profiles directly, with no placement percentage.
- **Tax professionals** — including current HMRC staff and in-house teams — list themselves in confidence. Their identity stays hidden until *they* approve a reveal request from a specific firm.

**The sharpest wedge:** HMRC and in-house tax staff who are open to a move but cannot risk appearing on LinkedIn, being seen job-hunting, or tipping off their current employer/department. Duxier gives them a way to be found without being seen to look.

**What this is not:** a re-skinned job board. Anonymisation is the product, not a feature bullet. Employer names, exact dates, and location are generalised specifically so a profile can't be reverse-identified by anyone who knows the sector.

---

## 2. Competitive Landscape (researched — see summary, don't re-research from scratch)

UK tax recruitment: ~£4bn market, ~45,000 specialist professionals, ~7,000 employing businesses, growing ~16%/year.

**Tier 1 (established leaders):** Brewer Morris (est. 1987, part of The SR Group, 850+ clients/year, 1,000+ placements in 2024), Hays Tax (2,500 clients/year, generalist scale), Pro-Tax/Pro Recruitment (largest dedicated UK tax team, ~20 years).

**Tier 2 (specialist mid-market — the real competitive set):** Ambition, Pure Search, FD Capital (founded 2018, CIOT-qualified focus, 10-day shortlists), Harvey John, SRM, Nielsen Grey, Longman Tax Recruitment (North of England), Howells Consulting (personal tax/trusts boutique), Unity Executive Tax, Cowen Partners.

**Tier 3 (generalist finance firms with a tax bolt-on):** Consultancy Group, Oakridge, TPF, KBM — weaker tax credibility, easiest to out-position.

**What every serious player claims:** recruiters who were tax practitioners themselves; CTA/CIOT/ACA-qualified candidate networks; access to passive talent; fast shortlists. Nobody differentiates on process transparency, technology, or a self-serve confidential search mechanic — it's a relationship-sold, trust-led market that still leads with "we understand tax" as the whole pitch.

**Gaps found:** no regional-neutral modern-process play; thin coverage of R&D tax, tax technology roles, and SME/scale-up in-house hires (most Tier 1/2 focus FTSE and Big 4); nobody offers a genuinely candidate-controlled anonymised search product.

---

## 3. Honest Model Pressure-Test (carry this into any pitch deck or investor conversation)

**Why agencies actually get paid** (and what a pure database removes):
1. Proactive sourcing of passive candidates — Duxier doesn't do this; candidates opt in themselves.
2. Screening/filtering before a client wastes time.
3. Process management (chasing, counter-offer handling).
4. Risk transfer (rebate guarantees on failed hires).
5. Confidentiality management.

A searchable anonymised database only solves the *lowest-value* part of the problem (finding CVs). Firms with an open vacancy may still prefer paying someone else to run 2–4 for them.

**Unresolved and needs deciding before build:**
- **Monetisation model.** Not agency fees — but what replaces it? Options: flat subscription for firms to search, pay-per-reveal, candidate-side premium/promoted listing. *Pick one before backend work starts.*
- **Seeding/chicken-and-egg.** Candidates won't list into an empty platform; firms won't pay to search a thin pool. Need a concrete plan to get 100–200 anonymised profiles live (HMRC/ex-Big 4 weighted) before general firm access opens.
- **Verification layer.** Are profiles self-reported only, or is there any screening/verification? Unverified profiles will be discounted hard by firms used to agency vetting.
- **Legal/compliance framing for the HMRC angle.** Market this as general professional discretion, not as a route to bypass Civil Service Business Appointment Rules or conduct rules. Get this copy checked before public launch.
- **Anonymisation methodology, for real.** In a 45,000-person specialist market, quals + PQE + region + employer size often de-anonymise someone even with the name removed. Needs an actual redaction spec (see Section 5), not just marketing language.

---

## 4. Brand & Positioning

- **Name:** Duxier Tax Recruitment. Domain target: duxiertaxrecruitment.com.
- **Core line:** "Firms don't need another agency. They need to see who's already looking."
- **Positioning axis:** No placement percentage + candidate-controlled confidentiality, sharpened by the HMRC/in-house discretion wedge.
- **Tone:** Direct, confident, document/ledger-inspired — not corporate-safe navy-and-stock-photo like the Tier 1 incumbents.

---

## 5. Brochureware Site — Already Built

**File:** single self-contained HTML file, already created and committed to a local git repo (not yet pushed anywhere).

- Local path when built: `/home/claude/duxier/index.html`
- Delivered copy in this conversation: `/mnt/user-data/outputs/duxier-tax-recruitment.html`
- Local git repo: initialised, branch `main`, one commit: `"Initial brochureware site — Duxier Tax Recruitment"`

**Design system used:**
- Palette: ink navy `#0B1220` / `#141C2B`, paper `#F7F5F0` / `#ECE7DA`, brass accent `#AD8A54` / `#C8A468`, forest-green "verified" stamp `#2F6F52`, redaction black `#12151C`.
- Type: Fraunces (serif display), IBM Plex Sans (body), IBM Plex Mono (reference numbers, redaction labels, data).
- Signature element: a literal "redacted CV" document card in the hero — role/quals/PQE visible, employer/name/contact shown as black redaction bars — demonstrates the entire mechanic visually before any copy is read.

**Sections built, in order:**
1. Nav — logo, anchor links, "For professionals" / "For firms" CTAs.
2. Hero — headline, redacted CV card pair, dual CTA.
3. The problem — £4bn / 45,000+ / 20–30% fee stat strip, pull-quote.
4. How it works — two-column path (Firms: search → shortlist → request reveal → hire direct; Professionals: submit → redact → get requested → approve reveal).
5. Comparison table — Traditional Agency vs Duxier across fee, discretion control, candidate pool, search access, who built it.
6. Confidentiality/trust section — four-point anonymisation methodology (employer generalised, dates ranged, location broadened, identity locked).
7. HMRC/in-house callout banner — discretion messaging, deliberately framed around general professional confidentiality rather than encouraging any conduct-rule workaround.
8. Final CTA — dual lead-capture panels (firm registration, candidate registration). **Front-end only — forms show a success state but do not submit anywhere yet.**
9. Footer.

**Known gaps to close before this goes live:**
- Lead forms need real submission handling (email notification, CRM, or simple DB — decide based on monetisation model above).
- No pricing is shown anywhere — deliberate until monetisation is decided, but the "no placement percentage" promise needs a concrete replacement stated before firms are asked to register.
- Confidentiality section makes methodology claims that need to be true in the actual backend before public traffic arrives.

---

## 6. What Claude Code Should Do Next

**Immediate (repo + deploy):**
1. ~~Create a new GitHub repo: `duxier-tax-recruitment`.~~ **Done** — public repo at [github.com/mcfearless75/duxier-tax-recruitment](https://github.com/mcfearless75/duxier-tax-recruitment).
2. ~~Push the existing local commit.~~ **Done** — pushed to `main`.
3. ~~Wire up GitHub Pages, point custom domain.~~ **Done** — GitHub Pages enabled on `main` root, `CNAME` file set to `duxiertaxrecruitment.com`. **Outstanding: add the DNS records at GoDaddy (below) to complete the link** — Pages is live now on the default `mcfearless75.github.io/duxier-tax-recruitment/` URL and will pick up the custom domain once DNS resolves.
4. Wire the two lead-capture forms in the HTML to an actual endpoint (Formspree/simple serverless function/Airtable — pick the lightest option that doesn't block launch).

**GoDaddy DNS records needed for `duxiertaxrecruitment.com`:**
| Type | Name | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | mcfearless75.github.io |

Set these in GoDaddy DNS management. Once they propagate, GitHub Pages verifies the domain automatically and issues an HTTPS certificate (usually within an hour, sometimes up to 24h).

**Before opening firm access (not urgent, but sequence matters):**
5. Decide and build the monetisation mechanic (subscription paywall vs pay-per-reveal vs candidate premium) — this determines whether firm-side auth/billing needs to exist before any real search feature ships.
6. Build the actual anonymisation pipeline for candidate submissions: employer name → sector/size band, exact dates → PQE range, town/postcode → region, name/contact → hidden field unlocked only on mutual reveal approval.
7. Build the reveal-request/approval flow (candidate must actively approve before identity is shown to a firm) — this is the actual product, not the marketing site.
8. Seed 100–200 real or realistic anonymised profiles, weighted toward HMRC/in-house/ex-Big 4, before general firm registration opens.

**Legal/compliance checkpoint (flag, don't solve in code):**
9. Get the HMRC/in-house discretion messaging checked against Civil Service conduct rules and Business Appointment Rules framing before this goes live publicly — currently written to describe general professional discretion, not to imply help evading employer/departmental awareness.

---

## 7. Open Decisions Paul Needs to Make (blocking, not code work)

- Monetisation: subscription / pay-per-reveal / candidate premium — pick one.
- Seeding strategy: how are the first 100–200 candidate profiles actually sourced?
- Verification: self-reported only, or some proof-of-qualification layer?
- Repo visibility: public or private GitHub repo?
- Hosting: GitHub Pages vs Vercel vs Netlify vs existing infrastructure (PRL Azure tenant?).
