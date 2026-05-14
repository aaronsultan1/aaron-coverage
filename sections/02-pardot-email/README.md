# Pardot — List Management

MMA uses **Pardot** (also called "Marketing Cloud Account Engagement") for marketing emails. **Aaron's primary job in Pardot is building the lists.** The actual email sending is handled by **Jason Chase**.

**Pardot URL:** https://pi.pardot.com
**Login:** Same as Salesforce (single sign-on via your MMA email)

**Key people:**
- **Jason Chase** — schedules and sends all Pardot emails; he needs a list name from Aaron
- **Amanda Hyland** — drives what emails go out and when; she'll tell you what audience is needed

---

## How the workflow works

1. Amanda (or Jason) asks for a list for an upcoming email
2. You build a **Prospect List** in Pardot with the right contacts
3. You give Jason the **list name** (copy/paste it exactly)
4. Jason creates the email in Pardot, applies suppression lists, and sends
5. Done — you don't send anything directly

**Jason always applies these suppressions on his end — you don't need to worry about them:**
- Board of Directors
- People who already RSVP'd (for event emails)
- Recent survey completers (for survey emails)

---

## What types of lists Aaron manages

- **Member invite lists** — active member contacts filtered by region, role, or segment (e.g., "All NA Member CMOs")
- **Event invitation lists** — contacts invited to CATS, CCS, CARS, POSSIBLE, webinars
- **Suppression lists** — people to *exclude* from a send (e.g., already registered, already replied)
- **Survey lists** — members to receive a satisfaction survey, filtered to exclude recent completers

---

## Tasks

### 🟢 EASY: Find an existing Pardot list

1. Go to **Pardot** (https://pi.pardot.com)
2. In the left nav, click **Lists** → **Prospect Lists**
3. Use the search bar at the top to find the list by name
4. Click into the list to see the prospect count and member details

> **Tip:** Aaron names lists clearly — e.g., "CCS 2026 - Member Invite List - Round 1" or "POSSIBLE 2026 - Registered Members." Search a keyword from the event name.

---

### 🟢 EASY: Check if a specific person is in a Pardot list

1. In Pardot, go to **Prospects** in the left nav
2. Search by the person's email address
3. Open their **Prospect record**
4. Click the **Lists** tab — you'll see every list they're currently on
5. Also check their **Mailable** status (top of their record) — see below

---

### 🟢 EASY: Check someone's mailable status

Every Pardot prospect has a mailable status. This affects whether Pardot will send to them.

1. Find the person in Pardot (search by email under **Prospects**)
2. Open their record — the status shows near the top: **Mailable** or **Unmailable**
3. If **Unmailable**, click **View Reasons** to see why:
   - **Opted out** — they clicked Unsubscribe
   - **Hard bounce** — their email address permanently bounced
   - **Admin do not email** — manually flagged

> **Important:** If you're unsure about someone's mailable status and whether they can still be reached, ask Amanda — she'll know.

---

### 🟡 MEDIUM: Build a Pardot list from a Salesforce export (static list)

**Use this when:** You have a specific one-time audience — e.g., "everyone who registered for CATS May" — and the list won't change after you build it.

**Step 1 — Export the list from Salesforce**
1. Go to Salesforce → **Reports**
2. Find or build the report with the right contacts (see [Salesforce — Find & Pull Data](../04-salesforce-data/README.md#build-a-report-or-run-a-list-view) for how)
3. Run the report → click **Export** → choose **Excel** or **CSV** (Formatted)
4. Make sure the export includes at minimum: **Email**, **First Name**, **Last Name**

**Step 2 — Create the static list in Pardot**
1. In Pardot, go to **Lists** → **Prospect Lists** → click **+ Add List**
2. Give it a clear name (e.g., "CATS May 2026 - Invite Round 2 - [date]")
3. Select **Static List** (not dynamic)
4. Click **Save**

**Step 3 — Import the contacts into the list**
1. Open the list you just created
2. Click **Import**
3. Upload the CSV from Salesforce
4. On the field mapping screen, map:
   - **Email** → Email (required)
   - **First Name** → First Name
   - **Last Name** → Last Name
   - Leave other fields unmapped unless you have a specific reason
5. Click **Import**

**Step 4 — Verify the list**
1. Wait a minute for the import to process, then refresh
2. Check the prospect count — does it match roughly what you expected?
3. Click into a few names to spot-check they look right
4. Once it looks good, send the list name to Jason

> **Naming convention:** Always include the event/program name, round number if relevant, and month/year. Makes it easy for Jason to find the right one.

---

### 🟡 MEDIUM: Build a dynamic Pardot list (auto-updating)

**Use this when:** The audience should update automatically over time — e.g., "all active NA members" for an ongoing program.

1. In Pardot, go to **Lists** → **Prospect Lists** → **+ Add List**
2. Name it clearly
3. Select **Dynamic List**
4. Click **Save**, then click into the list to set the **Match Rules**
5. Add rules. Common combinations Aaron uses:

   **For all active NA members:**
   - CRM Account Field: `Account Status` **contains** `Active`
   - CRM Account Field: `Region` **contains** `NA`

   **For member CMOs only:**
   - Add the above, plus:
   - Prospect Field: `Job Title` **contains** `CMO` (or Chief Marketing)

   **For a specific event's registrants:**
   - CRM Campaign Member: `Campaign Name` **equals** [campaign name] AND `Status` **equals** `Registered`

6. Save the rules — Pardot will auto-populate the list and keep it updated
7. Check the prospect count after a few minutes to sanity-check

> **Dynamic vs. Static:** If the email goes out once and the list is done, use Static. If the list needs to reflect who's currently a member at send time, use Dynamic.

---

### 🟡 MEDIUM: Add people to a suppression list

Suppression lists work exactly like regular lists — you add people to them, and Jason applies them at send time to exclude those people from the email.

**When you'd do this:** Jason or Amanda asks you to update a suppression list — e.g., add everyone who already responded to a survey, or add people who already RSVP'd to an event.

1. Get the list of people to suppress — usually from a Salesforce report or export from SurveyMonkey
2. Export as CSV, make sure it includes **Email** column
3. In Pardot, find the suppression list by name (Jason can tell you which one to use)
4. Click **Import** → upload the CSV → map Email → Import
5. Let Jason know it's updated

---

### 🟡 MEDIUM: Check the stats on a Pardot list after a send

After an email goes out, you may get asked how many people were on the list or what the open/click rate was. Jason handles the actual send stats, but you can check list counts:

1. In Pardot → **Lists** → find the list
2. The list overview shows the **prospect count** at the time of the last update
3. For open/click/bounce stats, ask **Jason Chase** — he has the send report

---

