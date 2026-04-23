# Apollo — Contact Database & Enrichment

**Apollo** (https://app.apollo.io) is MMA's B2B contact database and prospecting tool. Aaron uses it to:
- Find new contacts at member companies (for outreach and database building)
- Enrich existing Salesforce contacts (fill in missing titles, LinkedIn URLs, emails)
- Build audiences for sales outreach campaigns
- Export contact lists for LinkedIn custom audiences

**Apollo URL:** https://app.apollo.io  
**Login:** Separate from Salesforce

**Key context:**
- MMA has a **1.3M credit plan** (~$28K/year) — credits are used for enrichment and exports
- Apollo's department filter is relatively new — only ~20% of the database currently has department data
- Apollo is also used for email outreach via campaigns (warm-up domain: mmaglobal.net)
- Apollo sync with Salesforce is in progress — for now, exports go to SF manually

---

## Tasks

### 🟢 EASY: Search for contacts at a specific company

1. Go to **Apollo**: https://app.apollo.io
2. Click **Search** → **People**
3. In the filters on the left, find **Company** → type the company name
4. Apollo will show all contacts it has at that company with their titles, emails, LinkedIn URLs

> **Tip:** Apollo has a lot of records — always filter by title/seniority to narrow down relevant contacts (see below).

---

### 🟢 EASY: Check how many contacts Apollo has at a member company

1. In Apollo → **People** search
2. Filter: **Company** = [Company Name]
3. The result count at the top tells you how many records Apollo has
4. You can also filter by **Title Keywords** (e.g., "marketing") to see relevant contacts only

---

### 🟡 MEDIUM: Find marketing contacts at active member companies

This is the most common Apollo task Aaron does — finding new marketers at member companies to add to the database.

**Step 1 — Set up People filters:**
1. Go to Apollo → **Search** → **People**
2. Filter: **Job Title** → Keywords: `marketing` OR `chief marketing` OR `brand` OR `media`
3. Filter: **Seniority** → Select: VP, Director, C-Suite (or whatever level is needed)
4. Filter: **Company** → This is where it gets tricky — see Step 2

**Step 2 — Filter to active member companies:**

*Option A — Type companies manually (small lists):*
- In the **Company** filter, type each member company name one by one
- Use this when you have a short list (< 10 companies)

*Option B — Import a company list (larger batches):*
- Export the list of active member companies from Salesforce first (Account Name + Website Domain)
- In Apollo → go to **Lists** → **Companies**
- Upload the company list as a CSV
- Then in People search, filter: **Company Lists** → select your uploaded list
- This lets Apollo match contacts against your specific company universe

**Step 3 — Review results:**
- Look through the results — Apollo isn't always accurate
- Verify titles look real (not outdated data)
- Check email quality indicator (Apollo shows confidence scores)

**Step 4 — Export or save:**
- Click **Select All** → **Export to CSV** (uses credits)
- Or click **Save to List** to create an Apollo list without using credits yet

---

### 🟡 MEDIUM: Find contacts at member companies that are NOT yet in Salesforce

Aaron cross-references Apollo against SF to find net-new contacts.

1. Export your Apollo contact list (see above)
2. Export your existing SF contacts (active member accounts) as a CSV
3. In Excel, use VLOOKUP or conditional formatting to find emails in Apollo that don't exist in the SF export
4. The non-matching rows = net-new contacts to potentially add to SF

> **Note:** Aaron typically does this with a Python script for large batches. For small lists (< 50 people), manual VLOOKUP in Excel is fine.

---

### 🟡 MEDIUM: Enrich an existing contact in Apollo (fill in missing data)

When a contact in Salesforce is missing a title, LinkedIn URL, or email:

1. In Apollo → **Search** → **People**
2. Search by their name + company
3. Find their record — click to open
4. Copy the information you need (Title, LinkedIn URL, verified email)
5. Go back to Salesforce and update the contact manually

> **For bulk enrichment (100+ contacts):** Aaron uses a Python script (`apollo_event_sync.py`). Hold for Aaron for large batches.

---

### 🟡 MEDIUM: Look up contacts filtered by Salesforce field values (e.g., member companies)

The most powerful use of Apollo is filtering by your own SF data. Here's how to do it manually without a script:

**Scenario:** You want Apollo contacts at all Active-Parent/Active-Subsidiary accounts.

1. In Salesforce → **Reports** → build a report: Accounts where Status = Active-Parent OR Active-Subsidiary AND Region = NA or Global
2. Export as CSV — grab the **Company Name** and **Website** columns
3. In Apollo → **Lists** → **Companies** → upload your CSV
4. Apollo matches companies in your list by domain/name
5. Now in **People** search → filter by **Company Lists** = your uploaded list
6. Add additional filters (Title, Seniority, Department) to refine

---

### 🟡 MEDIUM: Build a contact list for a LinkedIn custom audience

**When this comes up:** Dan or Amanda asks for a member contact export for LinkedIn advertising.

1. In Apollo, filter: Company List = Active Members (see above) + Title = Marketing titles
2. Export to CSV — make sure to include: **First Name, Last Name, Email, Company, Title, Country**
3. Also export the Company list separately with: **Company Name, Domain, LinkedIn Company Page**
4. These CSVs go directly to LinkedIn Campaign Manager → **Matched Audiences** → **Upload a List**

---

### 🟡 MEDIUM: Check Apollo credit usage

1. In Apollo, click your **profile icon** (top right) → **Settings** → **Credits & Usage**
2. You'll see how many credits have been used and how many remain
3. Monthly credit refresh: check when credits reset

> **MMA plan:** ~1.3M credits annually. 600K are earmarked for SF database enrichment. Be mindful — exporting contacts uses credits. Saving to a list is free.

---

### 🔴 HARD: Running an Apollo email campaign

Aaron has set up a warm-up domain (`mmaglobal.net`) for Apollo campaigns. Running campaigns requires:
- Properly warmed-up mailboxes (takes ~30 days)
- Sequence setup with copy approval from Amanda/Angela
- Understanding of Apollo's deliverability settings

Do not start new Apollo campaigns without Aaron. The mailboxes are in the process of warming up as of April 2026.

---

### 🔴 HARD: Bulk Apollo-to-Salesforce sync

Aaron uses `apollo_event_sync.py` and `apollo_event_sync_delta.py` to bulk-match Apollo contacts to SF records and write back enriched data. For coverage, hold this for Aaron.

---

## Tips for searching in Apollo

| Filter | What it does | When to use |
|---|---|---|
| **Job Title Keywords** | Searches title text | Use for "marketing", "CMO", "brand" |
| **Seniority** | C-Suite, VP, Director, Manager, etc. | Use to control who you target |
| **Department** | Marketing, Sales, Finance, etc. | Note: only 20% of Apollo DB has this — less reliable |
| **Company** | Specific company names | For targeted lookups |
| **Company Lists** | Your uploaded company CSV | For member company filtering |
| **Location** | Country, state, city | Use when you need North America only |
| **Email Status** | Verified, likely valid, etc. | Higher = more reliable email |
| **Keywords** | Any text in their profile | Broad search — use carefully |

---

## Apollo vs. Salesforce — what's in each

| Apollo has | Salesforce has |
|---|---|
| Broad contact database (millions of records) | MMA's curated member database |
| Email confidence scores | Verified opt-out and mailable status |
| LinkedIn URLs | Campaign history, event attendance |
| Department/seniority filters | Contact type, board status |
| Company employee counts | Account membership status |
| Job change signals | Relationship history |

Use **Apollo to find contacts** → use **Salesforce to verify they're actually a member and not already in the database**.
