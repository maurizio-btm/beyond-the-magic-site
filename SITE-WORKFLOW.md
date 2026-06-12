# BTM Site — Improvement Workflow
*Drafted June 11, 2026 · From design critique + Maurizio's direction*

This file is a working plan, not site content. Keep it out of `main` if you prefer — it's safe to commit (nothing sensitive), but it's only for us.

---

## Phase 1 — Quick wins (I do these; ~1 session; no new content needed)

These are small, scoped fixes. Per our golden rule, items marked ⚠️ touch multiple files or page structure, so I'll proceed only on your go-ahead.

| # | Change | Files | Status |
|---|--------|-------|--------|
| 1.1 ⚠️ | **Dennis → "Co-Founder"** everywhere: homepage contact card, People page card + modal + bio, welcome page, etihad page | `index.html`, `people-behind-the-magic.html`, `welcome/`, `etihad/` | ✅ Done June 11 |
| 1.2 | **Contrast review** — corrected finding: the site already follows the brand rule (copper on light, copper-light on dark). Brand copper #A0714F on off-white measures ~3.8:1, just under AA's 4.5:1 for small labels. A real fix needs a darker copper added to the palette or navy labels — **brand decision, parked for Maurizio** | `styles.css` | ⏸ Parked |
| 1.3 | **"Let's Talk" overlap** — root cause found: Cal injects a `<cal-floating-button>` element with no inline style, so the old detector (looking for inline `position:fixed`) never hooked it on *either* page. Rewrote detection on both pages | `index.html`, `people-behind-the-magic.html` | ✅ Done June 11 |
| 1.4 ⚠️ | **Mobile menu opacity**: overlay was 98% — now solid `--navy-deep` on all 4 pages with a mobile menu | `index.html`, `people-...html`, `scheduling/`, `welcome/` | ✅ Done June 11 |
| 1.5 ⚠️ | **Mobile "Let's Talk" timing**: on ≤768px the pill now also hides while the hero is on screen | `index.html`, `people-behind-the-magic.html` | ✅ Done June 11 |
| 1.6 | **Stats cleanup**: dropped "3 Languages Delivered"; People stat relabeled "Industries on This Bench" to distinguish from homepage "Industries Served" | `index.html`, `people-behind-the-magic.html` | ✅ Done June 11 |
| 1.7 | **Hero BizHealth removal**: removed the "Start with a Health Assessment" outline button and the "Not ready for a full engagement?" helper line; "Our Story" promoted to the secondary (outline) button. Mid-page diagnosis panel untouched | `index.html` | ✅ Done June 11 |

**Discovered during 1.7:** the main-nav "ASSESSMENT" item links *externally* to bizhealth.ai on every page — a bigger leak than the hero line. Recommend repointing it to the Phase 3 internal page when that's built (nav change across pages = needs Maurizio's go).

## Phase 2 — Named bench ✅ Built June 11 (pending Maurizio's copy review)

Roster rebuilt with 5 named cards: Dr. Tricia Garwood, Stacey Robbins MBA, Shari Berens (Bright Bridge titles minus "Co-Founder"), Laura Nugent, Kimberly Maciejewski (Project Managers). Sources: Bright Bridge bios + LinkedIn. Open items: headshots (cards are text-only for now), whether to mention Bright Bridge Strategies by name, whether the "11+ Practitioners" stat stays.

<details><summary>Original plan</summary>

Goal: convert the anonymous specialist roster on the People page into named practitioner cards — directly answers "this is a dedicated team, not a one-man show."

**What I need from you (per person):**
- Name and title/specialty (as it should appear)
- Whether their existing anonymous blurb can stay as-is under their name, or needs a rewrite
- Headshot (optional but strongly recommended — even 3 of 9 with photos beats zero; square crop, goes in `assets/`)
- Confirmation each person approved the exact wording (you said agreements are signed — this is just the courtesy pass)

**What I'll do:** redesign the roster cards to match the Maurizio/Dennis card pattern (photo, name, specialty label, blurb, capability tags), keep brand styling, add `.reveal` animation. One line of intro copy explaining the bench model stays.

</details>

## Phase 3 — BizHealth.ai bridge page ✅ Built June 11

`bizhealth/index.html` created (hero → what it is + Dennis disclosure → 4 stat cards → platform hub: BizTools / BizGrowth Academy / BizLeaDer / BizGuides → bridge band with dual CTA). All nav, mobile menu, and footer "Assessment" links across the site now point to `/bizhealth/`; the homepage diagnosis panel points there too ("Explore the Assessment"). The only remaining external bizhealth.ai link is the "Begin the Assessment" CTA on the bridge page itself.

<details><summary>Original plan</summary>

Goal: support BizHealth without leaking visitors off-site in the first 10 seconds.

1. **New page** `bizhealth/index.html` — "A right-sized starting point." Positioning: for organizations that want clarity before (or instead of) a full engagement. Honest disclosure line: *"BizHealth.ai was founded by BTM co-founder Dennis Hough"* — transparency reads as strength here, and it converts BizHealth's existence into proof of bench depth rather than a competitor link.
2. Page structure: what it is → who it's for → what you get → how it relates to a BTM engagement ("many BizHealth diagnostics become BTM roadmaps") → CTA out to bizhealth.ai + secondary CTA back to booking.
3. Repoint the homepage "Start with diagnosis" panel to this internal page instead of straight to bizhealth.ai.
4. Nav: do **not** add to main nav (keeps nav tight); link from the diagnosis panel and footer only.

**Need from you:** 3–5 bullet points on what BizHealth actually delivers (report? score? consultation?) and price posture, so the page is concrete.

</details>

## Phase 4 — Proof, without waking the mouse

The constraint: pre-BTM work was under a Fortune 100 employer; no client-name permission. Only signed BTM client: Air Canada Rouge. The hidden client section stays hidden. Here's the path that's both safe and persuasive:

### 4a. Air Canada Rouge — the permission ask (highest value, do first)
Make a tiered ask to your contact there. Tiers, best to worst:
1. Logo + short case study with outcomes
2. Named case study, no logo
3. Attributed quote from an individual ("—Director of Inflight Experience, Air Canada Rouge")
4. Anonymized: "a North American leisure airline"

People say yes to tier 3 far more often than tier 1 — ask for tier 1, offer the fallbacks in the same email. I can draft this email when you're ready. Their comms/brand team usually has a standard logo-use approval path; your champion just needs to route it.

### 4b. Anonymized engagement snapshots (no permission needed)
Replace the hidden client wall with 3–4 "Engagement Snapshots" — industry + scale + problem + outcome, zero names:
- *"Global entertainment resort operation · 375 frontline cast · service-culture system design"* — describing **your role and scale** is biography, not client endorsement. The line to never cross: logos, company names, or implying the company endorses BTM.
- Format: short cards under "Track Record," each ending with the outcome.
- I draft from your inputs; you verify every fact is something you'd comfortably defend if Disney legal read it.

### 4c. Individual testimonials (the underused channel)
People who worked with you can endorse **you** in personal capacity without their employer's permission — same legal theory as a LinkedIn recommendation:
- 3–5 quotes, attributed as "Name, Former VP Operations, Fortune 100 entertainment company" or with employer named *only if the person is comfortable*.
- You already have these relationships. Ask each for 2–3 sentences; I'll help shape placement (likely the "Why Us" section and People page).
- Bonus: link the footer to BTM's LinkedIn page (enterprise buyers check) — need the URL from you.

### 4d. Case study page for Air Canada Rouge (after 4a lands)
You have `case-studies/` in the repo already. When permission comes back at any tier, I build the case study at the granted level and add "Case Studies" to the nav. Until then, nav stays as-is.

## People page preview → publish procedure (set up June 11)

The new named-bench version lives at **`people-behind-the-magic-preview.html`** (noindex, "Preview Draft" badge bottom-left, includes Laura's photo). The live `people-behind-the-magic.html` keeps the approved Phase 1/3 fixes but the original anonymous roster and stats (11+/200+/Industries Represented), so clients see no change until sign-off.

Share with the team after pushing: `www.beyondthemagic.co/people-behind-the-magic-preview` 

**To publish after approval (tell Claude "publish the people page" or do by hand):**
1. Copy preview file over `people-behind-the-magic.html`
2. In the now-live file: remove the `<!-- PREVIEW BADGE -->` div, the `noindex` meta, restore the real `<title>` and meta description
3. Delete `people-behind-the-magic-preview.html`
4. Apply any feedback edits collected from the team first, of course

## Backlog — site cleanup

- [ ] **Harmonize scheduling-page nav**: `scheduling/index.html` still uses the old nav (Origin / Philosophy / Services — 9 items) while every other page uses the current 7-item nav (Our Story / How We Work / Why Us / People / Assessment / Schedule / Contact). Links work via hidden anchor shims, but labels are inconsistent. Same check for `welcome/index.html`.
- [ ] **Contrast decision (parked 1.2)**: small copper labels on light backgrounds sit at ~3.8:1 vs 4.5:1 AA. Needs a brand call: darker copper added to palette, or navy labels.
- [ ] **Delete stale `.avif` originals** in `assets/` (garwood.avif, Robbins.avif, Berens.avif) once Maurizio confirms the JPGs look right in production.
- [ ] **Laura + Kimberly headshots**: add photos to their roster cards when provided (same treatment as the Bright Bridge three).
- [ ] **Case Studies in nav**: pending the Air Canada Rouge permission ask (Phase 4a) — add when there's something to show.

## Backlog — the .com (no spend now)

Understood on the $1,999. Zero-cost / low-cost mitigations meanwhile:
- **GoDaddy backorder** (~$25 one-time) so if the listing lapses or expires you're first in line — cheap insurance, only if/when you want.
- Parked-page prices often drop after long no-sale periods; worth re-checking quarterly. I can set up a scheduled check that looks at the listing monthly and tells you if the price changes.
- Meanwhile .co is consistently used on the site, emails, and contact cards — that's already right. Make sure any printed material / proposals always show **beyondthemagic.co** explicitly so nobody guesses .com.

---

## Suggested order of execution

1. Phase 1 (one working session, after your go-ahead on the ⚠️ items)
2. Phase 4a email draft (5 minutes of my time, highest leverage — send it early, permission takes weeks)
3. Phase 2 as soon as you send the bench info
4. Phase 3 once you send the BizHealth bullets
5. Phase 4b/4c drafting in parallel with anything above
