# Maki & Ramen — UK Site Pipeline

Standalone interactive site pipeline model. Kept in its own repository so it is
completely separate from the operations dashboards
(`site-comparison`, `nori-sales`, `maki-am-dashboard`).

## Live link

https://makiramen.github.io/site-pipeline/

## Contents

| File | What it is |
| --- | --- |
| `Maki_Ramen_Site_Pipeline_INTERACTIVE.html` | The model itself — self-contained, no dependencies. Open it in any browser. |
| `index.html` | Redirect so the root URL above lands on the model. |

## The stages, and the town hub

The page carries the whole search, not just the first pass. Switch stage with the
segmented control above the tabs. On the four modelled stages the engine, the
assumption sliders and the scorecard weights are shared — only the dataset under them
changes. Two stages (Viewings, Agent book) are records, not models. The hub sits in
front of all of them and is where the page opens.

### Towns — all in one (the landing page)

The chronological stages each answer a different question and none of them answers
*"what do we know about this town"*. The hub does. It joins every dataset on the page —
the 05 Aug town model, the 10 Aug units, the 14 Aug Savills call, the 22 Aug visit, the
field scorecard, the Exeter appraisal, the Bluewater heads of terms and the agent book —
onto **one key per place**, and shows only the sections that exist.

**43 towns.** Each card carries a row of signal chips (heads of terms · written
appraisal · field score · visited · units and best score · live with Savills · agent
book · desk tier) so you can see what exists before opening anything. Click a town and
it expands full-width into the merged detail, ordered by what matters rather than by
date:

1. **Heads of terms** — if there is a live deal (Bluewater only, today)
2. **The town** — the 05 Aug model inputs, score, tier and analyst verdict
3. **Units offered here** — every unit with terms, occupancy, EBITDA, payback, plus the
   Savills call and scheme trade on each
4. **The visit** — what was viewed, terms that came back, competitive pressure, our
   stated position, and the ten-criteria field score with the observations
5. **Written appraisal** — where one exists, with the field-vs-desk disagreement flagged
6. **On the agent book** — units introduced but not yet on a schedule

Filter chips: at heads of terms · visited · live with an agent · has units · desk tier
GO. Free-text search matches town, scheme and unit names. Every section ends with a
button through to the stage that produced it.

**Nothing is recalculated in the hub.** Every figure is read from the stage that
produced it, so the hub and the stages can never disagree. The chronological stages are
all still there.

### The chronological stages

| Stage | Date | What it is |
| --- | --- | --- |
| **Towns** | 05 Aug 2026 | The original run. 25 UK and Ireland towns plus Westfield Stratford as a benchmark, each scored on the best of up to three formats at our standard sizes. Rents are mostly reasoned estimates. |
| **Units** | 10 Aug 2026 | 23 modelled units across 16 towns from the agent schedule, with quoted terms. Each is modelled as advertised, at Maki format with the surplus handed back, and — where the demise runs more than 15% over format — on full rent for a Maki-sized trading area. |
| **Savills call** | 14 Aug 2026 | The same units with Savills' own status applied: live or rejected, their reason, and the incumbent trade they have quoted for each scheme. Adds Wandsworth, which is new on this schedule. |
| **Viewings** | 22 Aug 2026 | The record of the 18–20 Aug viewing round — six towns, thirteen units — the seven scored field responses, the Princesshay Exeter appraisal reproduced in full, the per-town evidence register, the 2027 target-list decisions and the commercial rules set on 21 Aug. Not scored by the desk model (see below). |
| **Agent book** | 22 Aug 2026 | Every live unit the agents currently have on us, from the email record: 19 units across both Savills desks plus Time Retail Partners, with quoted terms, incumbent trade, the plans and brochures on file, and where each one stands. Unscored. |
| **Bluewater HOTs** | 25 Aug 2026 | SVL05 at Bluewater — the first unit in the pipeline to reach a heads of terms. Scored on the shared engine, run against the 18–20% margin standard, read clause by clause against what was agreed by email, and set against the six Landsec documents behind the deal. Opens by default. |
| **Value markets** | 25 Aug 2026 | Matt's 21 Aug longlist of 15 mid-and-north towns at a ~£45k rent target, researched to model-input standard and scored on the shared engine at street-level format. Two priced pitches per town — as briefed, and the best actually available. Carries the corrections to the brief, an evidence grade on every input, and the £1.2m reality check. |

## The 25 Aug value-market stage

Matt issued a 15-town value-market longlist on 21 August — mid-and-north towns at a
target rent of about £45,000, claimed capable of £1.2m–£1.6m. Every town has been
researched to model-input standard and run through the same engine as the other scored
stages. Three findings reframe the brief.

**£45k is above market, not a stretch.** Evidenced quoting rents for a 1,600–2,200 sq ft
unit run £8–£18 psf across the list. Wolverhampton's Victoria Street quotes £18,000 for
1,800–2,300 sq ft; Bolton's closest comparable is £20,004; Barnsley's Market Street lets
at £8.49 psf. Carrying £45k as a flat assumption overstates cost by roughly 2× in nine
towns and would have made them look uninvestable for the wrong reason. Rents on this
stage are the evidenced figure for the named pitch, not the brief's number.

**The revenue thesis does not hold.** A 2,000 sq ft street unit seats 61. To carry £1.2m
it needs roughly 931 covers a week at 68% utilisation, which maps to a demand index
around 0.68–0.74. Westfield Stratford indexes 0.822; the median town on this list indexes
0.41. Only Bury (0.670) gets close. The engine puts the real range at £0.62m–£1.20m,
centre of gravity about £0.88m. **Nothing on the list reaches GO.**

**The margin case is real, and it is the reason to keep going.** On the right pitch at the
real rent, occupancy lands at 3–6% of sales against 8–11% on the shopping-centre boxes.
Fourteen of fifteen clear the 18–20% net standard set on 21 August, and payback runs
1.6–2.9 years against 2.5–5 on the August board.

### Engine changes on this stage

Two deliberate differences from the town stage, both flagged in the page footnote:

- **Street-level capacity spec at 2,000 sq ft**, not a shopping-centre box.
- **Rates are built from evidenced rateable values at the 2026/27 RHL multiplier of
  38.2p**, not the town stage's `rates psf = 0.43 × rent psf` rule. That rule breaks in
  these markets because the RV routinely sits *above* the passing rent — Hanley carries an
  RV of £14.65 psf on a quoting rent of £11.27 psf. Small Business Rate Relief is not
  modelled anywhere on the page: a multi-site group is not eligible for it.

Everything else — the utilisation curve, the spend-per-head formula, the cost stack, the
scorecard weights and the tier thresholds — is shared with the other scored stages, and
the three earlier stages score identically before and after this stage was added.

### Two toggles that exist only here

Both read fields (`wsFull`) that only the fifteen value-market sites carry, so they are
inert on every other stage regardless of state.

- **Score cluster-neutral.** Network fit rewards distance from the existing estate. Every
  town on this list is infill within 20–65 minutes of a Maki site — Wakefield scores 0/10,
  Bury 0.5/10 — so the strategy is punished by construction. For a value-market cluster
  play, proximity is an operational asset (Lynas drops, AM rota coverage, kitchen support),
  not a liability. Dropping network fit and rescaling to 90 points makes Bury 79.1 and the
  only GO on the list. **This is a live question for the committee, not a display option.**
- **Ungate whitespace.** The no-Wagamama 40% discount was written in August and never
  exercised, because every town on the August list already had one. Eight towns here have
  none, so it bites for the first time. On the evidence the rule is right — Huddersfield's
  Wagamama delivery kitchen opened and closed in 90 days, and Warrington's absence next to
  sites in Bolton and Preston is a revealed judgement, not an oversight — but the toggle
  shows the board without it.

### The corrections to the brief

Recorded on the stage banner and in each town's deep dive:

- **Students.** UCLan is 22,015 FTE, not 35,000, and falling — and the institution is now
  the University of Lancashire. "University Centre Doncaster" is **799 HE students** on
  audited accounts, not a university. Wakefield has no university and the Leeds-overflow
  claim runs the wrong way geographically. Warrington's Chester campus at Padgate has
  closed. Barnsley is an FE college with an HE wing. Huddersfield is 13,430 FTE, not 20,000.
- **Whitespace.** "Likely — verify" was wrong seven times. Preston has a trading Wagamama
  *and* Cosmo at Animate. Stoke, Derby, Doncaster, Bolton and Wolverhampton all have
  trading Wagamamas. Middlesbrough is reported to have 9,025 sq ft of Cosmo's Umami signed
  on the named pitch. Wakefield, Barnsley and Doncaster each already have a ramen
  specialist trading. Genuine whitespace survives in six towns, not fifteen.
- **The pitch itself.** The named pitch is the wrong pitch in eleven of the fifteen.
  Golden Square Warrington closes at 17:30 four days a week and has no full-service
  restaurant in it. Frenchgate Doncaster closes at 17:30. The Potteries Centre and Market
  Place Bolton close at 18:00. Half of Wakefield's named pitch — The Ridings — is
  council-owned and scheduled for demolition around autumn 2028.

### The one hard trading comparable

**Koji, 314 High Street West, Sunderland.** 1,512 sq ft, 40–50 covers, prime pitch opposite
the Empire, turning over £8,000–£10,000 a week before it closed on 10 August 2026 — that
is £275–£344 per sq ft. The model puts a 2,000 sq ft Sunderland street unit at £391 psf,
so it runs **14–42% hot against the only hard number in this exercise**. The turnover is
vendor-stated on leasehold sale particulars, not audited. It is still the best number
available, and it is still a seller's number.

### What the adversarial pass changed

Nine claims were corrected before this stage was built, listed in full on the stage banner.
The material ones: Wolverhampton is 16th most income-deprived, not 9th (a count of
districts misread as a rank); Bradford is 17th, not 4th; Huddersfield's 4.7m → 5.5m
footfall uplift is withdrawn and the stage is scored on 4.7m flat, with Magnetar — not
Northdale Advisors — as the Kingsgate buyer; the Mander Centre has been receiver-controlled
since May 2022, not August 2025; and there is no YO! Sushi at Middlebrook.

## The 22 Aug viewings stage

Matt Jenner visited Plymouth, Exeter, Portsmouth, Basingstoke, Oxford and
Bracknell on 18–20 August. This stage carries, per town: the units actually
viewed and how (internal, external, customer inspection, walk-past), the terms
that came back, the competitive pressure on the unit, our stated position from
the 18 Aug target-list reply, and the verdict where one has been written.

It deliberately does **not** score. The assumption rail and the ranking board are
hidden on this stage. Nothing here re-ranks the earlier three.

### The field scorecard

**Correction.** An earlier version of this README and of the page said the site-visit
Google Form had no 2026 responses. That was wrong. The form carries **seven scored
responses filed 19–21 August**, covering all six towns of the round plus Solihull.
They are now the first thing on this stage.

Method, reproduced from the sheet and verified against every row:

- **Location feasibility** = mean of visibility, foot traffic, transport, ecosystem,
  competition & synergy — each 1–10 — × 10.
- **Demographic fit** = mean of audience density, consumer behaviour, cultural
  receptiveness, spending power, social proof, × 10.
- **Overall** = mean of the two.

| Site | Overall | Feasibility | Demographic |
| --- | --- | --- | --- |
| **Exeter** — Princesshay | **86%** | 86 | 86 |
| **Solihull** — Touchwood | **78%** | 80 | 76 |
| Basingstoke — Festival Place | 68% | 74 | 62 |
| Bracknell — The Lexicon | 67% | 72 | 62 |
| Oxford — George Street | 66% | 66 | 66 |
| Portsmouth — Gunwharf Quays | 57% | 50 | 64 |
| Plymouth — The Barcode | 46% | 60 | **32** |

**The calibration matters more than the ranking.** The form has taken fourteen real
responses since July 2025. Shoreditch Fat Hippo scored **81% and we took it** — the only
entry that became a trading Maki site, and so the closest thing to a pass mark the form
has. Exeter at 86% scores above our own Shoreditch. At the other end Mikaku Glasgow
scored 41% and Wagamama Edgware Road 43%, and neither proceeded; Plymouth's 32%
demographic fit is level with Mikaku, the lowest the form has ever recorded.

**Two findings that are not in any terms we hold:**

- **Oxford George Street** — roughly 60% of the demise is basement that cannot be
  customer-facing, ceiling under 6ft, damp. Large capex.
- **Basingstoke Festival Place** — Las Iguanas and Pizza Express are both being made
  vacant because they cannot hit trade figures, on top of the two units already empty.
  The units shown were two floors and 150 covers, judged too large; a third 5,000 sq ft
  retail unit is available.

**Editorial note.** Two responses use language that should not appear on a public URL.
Their substance is carried in full and the wording is paraphrased; those cards are
marked *wording paraphrased* and the sheet remains the record. The `Team Member` field
is unreliable — two rows carry the letting agent's name rather than the visitor's.

### The Exeter appraisal, in full

`Maki_Ramen_Site_Appraisal_Princesshay_Exeter.pdf` — 12 pages, prepared for the
Property Investment Committee — is the **only** written appraisal produced from the
round, and it is now reproduced in full on this stage rather than summarised in a
line. It carries: the 61/100 strategic score against a 62 conditional threshold and
the PROCEED WITH CAUTION call; a nine-attribute property read with Strong / Watch /
TBC / Verify ratings; the full SWOT at three levels each (why it matters, commercial
impact, long-term value); the competitor scoring matrix (Wagamama, YO! Sushi, Nando's,
Luciano's and the independents, scored 1–5 on brand, price, loyalty, delivery, lunch,
evening and composite threat); the partnership table with estimated annual customer
acquisition by channel; the weekly trading-intensity heat map; the trading-hours
recommendation; and the non-financial risk register with named owners.

It is here because it is the **template the other six sites are missing**, not just a
verdict. The defining finding stands: the unit is directly opposite Wagamama in a
single-scheme, mid-sized, value-led market, and the University of Exeter — ~38,800
students, close to 30% of the city — is the single lever that decides the head-to-head.

**And it disagrees with the field.** Exeter scores **86% in the field and 61/100 on the
desk**, on the same unit in the same week. The field visit scored cultural receptiveness
10 and competition & synergy 9 — Wagamama next door proves the demand and we take share
from it. The appraisal scored competitive position 4 and landed one point under its own
threshold — Wagamama opposite splits the ramen occasion two ways in a value-led market.
They diverge on exactly one question: **is an adjacent Wagamama proof of demand or a cap
on share?** That question is live at Exeter, Basingstoke, Bracknell and Portsmouth, all
of which have a Wagamama next door or opposite. Note too that the appraisal was written
against a c.£100k rent with everything else TBC, while the field visit records seven
live offers and a capital contribution on the table — they were not looking at the same
deal.

### The evidence register

Media counted from the Drive folder on 25 August; form responses from the site-visit
sheet.

| Town | Media | Written work |
| --- | --- | --- |
| Exeter | 1 photo · 5 videos | Form response 86% **+ 12-page appraisal, 61/100** |
| Solihull | not in the round folder | Form response 78% |
| Basingstoke | 1 photo · 5 videos | Form response 68% |
| Bracknell | 1 photo · 8 videos | Form response 67% |
| Oxford | 7 videos | Form response 66% |
| Portsmouth | 3 videos | Form response 57% |
| Plymouth | 9 photos · 4 videos | Form response 46% |

Every site now has a scored field response. What only Exeter has is a full written
appraisal on top of it — that is the remaining gap.

What it adds that the modelled stages did not have:

- **Portsmouth Gunwharf now has terms.** R30, the former Hubbox: 2,846 sq ft,
  £50 psf with turnover top-up, service charge £55,539, insurance £55,539, rates
  TBC, handover as seen. That closes one of the four `AWAITING TERMS` units
  carried on the 14 Aug stage.
- **Plymouth Cosy Club is a new unit entirely.** GF 937 + 1F 5,800 = 6,737 sq ft,
  £110,000 pa or turnover whichever is higher, service charge £62,603, rateable
  value £147,000, new 10/15 year lease with incentive, fitted but some F&F may be
  removed.
- **Oxford George Street is a new street-level cluster**, and it is not the same
  proposition as Oxford Westgate, which the 10 Aug model scored NO. 59 (fitted
  Zizzi) at £120k with 6 months rent free; 61 and 67–69 at £100k with 12 months
  incentive; 71 and 75 already under offer.
- **The 2027 target list with our verdicts on all 23 Savills targets**, plus the
  six we added: Trafford Centre, Manchester (final site), York, Bull Ring,
  Solihull and Bluewater.
- **The rules that now govern a viable site** — five years not two, six sites a
  year maximum, one opening every two months, fitted / low rent / low SC / low
  capex as the default profile, higher capex only at S-tier (Trafford, Bull Ring,
  Bluewater, Dublin), and an 18–20% net margin standard with a 20% minimum on the
  street-level search.
- **The street-level value longlist** issued 21 Aug — 15 mid-to-north markets at
  a c.£45k rent target.

## The 25 Aug Bluewater stage

Unit SVL05 in the Plaza, the former GBK — 3,951 sq ft on the ground floor, heads of
terms dated 20 August 2026 and issued by Savills on 24 August. It is the first unit
here that has terms in a document rather than an email, so it is the first one where
the margin standard can actually be applied.

It carries the whole deal: the terms, the margin gate, the scorecard, the scheme
evidence, the corrected pitch, the clause-by-clause read, the marketing package, the
launch window, the negotiating list and the document register.

Five things on this stage that no earlier stage does:

- **The margin standard is applied as a gate**, not recorded as policy. The ladder
  runs net turnover from £1.5m to £4.5m and marks PASS / FAIL at 18% and at 20%.
  Margin is shown twice — site EBITDA before the central recharge, and after it —
  so the definition cannot be argued after the fact.
- **The scorecard is the same engine as every other stage.** SVL05 scores **47.8,
  tier NO**. The 05 Aug town record scored Bluewater 41.3 on a reasoned £58 psf
  estimate; the quoted rent came in at £58.21 psf, so the estimate was right and the
  tier has not moved. What drags it is network fit (0.5/10 — M17 Lakeside is 25
  minutes away), whitespace (3.8/15 — Wagamama, Rosa's Thai and Chi already in the
  scheme) and occupancy cost (3.1/18).
- **The heads of terms are read against the email chain**, clause by clause: 3 points
  as agreed, 2 changed, 6 new and never negotiated, 2 unresolved tracked changes still
  sitting in the draft.
- **The assumption rail stays live.** Move a slider and the gate moves with it. The
  Viewings and Agent book stages hide the rail; this one does not.
- **The six Landsec documents are read out**, not just listed — the March 2026 leasing
  brochure, the January 2026 floor plans, the Spotlight media rate card, the Brand
  Partner pack, the PLUS+ pack and the 2026/27 marketing calendar.

The headline numbers, at the default assumptions:

| | |
| --- | --- |
| Total occupancy | £422,828 pa — **£107.02 psf** all in |
| Our capacity model | £1,942,973 net — **12.0%** site EBITDA, FAIL |
| 18% gate clears at | **£2,682,592** net turnover |
| 20% gate clears at | **£3,079,377** net turnover |
| Turnover rent overtakes the base at | £3,066,667 |
| Turnover rent hits the £300k cap at | £4,000,000 |
| Same model, Plaza treated as an evening pitch | **£2,207,924** — 14.6%, still FAIL |
| Landsec scheme sales density £569 psf × our demise | **£2,248,119** — 15.0%, still FAIL |
| Area comparators (agent, 4 Aug) | Bill's £2.98m → 19.6% · Five Guys £3.3m → 20.4% |

The gate table also carries a **share-of-footfall column**: what proportion of
Bluewater's 18m annual visits has to eat with us once, at the model's £24.10 spend per
head, for each row to happen. The 18% gate needs **0.62%**. Our capacity model delivers
**0.45%**. That is the gap stated as a business problem rather than an argument about
the model.

So the deal works if and only if this box trades close to the Plaza incumbents. Four
independent readings now sit under the gate rather than one, and they cluster around
£2.2m rather than £1.9m — but none of them clears £2.68m. The comparator that would
settle it, Wagamama's Bluewater turnover, has been quoted by Savills in every other
scheme on this pipeline but not in this one — and the January plans show Wagamama
trading directly above us on the upper floor of the same leg.

### What the six documents changed

- **The adjacency list in the agent's introduction email spans both floors.** SVL05 is
  ground floor only. On our own floor the neighbours are Nando's, The Real Greek,
  Browns, Gravity, Five Guys, Bella Italia, ASK, Pho and the Showcase cinema. Wagamama,
  The Big Easy, Rosa's Thai, Pizza Express, TGI Fridays and Ballerz are all upstairs.
  Bill's is not in the Plaza at all — it is in the Lower Rose Gallery. And Chi, the
  ramen and sushi operator the 05 Aug record scored against us, is in The Village at the
  opposite end of the scheme.
- **Landsec zones the Plaza as "family dining and entertainment"**, anchored by the
  Showcase cinema, the Gravity trampoline park and Dinotropolis soft play. The 05 Aug
  record priced this site on a 21:00 mall close. That is the evidence for revisiting the
  evening input — which has deliberately **not** been changed, so the score still stands
  as scored.
- **£569 psf scheme sales density** is the first scheme-level revenue anchor this model
  has ever had for Bluewater.
- **89 minutes dwell, not 82.** The brochure quotes 82 as Bluewater's own dwell time;
  the Spotlight deck shows 82 is the benchmark across Landsec's full-price assets and
  Bluewater is 89. Use 89 and say where it came from.
- **The marketing package is a real commercial term the model does not price.** Clause
  39 obliges us to agree a launch marketing budget with the landlord. The PLUS+ solus
  email to 151,000 Bluewater members at a 50–55% open rate — the highest of the nine
  Landsec destinations — is free to brand partners, as are the brand page, What's On
  listings, 31.1m of annual social reach, PR and influencer support. The paid Spotlight
  rates put the Plaza Screen that faces our own leg at £3,000 a fortnight. A credible
  paid launch is £13,800, or 12% of the capital contribution.
- **The launch window has a date.** January access plus the 16-week opening obligation
  puts us open in the first half of May 2027, and The Kent Food Fest is 16–17 May. Ask
  the marketing team to hold a slot before exchange, not after.
- Two figures in the pack disagree with each other and one is stale: brand partners are
  275+ in the brochure and 300+ in Spotlight, and the Spotlight deck still names House
  of Fraser as an anchor when NEXT is opening in that space in 2026.

### Engine changes

Both are backwards compatible and the earlier stages were regression-tested
row-for-row against the previous build — every score, tier, EBITDA and net-sales
figure on the Towns, Units and Savills stages is byte-identical.

- **Turnover rent.** `rentTurnoverPct` and `rentCapPa` on a format make rent the
  higher of the quoted base and a percentage of net turnover, subject to a cap. Where
  a unit carries no turnover terms this collapses to the quoted base rent.
- **Turnover override.** `netOverride` sets net sales directly instead of deriving
  them from capacity, scaling dine-in and delivery pro rata so the aggregator
  commission still lands on the delivery share only. This is what lets the same unit
  be tested at an agent-quoted or incumbent turnover rather than only at the model's.
- Also added: `ratesPa` and `insPa` so rates and insurance can be taken as quoted in
  £ pa rather than rebuilt from a psf figure.

## The agent book stage

Built from the Gmail record rather than from an agent schedule, because a large
part of the book has never appeared on one. Five groups:

- **In legals or under negotiation** — Westfield (board approved 3 Aug, final HOTs
  with Brodies), Bluewater SVL05 (rent and turnover agreed, open on the incentive),
  One Tower Bridge (two competing offers, our offer never sent).
- **Manchester and Trafford** — the two units from Jack Wagland at Savills
  Manchester. Neither has ever been on a Savills schedule, so neither appears on
  any earlier stage of this model.
  - **Trafford Centre — the Nimchi unit** (supersedes R11A): ground 2,659 +
    mezzanine 1,492 = 4,151 sq ft, c.£225k base rent, service charge £94,036,
    rates £79,550, vacant possession likely Q1 2027. Total occupancy £398,586 pa
    at £96.02 psf. Wagamama on the scheme does £6.89m net of VAT; Wingstop £175k
    a week. Terms came by WhatsApp on 18 Aug 2026 and have no document behind
    them. R11A — proposed on in August 2025 — has never been formally closed out.
  - **Manchester Oxford Street** (Unit B, St James Building, the Pizza Express):
    3,150 sq ft on a single ground floor, c.£130k rent at £41.3 psf, RV £75,000,
    service charge £3.26 psf. Scores 74/100, the highest in the pipeline. Blocked
    on the MAF2 Northern Quarter franchise radius, not on the market.
- **Introduced with terms, no decision taken** — Cardiff St Davids, Touchwood
  Solihull, Oxford 59 George Street, Oxford Westgate, Canary Wharf Wood Wharf,
  Canterbury, The Oracle Reading.
- **Declined** — Merry Hill (size), Brent Cross (rent), Kings Cross Vermuteria
  (size), each with the reason recorded so it does not come back round.
- **Franchisee track** — The Glades Pasta Remoli, Bromley Marugame Udon,
  St Marks Square Bromley, Southside Wandsworth.

Each card lists the plans, brochures and particulars on file for that unit — 42
entries in total. Trafford is the one unit whose terms rest on a WhatsApp message
rather than a document. Where a figure lives only inside an attachment and has never
been read out, the card says so rather than leaving the field blank.

## How the unit stages differ from the town stage

- **Rent and service charge are used as quoted**, in £ pa on a named demise. The
  £130 psf cap that guards against misread Zone A retail rents is not applied to
  a quoted total.
- **Trading area and demised area are separate.** Seats and sales come from the
  trading area; rent, service charge and rates are paid on the demise. That is
  what makes the full-rent variant meaningful.
- **The headline line is the Maki-format one**, not the biggest one. The
  as-advertised line scales revenue linearly with floor area with no demand
  ceiling in the model, so on a 6,500 sq ft demise it is an upper bound and not a
  forecast.
- **Units with rent or service charge quoted TBC are tiered `AWAITING`**, scored
  only on what is known, and their score is expressed against the points actually
  available rather than out of 100. They are not comparable with a fully priced
  unit.
- **Capex** is the £300k all-in trading box plus a shell-off allowance per surplus
  sq ft (slider, default £40). Neither figure is a Maki outturn.
- **The two occupancy columns are the same money twice.** *Occupancy cost £/yr* is the
  total paid to hold the unit — rent + service charge + rates + insurance. *Occupancy %
  of sales* is that figure divided by net turnover. The cost is close to fixed, so the
  percentage falls as the box trades harder, and it is the percentage the industry
  judges a site on. Under about 13% is comfortable; over 20% is where Bluewater starts
  at our own modelled turnover.
- **Street-level units use the street-level capacity spec.** The source workbook
  applied the shopping-centre front-of-house and cover ratios to every unit
  including the street ones; this build corrects that, so Cardiff 16 Working
  Street, Bromley 3 East Street, Covent Garden, Spitalfields, Oxford George
  Street, both Canary Wharf units and Wandsworth read slightly differently here
  than in `Maki_Ramen_Site_Pipeline_Model.xlsx`.

## The scheme benchmark (14 Aug stage only)

Savills quotes incumbent weekly turnover for most schemes. Where Wagamama is
quoted it is used as the read-across; otherwise the strongest credible comparator
stands in. Two things to hold on to:

- These are **bigger boxes than ours**. The ratio is a read on how hard a
  scheme's F&B trades, not a revenue target for a Maki unit. Healthy range in
  this batch is roughly 0.3–0.6.
- Where our model lands **above the incumbent line**, the model is wrong, not
  optimistic. The page flags that explicitly (it fires on Watford).

## Known weaknesses — read before quoting any single number

0. **The scorecard loses half its discrimination on the value-market stage.** Because
   rents there are so low, all fifteen towns score the full 18/18 on occupancy cost and
   thirteen score the full 15/15 on payback — 33 of the 100 points are effectively
   constant across the list. The ranking on that stage is driven almost entirely by
   demand, whitespace, affluence and network fit. The scorecard was calibrated for
   shopping-centre rents and is doing less work there than the score implies.
0b. **Five value-market towns have no publishable footfall** — Preston, Sunderland,
   Wolverhampton, Warrington and Doncaster — and take the model's not-sourceable default,
   which is punitive. Preston's demand index moves from 0.281 to 0.410 on a 7m assumption
   and Warrington's from 0.432 to 0.626. Buying MRI Springboard or Place Informatics for
   those five is the highest-value data purchase on the page.
1. **The Westfield Stratford benchmark fails its own model.** At our standard
   format and published rent tone Stratford does not clear the hurdle, yet we
   trade there profitably. Loading the real Stratford lease terms and trading
   numbers is the single highest-value fix and would recalibrate every line on
   every stage.
2. **Capex is a benchmark, not an outturn.** Real Shoreditch, Southampton or
   Birmingham build costs would make the payback column decision-grade. This
   matters most on the oversized demises.
3. **No demand ceiling.** Revenue scales linearly with sq ft. The as-advertised
   line on a large unit is always an upper bound.
4. **Two footfall figures are placeholders and must not be quoted externally:**
   Canary Wharf (Wood Wharf is not published separately from the 76m estate
   figure) and Covent Garden (Shaftesbury Capital publishes no estate footfall;
   the circulating 44m has no traceable source).
5. **Wandsworth is provisional.** New on the 14.08 schedule, its town inputs were
   built for this stage and its footfall is Landsec marketing copy at 8.5m.
6. **Savills rejects on grounds the scorecard does not contain** — fit-out
   condition, incumbent trade levels, pitch quality, competitive density. Four of
   our five GO units were killed on them. That is a gap in the model, not
   necessarily a wrong call by the agent.
7. **Two agent comments would move units and are not yet loaded:** Cardiff St
   Davids is expected to deal at c.£120k pa against £155k quoted with two years'
   incentive; Basingstoke would deal at £135–140k against £185k quoted with 12–18
   months.
8. **One unit is listed but not modelled:** Pasta Remoli, The Glades (Bromley) —
   every term is quoted TBC. It is named on the page rather than silently
   dropped.
9. **Every site has a field score; only Exeter has a full appraisal.** The seven form
   responses are on the page and the Exeter appraisal is reproduced in full. The gap is
   no longer "no verdict" — it is that six sites have a ten-criteria field score and no
   catchment, competitive or partnership analysis behind it.
9b. **The field score and the desk appraisal disagree on Exeter by 25 points**, and the
   disagreement is not reconciled anywhere. Neither instrument is weighted, combined or
   ranked against the other on this page, deliberately.
10. **The new terms on the 22 Aug stage are not yet in the model.** Gunwharf R30,
    Plymouth Cosy Club and the George Street units are recorded, not scored.
    Loading them into the units dataset is the next update.
11. **The 18–20% net margin standard is recorded as policy, not applied as a
    gate.** The GO / WATCH / NO tiers on the earlier stages are unchanged. If it
    were applied it would very likely re-rank the board.
12. **Nothing on the agent book stage is scored**, and the two Manchester units
    have never been in the model at all. Trafford R11A and Oxford Street are the
    obvious next additions to the units dataset.
13. **Three sets of figures sit inside attachments and have never been read out:**
    the Westfield heads of terms, the Canterbury particulars and The Oracle trade
    stats (an inline image). The Bluewater heads of terms have now been read out in
    full on the 25 Aug stage.
14. **The Bluewater fit-out is unpriced.** The landlord will not strip out, a new
    shopfront to Bluewater specification is required, and the kitchen extract and
    grease-trap system is on us. None of that is inside the flat £300k capex the
    model carries, and it is the largest unquantified number in the only deal on the
    board with a document behind it.
15. **The margin gate applies on the 25 Aug stage only.** Applying it across the
    Towns, Units and Savills stages would very likely re-rank the whole board; that
    remains a deliberate decision not taken.

## Notes

- The model is a single self-contained HTML file; there is no build step.
- To update it, replace `Maki_Ramen_Site_Pipeline_INTERACTIVE.html` and commit.
- This repository is **public** — anything added here is readable by anyone.
  The 10 Aug, 14 Aug and 22 Aug stages carry quoted rents, agent status,
  third-party trade figures, named competing bidders and internal margin targets.
  Consider whether that belongs on a public URL.
