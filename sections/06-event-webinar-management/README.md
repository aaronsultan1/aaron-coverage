# Event & Webinar Management

MMA runs regular webinars (Decoding AI for Marketers, DAMit, etc.) and events (POSSIBLE, CMO & CEO Summit). Aaron manages the Salesforce side — creating campaigns, importing attendees, and keeping data clean.

**Registration platform:** Stova (formerly Eventscloud)  
**Stova URL:** https://na-admin.eventscloud.com  
**Stova login:** Username is typically `firstname.lastname` format

**Key people:**
- **Dan Whiting** — oversees DAMit and webinar content
- **Erin Disney** — handles event logistics and registration tracking

---

## Tasks

### 🟢 EASY: Pull a list of webinar registrants from Stova

1. Log in to **Stova**: https://na-admin.eventscloud.com
2. Navigate to the relevant event (search by event name)
3. Click **Reports** or **Registrants**
4. Export the attendee list as CSV/Excel
5. The export includes: name, email, company, registration date, attendance status

---

### 🟢 EASY: Check if someone registered for a webinar (in SF)

Aaron creates a Salesforce Campaign for each webinar. To check:
1. In SF, search for the **Campaign** by webinar name
2. Open the campaign → click **View Campaign Members**
3. Search for the person's name or email

---

### 🟢 EASY: Check upcoming webinar schedule

1. Go to the **Webinar Calendar** on Sharepoint: https://mmaglobalcom.sharepoint.com/sites/Webinars
2. Or ask Dan Whiting — he tracks the calendar in an Excel file
3. MMA's public webinar page: https://mmaglobal.com/webinars

---

### 🟡 MEDIUM: Add webinar attendees to a Salesforce campaign (small batch)

**When this comes up:** After a webinar, Dan asks for attendees to be added to the SF campaign.

For a small batch (< 20 people):
1. Export attendee list from Stova (CSV)
2. For each person, search them in SF
3. Open their Contact record → Campaign History → **Add to Campaign**
4. Select the correct campaign → set Status = `Attended`
5. Save

> For people not found in SF (they might be Leads or not exist), check under Leads too. If truly not in SF, create a Contact (see [Salesforce Data → Create Contact](../04-salesforce-data/README.md#medium-create-a-new-contact-in-salesforce)).

---

### 🟡 MEDIUM: Create a Salesforce campaign for a new webinar

1. In SF, go to **Campaigns** (in the app launcher or top nav)
2. Click **New**
3. Fill in:
   - Campaign Name (e.g., "Decoding AI for Marketers - May 2026")
   - Type = Webinar
   - Status = Planned (change to Active when it goes live)
   - Start Date / End Date
4. Save

---

### 🔴 HARD: Bulk import of 100+ webinar attendees to Salesforce

Aaron uses Python for this (`add_campaign_members.py`). For coverage:
- If Dan needs this urgently, consider using Salesforce's built-in **Data Import Wizard**:
  - Go to Setup → Data Import Wizard
  - Choose "Campaign Members"
  - Upload a CSV with Contact Email + Campaign Name
  - Map fields and import
- **Warning:** The import wizard requires exact email matches. Anyone not found will be skipped. You'll need to handle non-matches manually.

---

### 🔴 HARD: Creating SF campaigns + Pardot lists + form handlers for POSSIBLE sessions

At the start of each POSSIBLE cycle, Aaron uses a Python script (`create_possible_2026_campaigns.py`) to create:
- A Salesforce Campaign for each of the 9 POSSIBLE sessions
- A matching Pardot list
- A Pardot form handler for each session

For coverage: these should already be created for POSSIBLE 2026. If a new session is added, hold for Aaron.
