# SpecialtyScope 🩺

**Find the specialty that fits who you are, not just what it pays.**

SpecialtyScope is a free, open-source website for premeds and med students. A 5-minute self-check asks about your personality, stress limits, life outside work, feelings about lawsuits, and interest in research. It then matches you to **51 medical specialties** using published data on burnout, malpractice risk, hours, training length, match odds and pay.

👉 **Try it:** https://YOUR-USERNAME.github.io/specialtyscope

<p align="center">
  <img src="docs/home.png" width="260" alt="Home page with floating specialty bubbles">
  <img src="docs/self-check.png" width="260" alt="Self-check question screen">
  <img src="docs/results.png" width="260" alt="Self-check results with top matches">
</p>

---

## Why this exists

Most specialty websites rank fields by salary. That pushes students toward whatever pays most or trends online. SpecialtyScope starts from the other end:

- **Who are you?** Do people energize you or drain you? Do you stay calm in emergencies? Can you carry sad outcomes home?
- **How do you want to live?** Nights and weekends, stress, the chance of being sued, how many years you'll train.
- **Academia or practice?** How much you enjoy research and teaching.
- **The money check.** See your matches as if every specialty paid the same, so you can tell which picks fit *you*.

## Features

| Tab | What it does |
|---|---|
| **Home** | 51 floating specialty bubbles. Resize them by lifestyle, burnout, lawsuit risk, training length or pay. Tap one for its full profile. |
| **Self-check** | 15 statements plus 3 reflection questions. Shows a "self-portrait", your top 5, the money check, overlooked picks, and a copyable report. |
| **Explore 51** | Search, filter and sort every specialty. |
| **Lifestyle** | Pay vs. hours chart, plus rankings by lifestyle balance, hours, vacation, call, pay per hour, burnout and lawsuits. |
| **Compare** | Up to 3 specialties side by side, with a 20-year training timeline and running pay totals. |
| **Chance me** | **Residency:** odds of matching in 23 NRMP specialties for MD or DO seniors, adjusted for Step 2 CK. **Med school:** the AAMC acceptance rate for your GPA and MCAT. |
| **HPSP** | For military scholarship students: benefits, commitment rules, a payback timeline calculator, and new-doctor military pay. |
| **Sources** | Every dataset, linked, with methods. |

<p align="center"><img src="docs/lifestyle.png" width="820" alt="Lifestyle tab: pay vs. hours scatter chart"></p>

## Data sources

| Data | Source | Coverage |
|---|---|---|
| Average pay | [Doximity Physician Compensation Report 2026](https://www.doximity.com/reports/physician-compensation-report/2026) | All 51 specialties |
| Second pay estimate | Medscape Physician Compensation Report 2026 ([summary](https://thedo.osteopathic.org/2026/07/what-physicians-are-getting-paid-in-2026/)) | 29 specialties |
| Hours, PTO, call, schedule | [Marit Health 2026 Lifestyle Balance Index](https://www.marithealth.com/posts/2026-physician-lifestyle-balance-index) | 31 specialties |
| Burnout | AMA 2026 Organizational Biopsy ([summary](https://www.beckershospitalreview.com/quality/hospital-physician-relationships/6-of-20-physician-specialties-see-lower-burnout-but-lower-happiness-rates/)) | 15 specialties |
| Ever sued | [AMA Policy Research Perspectives, 2023](https://www.ama-assn.org/system/files/policy-research-perspective-medical-liability-claim-frequency.pdf) | 24 specialties |
| Annual claim rate | [Jena et al., NEJM 2011](https://pubmed.ncbi.nlm.nih.gov/21848463/) | Neurosurgery, thoracic surgery |
| Match rates, Step 2 CK | [NRMP Charting Outcomes 2026](https://www.nrmp.org/match-data/charting-outcomes-characteristics-of-u-s-md-seniors-who-matched-to-their-preferred-specialty-2026-main-residency-match/) | 23 specialties (MD and DO) |
| Research expectations | [NRMP Charting Outcomes 2024](https://www.nrmp.org/wp-content/uploads/2026/03/Charting_Outcomes_MD_Seniors2024_revised-citation.pdf) | 22 specialties |
| Med school admissions | [AAMC FACTS Table A-23](https://www.aamc.org/data-reports/students-residents/data/facts-applicants-and-matriculants) (2023–24 to 2025–26) | MCAT × GPA grid |
| Resident salaries | AAMC Survey of Resident/Fellow Stipends 2025 ([AMA summary](https://www.ama-assn.org/medical-residents/residency-life/resident-physician-pay-still-rising-growth-trails-inflation)) | PGY-1 to PGY-8 |
| Training length | [ACGME](https://www.acgme.org/specialties/) program requirements | All specialties |
| HPSP | [Air Force HPSP fact sheet](https://www.airforcemedicine.af.mil/Media-Center/Fact-Sheets/Article/425437/hpsp-fact-sheet/), [Navy Accessions](https://www.med.navy.mil/Accessions/Stipend-and-Bonuses-for-HPSP-FAP), [DFAS special pays](https://www.dfas.mil/MilitaryMembers/payentitlements/Pay-Tables/HPO4) | — |
| Personality research | [Stienen et al., BMJ Open 2018](https://bmjopen.bmj.com/content/8/7/e021310) | Context only |

**Where data is missing, the site shows "n/a" or a faded bubble.** It never fills gaps with guesses.

## How the estimates work

- **Self-check matching.** Each answer is scored from −1 to +1 and compared with each specialty on 12 dimensions: patient contact, pace, continuity, hands-on work, emotional weight, visual/puzzle work, lifestyle, lawsuit risk, burnout, training length, research culture and pay. Dimensions without data for a specialty are skipped for that specialty. Stress, lawsuits and lifestyle only count when you say you care about them. The six work-style ratings, such as "emotional weight", are **our own description of the daily work**, and the site labels them that way.
- **Residency odds.** The calculator starts from NRMP's 2026 match rate for seniors who listed the specialty first. For MD seniors, it then adjusts with Bayes' rule, treating matched and unmatched Step 2 CK scores as bell curves centered on NRMP's medians. Adjustments for research, letters, AOA, rotations and applying broadly are **stated assumptions**: NRMP ranks these factors as important but doesn't publish how much each one matters.
- **Med school odds.** These are the AAMC acceptance rates for each GPA × MCAT cell, with no adjustments.
- **HPSP timeline.** A simplified model: you owe the longer of your scholarship years or your military residency years. Your commitment paperwork is the final word.

## Run it yourself

It's a single HTML file with no build step, no backend, and no tracking.

1. Download `index.html`.
2. Double-click it to open in any browser, or host it anywhere: GitHub Pages, Netlify, Vercel, or your school's site.

**GitHub Pages:** go to Settings → Pages → Branch: `main` → Save. The site goes live at `https://YOUR-USERNAME.github.io/specialtyscope`.

## Updating the data each year

All the numbers live near the bottom of `index.html` in three constants:

- `SPECIALTIES`: one object per specialty. Key fields:
  - `pay`: Doximity average
  - `medscape`
  - `train`: years after med school
  - `life`: `{hours, pto, call, sched, lbi}` from Marit
  - `nrmp`: `{md, do, s2, q1, q3, um, comlex}`
  - `burnout`
  - `sued` / `suedYr`
  - `pubs`
  - `work`: the six work-style ratings, 0–1
- `AAMC`: the MCAT × GPA acceptance grid.
- `PGY`: average resident pay by training year.

When a new report comes out:

1. Update the numbers in the matching fields.
2. Update the matching entry on the Sources tab (`SOURCES` list).
3. Change the "Data checked" date in the footer.

New releases to watch for:

| Report | Usually published |
|---|---|
| NRMP Main Match results | Spring |
| NRMP Charting Outcomes | Summer, every other year |
| Doximity compensation report | Spring |
| AAMC FACTS tables | Fall |

## Contributing

Pull requests are welcome, especially:

- Newer or better-sourced data. Please link the source in your PR.
- Data for specialties marked "n/a".
- Corrections. If a number is wrong, open an issue with the source.
- Accessibility and translation improvements.

Please keep every number traceable to a public source, and label anything that's an estimate.

## Disclaimer

SpecialtyScope is an educational reflection tool, not career, financial, legal or medical advice. It isn't affiliated with or endorsed by NRMP, AAMC, AMA, Doximity, Medscape, Marit Health, the Department of Defense, or any military branch. Averages hide big differences by location, practice type and experience. Talk with residents and attendings, and shadow, before you decide.

## License

[MIT](LICENSE). Use it, copy it, improve it. The data belongs to its publishers. See the sources above.
