# Renewals Support

Aaron attends and supports the weekly **Sales & Board Updates for Membership Renewals** meeting (currently on Wednesdays). His role is data support — pulling engagement and attendance data for at-risk accounts so the sales team can make informed decisions.

**Key people:**
- **Angela Gray** — runs the meeting, drives strategy
- **Shauna Peck** — tracks renewal status, owns action item tracking
- **Stephen Wellman** — sales lead (on medical leave as of mid-April 2026 — 90-day temp hire approved)
- **Kevin Granath / Jade Bentham** — board and executive relationships
- **Amanda Hyland** — handles outreach and follow-up

---

## What Aaron pulls for this meeting

### 🟢 EASY: Pull DAMit (Decoding AI for Marketers) attendance for a specific company

When the team asks "How many people from Walmart have attended DAMit sessions?"

1. In Salesforce, go to **Reports**
2. Find the report: "DAM/Decoding AI Registrants" or search "Decoding AI" in Reports
3. Filter by **Account Name** = the company in question
4. Export or read off the count

OR:
1. Go to the **DAMit campaign** in SF (search "Decoding AI" in Campaigns)
2. Click **View Campaign Members**
3. Filter or search by company

---

### 🟢 EASY: Check if a specific contact attended a particular event

1. Find the contact in SF
2. Scroll to **Campaign History** related list
3. Look for the event campaign — Status should show `Attended` vs. `Registered`

---

### 🟡 MEDIUM: Pull an engagement report for an at-risk member

When the team wants to show a member how much they've used MMA resources (to help with a renewal conversation):

1. In SF, find the **Account** record for the company
2. Look at:
   - **Contacts** tab → how many contacts are in SF
   - **Campaign History** on the Account or on individual contacts → events attended
   - **DAM certificates** (see Certificate Tracking section below)
3. In Pardot, look up their contacts → check open/click rates
4. Compile into a simple summary: "You have X contacts in our database, attended Y webinars, Z people have DAM certificates"

> Amanda often sends these "engagement reports" to at-risk members before a renewal call. Ask her what format she uses.

---

### 🟡 MEDIUM: Check Verizon (or another company's) attendee data — manual pull needed

Verizon attendee data is **not automated** — it has to be manually pulled from the event system.

1. Log into **Stova**: https://na-admin.eventscloud.com
2. Find the relevant event
3. Export attendees → filter by company = Verizon
4. Cross-reference against the SF campaign if needed

---

### 🔴 HARD: Building a full member engagement report PDF/Word doc

Aaron uses `engagement_report.py` / `engagement_report_docx.py` for formatted multi-page reports. For coverage, provide a manual SF report export and let Amanda format it for the renewal conversation.

---

## Renewals meeting cadence

- **Wednesdays** — Sales & Board Updates for Membership Renewals (Angela, Shauna, Amanda, Kevin, Jade, Aaron)
- **Action items** must be completed by end of Thursday
- **Stephen/Amanda** chase anything outstanding on Fridays
- **Goal:** everything actioned before Monday

> The team has been flagged that action items repeat week over week. Whoever covers Aaron should complete same-day or flag a specific date — not carry items open indefinitely.

---

## Key overdue account statuses (as of April 2026)

| Account | Risk Level | Notes |
|---|---|---|
| Tubi | High | $125K, rebudgeting, outcome uncertain |
| Peron | High | Stephen Yap needs re-engagement |
| PNC Bank | High | Jen Garbach unresponsive |
| 7-Eleven | High | $25K, lost main rep |
| MarketBridge | Medium | Reversed course, need meeting |
| NBC Universal, Google, Live Ramp | Medium | ~Day 60, check-ins needed |
| Walmart | Medium | Renewal drags like last year |
| Heineken | Low-Medium | Verbal yes received |
