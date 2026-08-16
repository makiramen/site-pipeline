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

## The three stages

The page now carries the whole search, not just the first pass. Switch stage with
the segmented control above the tabs. The engine, the assumption sliders and the
scorecard weights are shared — only the dataset under them changes.

| Stage | Date | What it is |
| --- | --- | --- |
| **Towns** | 05 Aug 2026 | The original run. 25 UK and Ireland towns plus Westfield Stratford as a benchmark, each scored on the best of up to three formats at our standard sizes. Rents are mostly reasoned estimates. |
| **Units** | 10 Aug 2026 | 23 modelled units across 16 towns from the agent schedule, with quoted terms. Each is modelled as advertised, at Maki format with the surplus handed back, and — where the demise runs more than 15% over format — on full rent for a Maki-sized trading area. |
| **Savills call** | 14 Aug 2026 | The same units with Savills' own status applied: live or rejected, their reason, and the incumbent trade they have quoted for each scheme. Adds Wandsworth, which is new on this schedule. |

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

## Notes

- The model is a single self-contained HTML file; there is no build step.
- To update it, replace `Maki_Ramen_Site_Pipeline_INTERACTIVE.html` and commit.
- This repository is **public** — anything added here is readable by anyone.
  The 10 Aug and 14 Aug stages carry quoted rents, agent status and third-party
  trade figures. Consider whether that belongs on a public URL.
