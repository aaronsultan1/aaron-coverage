# New Member Onboarding

When a company becomes a new MMA member, Aaron handles the Salesforce and Outreach setup so they can receive member communications. Shauna Peck handles the business/contract side — Aaron is notified when a new member is confirmed.

---

## Tasks

### 🟢 EASY: Verify a new member account exists in Salesforce

1. Search the company name in SF
2. Open the Account record
3. Confirm **Status** is `Active-Parent` or `Active-Subsidiary`
4. If the account is still `Non-Member` or `Inactive`, Shauna may need to update it first

---

### 🟡 MEDIUM: Create a new contact for a new member

**Only after confirming the SF Account exists and is Active.**

1. Open the Account record in SF
2. Scroll to **Contacts** → click **New Contact**
3. Fill in:
   - First Name, Last Name
   - Email
   - Title / Job Function
   - Account = their company (should auto-fill)
4. Save

> **Key contacts to create:** The primary marketing contact (usually CMO or VP Marketing level). Andrew Somer may give you the name to add.

---

### 🟡 MEDIUM: Add a new member to CCS/CATS/CARS invite lists

These are the outreach lists managed in Outreach for CMO event invitations. Andrew Somer typically requests these adds.

**CCS = CMO & CEO Summit  
CATS = C-level Advertiser Targeting Strategy  
CARS = C-level Advertiser Relationship Strategy**

1. Find the person in **Outreach** (or create them as a Prospect if needed)
2. Add them to the appropriate Outreach sequence
3. Also update the master invite Excel file on Sharepoint (ask Amanda for the file location)

---

### 🟡 MEDIUM: Add a new member contact to Pardot member lists

After creating the SF contact, they should start receiving member emails. Pardot **dynamic lists** update automatically from Salesforce — so if the Account Status is Active and the contact record is created correctly, they'll appear in dynamic lists on their own.

**To verify:**
1. Wait a few minutes for Pardot to sync with SF (usually < 10 minutes)
2. In Pardot, go to the main member list (e.g., "NA/Global Active Member Contacts")
3. Search for the new contact — they should appear

If they don't appear after 30 minutes, check:
- Is their Account Status = Active?
- Is the Contact's Region field set to NA or Global?
- Is their email valid (no typos)?

---

### 🔴 HARD: Bulk new member contact import (multiple people from one company)

If a new member company sends a list of 20+ contacts to add, hold for Aaron. He uses Python to validate, deduplicate, and import cleanly.

---

### 🔴 HARD: Apollo enrichment for new member contacts

Aaron uses Apollo to enrich contact data (fill in titles, LinkedIn URLs, etc.) after creating new contacts. This is done via Python script (`apollo_event_sync.py`). Hold for Aaron.

---

## CCS / CATS / CARS — what they are

These are Aaron's terms for different tiers of CMO outreach. For POSSIBLE 2026 coverage, the most important thing is:

- **If Andrew Somer asks you to add a specific CMO to "CCS invite list"**: add them to the Outreach CCS sequence (see [Outreach Sequences → Add one person](../03-outreach-sequences/README.md))
- **If Andrew Somer asks you to add them to SF**: create the contact under their company account (see above)
- Always confirm with Andrew if the person is a current CMO/C-level before adding — these are invitation-only lists
