# Data dictionary

All data in this folder is **synthetic sample data** for the Creator Platform — Lunch Break Pilot demo. It is structured to mirror the live feeds the platform is designed to call.

## `adp/payroll_activity_sample.csv`

Synthetic **ADP-style payroll/activity records** — the model for verified, live income data. One row per person. Payroll is the live truth about money: if the record is active and the last pay date is recent, the income is real *today*, not whenever a profile was last edited.

| Field | Meaning |
|---|---|
| `person_id` | Synthetic person identifier |
| `role` | `viewer` (watches streams), `payer` (holds the money/account), or `viewer_payer` (both) |
| `age_band` | Age range — activity data carries current age, profiles don't |
| `income_band_annual` | Verified income range from payroll, not self-reported |
| `employment_status` | `active` = currently on payroll |
| `employer_sector` | Industry of employment |
| `pay_cycle` | How often they are paid |
| `last_pay_date` | Most recent pay date — recency is what makes this *live* data |
| `county` / `zip` | Market geography (Suffolk, Nassau, Buffalo) |
| `activity_status` | `active_now` = activity current within the live window |
| `linked_person_id` | For a college viewer, the parent payer their spending resolves to |

## `adp/audience_segments.json`

Aggregated **live audience segments** per market, derived from activity + payroll-style data (never from static profiles): active viewers, age mix, income mix, and payer mix (`self` vs `parent_account`). Includes a `snap_households` segment — elderly households on SNAP benefits who can order food online with those benefits; going outside is hard, so the food moment has to come to them.

## `foursquare/food_locations_sample.csv`

Food locations in **Foursquare Places schema** (`fsq_id`, name, categories, latitude/longitude, address, locality, region, postcode) — the fulfillment layer. A food moment is only bought where it can be fulfilled: these are the Metro Burger stores behind the pilot's geofences (Suffolk 12, Nassau 9, Buffalo 4 — matching the console's eligible-store counts), each with pickup + delivery coverage notes in the console's Market & Geofence Planner.
