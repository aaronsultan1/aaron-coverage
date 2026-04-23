# HubSpot Migration (Major Upcoming Project)

MMA is actively evaluating moving from **Salesforce** to **HubSpot** as its CRM. This is a significant project Aaron is heavily involved in. The coverage person needs to know this is happening and who to escalate to.

**Current status (as of April 2026):**
- Demos completed (April 7 and April 1)
- Salesforce contract renewal decision deadline: **end of May 2026** (contract ends July 27)
- HubSpot team wants a decision within 2 weeks for a mid-June migration
- Team concern: aggressive timeline; some prefer September start
- Matt Craig (Finance) needs to evaluate if paying both systems temporarily is feasible

**Key people:**
- **Angela Gray** — leads the decision
- **Matt Craig** — evaluating financial feasibility
- **Aaron Sultan** — mapping data requirements, attending demos, assessing risk
- **Shauna Peck** — providing input on membership data needs
- **Dan Whiting** — reviewing website/Jason integration needs

---

## What the coverage person needs to know

### 🟢 EASY: Understand the current state

- **Nothing has been decided yet.** Salesforce is still the system of record.
- All current Salesforce tasks should continue as normal.
- If someone asks "are we moving to HubSpot?" — say: "It's under evaluation. Angela Gray is the decision-maker."

---

### 🟡 MEDIUM: If asked to attend a HubSpot demo or decision meeting

- Take notes on: what HubSpot can and can't do vs. Salesforce
- Key questions Aaron tracks:
  - Can HubSpot handle the board member protection rules (don't update protected contacts)?
  - How does Apollo integrate with HubSpot vs. Salesforce?
  - How does Outreach get replaced (HubSpot has its own sequences)?
  - What happens to all the Pardot lists and campaign history?
  - Can the website (Drupal) integrate cleanly with HubSpot?
- Pass notes to Angela and Aaron after the meeting

---

### 🟡 MEDIUM: If asked to do data mapping for the migration

Aaron was tasked with building a data mapping document. If asked to continue this:

1. Go to the existing Asana project Aaron created for the database build
2. The mapping doc lists: current SF fields → what they would map to in HubSpot
3. Key fields to verify: Contact Type, Board Member flags, Campaign History, Renewal Status, Ecosystem, Key Role
4. Do not delete or archive any SF records — migration hasn't been approved yet

---

### 🔴 HARD: Any actual migration work

Do not execute any actual migration steps. Hold all migration work for Aaron. The decision alone will take weeks of planning before any data moves.

---

## Why this matters for coverage

If the HubSpot decision gets made during Aaron's leave:
1. **The Salesforce → HubSpot data migration will become the #1 project for the membership team**
2. Many of Aaron's current Python scripts (Salesforce-specific) would need to be rebuilt for HubSpot
3. Pardot would be replaced by HubSpot Marketing Hub
4. Outreach sequences would be replaced by HubSpot sequences
5. The coverage period may coincide with Aaron having to ramp back up on a completely different tech stack

> **Bottom line:** Flag to Angela immediately if any migration decision is made. This changes everything about how the membership team operates.
