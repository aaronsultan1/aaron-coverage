# Salesforce Data Management

Salesforce is the central CRM for MMA. Aaron manages data quality, imports, and reporting. This section covers the most common manual tasks.

**URL:** https://mmaglobal.lightning.force.com  
**Login:** Your MMA email + Salesforce password

---

## Key concepts

- **Account** = a company (e.g., Procter & Gamble)
- **Contact** = a person at that company
- **Lead** = someone who hasn't been matched/converted to a Contact yet
- **Campaign** = a list of contacts associated with an event, email, or program
- **Account Status values:** `Active-Parent`, `Active-Subsidiary`, `Active-Local Council` = member; `Inactive/Cancelled`, `Non-Member` = not a current member
- **Protected contacts** = board members, B2B CMO Council, MFC — never edit their contact fields; only Jade/Angela touch these

---

## Tasks

### 🟢 EASY: Look up a contact in Salesforce

1. Click the **search bar** at the top of any SF page
2. Type the person's name or email address
3. SF will show matching Contacts and Leads
4. Click the Contact record to open it

> **Can't find them?** Try searching just their last name, or search by email. Also check if they might be a **Lead** (not yet a Contact).

---

### 🟢 EASY: Check if a contact is a protected/board member

1. Open their Contact record
2. Look for any of these fields being checked:
   - `Is Board Member` = checked
   - `Contact Type 1` = has a value
   - `Committee Member` = checked
   - `Current B2B CMO Council Member` = checked
   - `Current MM25 Board Member` = checked
3. If any of these are set → **do not edit their contact record.** Flag to Jade or Angela.

---

### 🟢 EASY: Check a contact's email opt-out status

1. Open the Contact record
2. Look for **Email Opt Out** — if checked, they've opted out of marketing emails
3. Also check **Pardot Do Not Email** — older field
4. **Note:** Opted-out people can still be emailed by Reach Marketing through their own domain — ask Amanda about the Reach workaround if needed

---

### 🟢 EASY: Check a contact's email fields (there are 4)

SF stores up to 4 emails per contact. When looking for someone by email, check all 4:
1. **Email** — primary email
2. **Secondary Email** (`Secondary_Email__c`) — second work email
3. **Personal Email** (`Personal_Email_Address__c`) — personal/alternate
4. **MediaRadar Verified Email** (`MediaRadar_Verified_Email__c`) — auto-enriched

---

### 🟢 EASY: Check an account's membership status

1. Search the company name in SF
2. Open the **Account** record
3. Check the **Status** field:
   - Active-Parent / Active-Subsidiary / Active-Local Council = ✅ member
   - Inactive/Cancelled or Non-Member = ❌ not active
4. Also check **X2026 Dues Charged** — $0 + Inactive = definitely not active

---

### 🟡 MEDIUM: Update a contact's title (when SF title is blank)

1. Open the Contact record
2. Click **Edit** (pencil icon at top)
3. Find the **Title** field and fill it in
4. Click **Save**

> Only do this if the title field is completely blank. Don't overwrite an existing title.

---

### 🟡 MEDIUM: Add a second email to a contact (Secondary Email field)

1. Open the Contact record
2. Click **Edit**
3. Find **Secondary Email** (`Secondary_Email__c`) — scroll down if needed
4. Add the new email
5. Save

---

### 🟡 MEDIUM: Check for duplicate contacts

If you suspect two contacts are the same person:
1. Search by name in SF
2. Check both records — compare email, company, LinkedIn URL
3. Go to the person's LinkedIn to confirm they're the same person
4. **Do not merge board member records** — flag to Jade
5. For non-board contacts, use SF's built-in merge:
   - On a Contact record, click the dropdown arrow next to "Edit" → **Merge**
   - Select the records to merge
   - Choose which record is the "master" (keep the one with the most complete data)
   - Confirm

---

### 🟡 MEDIUM: Create a new contact in Salesforce

**Only do this for confirmed active member companies. Never create a contact without an Account.**

1. First, find the Account (company) and confirm it's Active in SF
2. On the Account record, scroll to **Contacts** related list → click **New Contact**
3. Fill in: First Name, Last Name, Email, Title
4. Save

> If you can't find an active SF account for the company, **do not create the contact.** Flag it for Aaron.

---

### 🟡 MEDIUM: Build a Salesforce report

1. Go to **Reports** in the top nav
2. Click **New Report**
3. Select a report type (e.g., "Contacts," "Contacts with Campaign Members," "Accounts")
4. Add filters as needed (e.g., Account Status = Active-Parent)
5. Choose columns to display
6. Click **Run**
7. Click **Export** if you need a CSV/Excel version

> **Tip:** Look at existing reports first — someone may have already built what you need. Search the report name in the Reports tab.

---

### 🟡 MEDIUM: Check DAM (Decoding AI for Marketers) certificate status for a contact

Aaron manages certificate tracking in Salesforce. Certificates are now series-based (DAM Certificate 7, 8, 9, etc.).

1. Open the Contact record in SF
2. Look for the **DAM Certificate** fields in the contact record (scroll down)
3. At the account level, there is a rollup field showing total certificates across all contacts at that company

---

### 🟡 MEDIUM: Rename or update certificate field names in Salesforce

Aaron was tasked with renaming SF certificate fields from year-based to series-based naming (e.g., "2025 DAM Certificate" → "DAM Certificate Series 7"). This requires SF admin access.

1. Go to **Setup** → **Object Manager** → **Contact**
2. Click **Fields & Relationships**
3. Find the certificate field → click **Edit**
4. Update the **Field Label** (not API name — changing API name would break things)
5. Save

> Only do this if Aaron has specifically briefed you on which fields need renaming.

---

### 🔴 HARD: DemandTools deduplication

**DemandTools** is a Salesforce data management tool used for large-scale deduplication. It currently only runs on **Shauna's laptop** and requires training before use. Aaron is in the process of getting trained.

- **Do not attempt to use DemandTools without training**
- For contact duplicates, use Salesforce's built-in merge tool (see above)
- For large-scale dedup needs (100+ records), flag to Shauna

---

### 🔴 HARD: Bulk creating contacts from a registration file

Aaron uses Python for this. Do not attempt manually for large batches. See [POSSIBLE Registration → Hard tasks](../01-possible-registration/README.md) for guidance on when to hold vs. act.

---

### 🔴 HARD: Reverting Apollo enrichment changes

If Apollo (a data enrichment tool) overwrites contact titles/roles incorrectly, Aaron uses a Python script to revert. Do not attempt manually. Flag to Aaron urgently.

---

### 🔴 HARD: Renewal status bulk update

Aaron runs `populate_renewal_status.py` to sync renewal statuses from the Membership Business Tracker spreadsheet to SF accounts. For coverage: if someone asks for a specific account's renewal status, look it up manually in SF (field: `Renewal Status`). For a bulk update, hold for Aaron.

---

## ⚠️ Things to never do in Salesforce

- **Never delete records** — deactivate or flag instead
- **Never merge board member records** — only Jade does this
- **Never remove the Account from a Contact** — every contact must have an account
- **Never modify account Status** — that's Shauna's responsibility
