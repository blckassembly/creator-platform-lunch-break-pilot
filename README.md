# Creator Platform — Lunch Break Pilot

**The food moment, from the platform's side of the glass.**

Built at the **Creator Economy Hack (powered by You.com)** — November 22, 2026, New York City.

Everybody builds for the viewer: a search box, a card, a link. But a viewer mid-stream never searches — the stream is clean, the streamer is an hour in, and nobody leaves to hunt for food. The platform sees what the viewer never does: **everyone watching, everywhere they are, all at once.** This repo is the data layer for the console that watches the watch party.

## The pilot

- **Campaign:** Lunch Break Pilot
- **Buyer:** Northline Media · **Brand:** Metro Burger
- **Creators:** Kai Voltage (Twitch, Gaming) · The Late Mic (YouTube, Podcast)
- **Markets:** Suffolk County, Nassau County, Buffalo (New York)

Console flow: **Wallboard → Signal Desk (You.com evidence) → Geofence Planner → Test Buy Builder → Live Results → Budget Reallocation.**

## The data doctrine: live, never static

Static data lies. A census of accounts counts people who haven't updated a profile in ten years — the age is stale, the income is stale, but their **activity** is current. So this platform never reads static profile data. It reads **live, verified, activity-current data**:

- **Is the person active right now?** (not "do they have an account")
- **What is their age?**
- **What is their income?** — read the way payroll reads it: current, verified, true today.

Ordering follows money, not appetite. Food-ordering volume rose when dining moved online during COVID, fell when people went back outside, and fell again when the free money ran out. Appetite never changed — income did. The Signal Desk is built to read the money.

Two corollaries:

1. **Resolve the payer, not just the viewer.** Kids stream on their parents' accounts and ask their parents for what they want. A college viewer's spending power is their parents' payroll record.
2. **Scale flips the play.** A 20-million-viewer event is tailgate logic — food prepped before kickoff, a split-screen QR moment, the crowd itself is the data.

## What's in this repo

```
data/
  adp/
    payroll_activity_sample.csv   — synthetic ADP-style payroll/activity records
    audience_segments.json        — aggregated live audience segments per market
  foursquare/
    food_locations_sample.csv     — food locations in Foursquare Places schema
```

See `data/README.md` for the data dictionary.

## Honesty note

All data in this repo is **simulated sample data**, built for the hackathon demo and structured exactly the way the live integrations will deliver it: ADP-style payroll/activity feeds for verified live income and activity, and Foursquare Places for real-world food locations and fulfillment coverage. The demo simulates live data; the calls are designed live.

## What's next

Live stream ingestion (real creator feeds and chat), live You.com calls in the Signal Desk, live payroll/activity and places integrations, and a first real pilot with a QSR brand and working creators.
