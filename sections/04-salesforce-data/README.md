# Salesforce — Find & Pull Data

Salesforce is MMA's CRM. This section covers the most common lookups and data pulls you'll need.

**URL:** https://mmaglobal.lightning.force.com
**Login:** Your MMA email + Salesforce password

---

## Key concepts

- **Account** = a company (e.g., Procter & Gamble)
- **Contact** = a person at that company
- **Campaign** = a list of contacts associated with an event, email, or program (e.g., "CATS May 2026 - Registrants")
- **Account Status values:** `Active-Parent`, `Active-Subsidiary`, `Active-Local Council` = current member; `Inactive`, `Cancelled`, `Non-Member` = not a member
- **Protected contacts** = board members, B2B CMO Council, MFC — never edit their contact records; only Jade, Angela, and Shauna touch these

---

## Tasks

### 🟢 EASY: Look up a contact

![Search for a Contact](../../assets/screenshots/salesforce/01-search-contact.png)

1. Click the **search bar** at the top of any Salesforce page
2. Type the person's name or email address
3. Salesforce will show matching Contacts and Leads
4. Click the Contact record to open it

> **Can't find them?** Try searching just the last name, or search by email. Also check whether they might be a **Lead** (not yet converted to a Contact).

---

### 🟢 EASY: Check if a contact is a board member

![Protected Contact Fields](../../assets/screenshots/salesforce/04-protected-contact.png)

1. Open their Contact record
2. Look for any of these fields being checked:
   - `Is Board Member` = checked
   - `Current B2B CMO Council Member` = checked
   - `Current MM25 Board Member` = checked
   - `Committee Member` = checked
3. If any of these are set → **do not edit the contact record.** Flag to Jade or Angela.

---

### 🟢 EASY: Check a contact's email opt-out status

1. Open the Contact record
2. Look for **Email Opt Out** — if checked, they've opted out of marketing emails
3. Also check **Pardot Do Not Email** — an older field that means the same thing

> If you need to reach someone who has opted out, ask Amanda — she'll know the right approach.

---

### 🟢 EASY: Check all 4 email fields on a contact

![Contact Email Fields](../../assets/screenshots/salesforce/03-contact-email-fields.png)

Salesforce stores up to 4 emails per contact. If you can't find someone by email, check all four:

1. **Email** — primary email
2. **Secondary Email** (`Secondary_Email__c`) — second work email
3. **Personal Email** (`Personal_Email_Address__c`) — personal/alternate
4. **MediaRadar Verified Email** (`MediaRadar_Verified_Email__c`) — auto-enriched

---

### 🟢 EASY: Check a company's membership status

![Account Membership Status](../../assets/screenshots/salesforce/02-account-status.png)

1. Search the company name in Salesforce
2. Open the **Account** record
3. Check the **Status** field:
   - `Active-Parent`, `Active-Subsidiary`, or `Active-Local Council` = ✅ current member
   - `Inactive`, `Cancelled`, or `Non-Member` = ❌ not active
4. Also check **X2026 Dues Charged** — if it shows $0 and status is Inactive, they're definitely not active

---

### 🟡 MEDIUM: Build a report or run a list view

![Salesforce Reports & Export](../../assets/screenshots/salesforce/05-reports-export.png)

**Option A — Use an existing report (fastest)**
1. Go to **Reports** in the top nav
2. Use the search bar to look for a report by name — someone may have already built what you need
3. Click the report → **Run** → review results
4. To export: click **Export** → choose **Excel** or **CSV (Details Only)**

**Option B — Build a new report**
1. Go to **Reports** → click **New Report**
2. Select a report type (e.g., "Contacts," "Contacts with Campaign Members," "Accounts")
3. Add filters — e.g., Account Status = Active-Parent, Region = NA
4. Add the columns you need (e.g., Name, Email, Title, Account Name)
5. Click **Run** to preview
6. Click **Save** to name it, then **Export** if you need a file

> **Tip:** Always search for existing reports before building new ones. There are a lot of pre-built reports already in there.

---

### 🟡 MEDIUM: Pull a campaign member list

Campaigns in Salesforce track who was invited, registered, or attended an event or program.

1. Go to **Campaigns** in the top nav (or search the campaign name in the search bar)
2. Open the campaign record
3. Scroll down to **Campaign Members** related list
4. You can see everyone in the campaign and their **Status** (Invited, Registered, Attended, etc.)
5. To export: click the **dropdown arrow** next to "Campaign Members" → **Export to CSV** (or run a Campaign Members report)

> To find the right campaign, search by event name and year — e.g., "CATS May 2026."

---

### 🟡 MEDIUM: Update a contact's title (only if blank)

1. Open the Contact record
2. Click the **pencil/edit icon** next to the Title field (inline edit)
3. Type the correct title
4. Click **Save**

> Only do this if the Title field is completely blank. Don't overwrite an existing title — even if it looks outdated, flag it instead.

---

### 🟡 MEDIUM: Add a contact to a Salesforce campaign manually

1. Go to the Contact record
2. Scroll down to the **Campaign History** related list
3. Click **Add to Campaign**
4. Search for the campaign name → select it
5. Choose the correct **Status** (usually "Invited" or "Registered")
6. Save

> For adding more than a handful of people at once, it's faster to run a report and use the **Campaign** → **Manage Members** import — but for 1–5 people, this method works fine.

---

### 🟡 MEDIUM: Check if someone is already in a campaign

1. Open their Contact record
2. Scroll to **Campaign History** related list
3. You'll see every campaign they've ever been added to, with their status in each

---

---

## How to build large audience reports

This section covers the filter logic for building contact lists for event invitations, Outreach sequences, and member outreach — and answers questions like "what filters do you use?" and "do you include subsidiaries?"

---

### Region scope — always NA + Global

Every large audience pull includes **both** `Region = NA` and `Region = Global`. Global accounts are multi-region members and are always included alongside North America. There is no separate "Global Market" filter — it's baked into the standard region clause.

> If a pull is specifically for a regional event (e.g., EMEA only), the region is changed accordingly. But the default is always NA + Global.

---

### What "Active member" includes — subsidiaries too

The membership filter is always:

```
Account Status starts with "Active"
```

This catches all three active status values:
- **Active-Parent** — the primary member company account
- **Active-Subsidiary** — a subsidiary of a member; also a member
- **Active-Local Council** — active local council member

Yes, subsidiaries are included. If a subsidiary is active, they are a member in good standing and their contacts are pulled.

> **Note:** `Active-Subsidiary (irrelevant)` is also technically caught by the filter but is usually excluded intentionally — it marks subsidiaries that exist for hierarchy reasons only, not as real membership accounts.

---

### The mailable definition — who gets filtered out

For any outreach-facing list, a contact must pass **all** of the following to be included:

| Filter | What it removes |
|---|---|
| **Email is not blank** | Contacts with no email address on file |
| **Email Opt Out = false** | Anyone who has unsubscribed |
| **Is Email Bounced = false** | Hard bounces (the standard SF field, not Pardot's bounce field) |
| **Is Board Member = false** | Global, NA, Media, CDO, APAC, EMEA, LATAM, and MFC board members |
| **Current B2B CMO Council = false** | B2B CMO Council members (not covered by Is Board Member — must be explicit) |

These five conditions are AND'd together — a contact is excluded if any one of them fails.

> **Why Is Board Member alone isn't enough:** The `Is Board Member` field covers most boards but does NOT cover B2B CMO Council. Those members pass the board filter naturally, so the B2B CMO Council exclusion must always be added separately.

> **MFC members:** The `Is Board Member` catch-all includes MFC. If a pull is intended to include MFC members (e.g., MFC-targeted outreach), you override it with a separate clause. For standard non-board audience pulls, MFC members are excluded along with other board types.

---

### How CMOs are identified — key role field, not title

For **member accounts**, CMOs are identified using the **`Account.CMO__c` key role field** — a dedicated lookup field on the Account record that points to the specific Contact who holds that role. This is maintained by Shauna.

**Do not use title string matching** (e.g., `Title LIKE '%CMO%'`) for member accounts. Title strings are unreliable — they vary in format, go stale when someone leaves, and can create duplicates. The key role field is the authoritative source.

For **non-member accounts**, the key role may not be populated. In those cases, title-based filtering is the fallback.

---

### Standard report type — Contacts and Accounts

For most large contact pulls, Aaron uses the **"Contacts and Accounts"** report type (not "Contacts" alone). This is because filtering on account-level fields (Status, Region, Ecosystem) requires the account relationship to be present in the report type.

For event-specific pulls (who was invited, registered, attended), the report type is **"Campaign Members with Campaigns and Contacts"** — this lets you filter by campaign and see each person's status.

---

### Standard fields on every large report

These columns are on every standard contact export:

| Field | Why |
|---|---|
| First Name / Last Name | Required for Outreach import |
| Email | Required for any send |
| Title | For sequence personalization and filtering |
| Account Name | Company name |
| Primary Ecosystem | Marketer / Agency / Seller / Enabler etc. — used for segmentation |
| Account Status | Confirms active membership at export time |
| Title Level Dynamic | Formula-derived seniority (C-Level, VP, Director…) |
| Is Board Member | Flag for board status — never send board-specific content to non-board audiences |
| Current B2B CMO Council | Same reason — always visible on exports |
| Salesforce ID (18-digit) | For re-import matching and deduplication |

For event reports specifically, these are also standard:
- **Campaign Member Status** (Invited / Registered / Attended)
- **Seed List Tag** (flags contacts for specific outreach tiers, e.g., "2026 Tier 1 CMOs")
- **MFC Board** and **NA / Global / Media Board** flags individually

---

### Key standing reports Aaron uses

**Board membership — "Current boards - Jade"**

For any question about who is on a board, Aaron uses the report **"Current boards - Jade"** (SF report ID: 00OVR000002sCfl2AE). This is the authoritative source for board status — more reliable than querying the boolean fields directly, because Jade keeps it current in real time. If you need to verify whether someone is a board member, run this report first.

**Main CMO reports**

- **Member CMO [Marketers NON Board]** (SF report ID: 00OVR000005a6vF2AQ) — member CMOs excluding board members, identified by key role field.
- **CMOs on Board - NAGLMD - 2026** (SF report ID: 00OVR000003AMDd2AO) — board member CMOs.
- **Invited_Main 2026 Events** (SF report ID: 00OVR000005KfvO2AS) — the standard event report template; all event campaign exports use these fields and this structure.

**Mailable contact counts**

Tracked monthly in the custom object `Emailable_Contacts_Snapshot__c`. Three records per snapshot: Total, Marketer-only, and Solution Provider. This is where the "how many mailable contacts do we have?" answer lives — not from running a fresh report each time.

---

### A few things to know when building these reports

1. **Subsidiaries are included** in all standard pulls (see above). This is intentional — Active-Subsidiary accounts are fully active members, so don't filter them out.

2. **Use "Is Email Bounced"** (the standard SF field) as the bounce filter — not `pi__pardot_hard_bounced__c` (Pardot's bounce field). These are different fields; the SF native one is correct.

3. **Board exclusions require two filters**, not one. `Is Board Member = false` alone misses B2B CMO Council members — they don't have that field set. Always add `Current B2B CMO Council Member = false` as a second condition.

---

## ⚠️ Things to never do in Salesforce

- **Never delete records** — deactivate or flag to Aaron/Angela instead
- **Never merge board member records** — only Jade does this
- **Never remove the Account from a Contact** — every contact must have an account
- **Never modify Account Status** — that's Shauna's job
- **Never create a new Account** — if you can't find a company in Salesforce, flag it; don't create one
