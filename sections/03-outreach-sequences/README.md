# Outreach — Sequences

**Outreach** is MMA's email outreach platform. It's used to send sequences (a series of timed emails) to groups of contacts — primarily for event invitations and member outreach.

**URL:** https://app.outreach.io
**Login:** Separate from Salesforce — use your MMA credentials

**Key people:**
- **Amanda Hyland** — drives most sequence sends; always check with her before activating or pausing
- **Angela Gray** — runs CCS/CATS CMO outreach sequences
- **Greg Stuart** — sends personal CMO emails through Outreach

---

## Key concepts

- A **sequence** is a series of emails sent automatically over time (e.g., an invite email on Day 1, a follow-up on Day 5)
- Each person in a sequence is a **prospect**
- Sequences can be **Active** (sending) or **Paused** (stopped)
- If someone **replies**, Outreach stops sending to them automatically
- If someone **bounces**, they get flagged — remove them from future sequences
- Aaron also stores **assistants (EAs)** in Outreach linked to their executives — searching for a CMO may show their EA too

---

## The full workflow: Salesforce → Outreach

This is the end-to-end process for building a new audience and getting a sequence out.

### Step 1 — Build the list in Salesforce

1. Go to Salesforce → **Reports** (or find an existing list view under **Contacts** or **Campaigns**)
2. Build or run a report with the right audience filters (see [Salesforce — Find & Pull Data](../04-salesforce-data/README.md#build-a-report-or-run-a-list-view))
3. Make sure the report includes at minimum: **First Name**, **Last Name**, **Email**, **Title**, **Company/Account Name**
4. Click **Export** → choose **CSV** (Details Only, not formatted)
5. Save the file to your desktop

### Step 2 — Import into Outreach

1. In Outreach, click the **grid/apps icon** (top left) or go to **Prospects** in the left nav
2. Look for an **Import** button (usually top right of the Prospects view) → click it
3. Upload the CSV you exported from Salesforce
4. On the **field mapping** screen, map each column to the right Outreach field:
   - First Name → First Name
   - Last Name → Last Name
   - Email → Email *(required)*
   - Title → Title
   - Company → Account Name
5. Click **Import** to finish

> After import, Outreach shows you a summary: how many prospects were **created** (new) vs. **updated** (already existed). New people are added to Outreach; existing people's records are updated with any new field values you mapped.

### Step 3 — Add prospects to a sequence

1. In Outreach, go to **Sequences** and find the sequence you want to use
2. Click **Add Prospects** (or **Enroll**)
3. Search for the people by name or import them from the list you just created
4. Confirm enrollment — they'll start receiving emails according to the sequence schedule

### Step 4 — Activate the sequence (if it's not already active)

1. Open the sequence
2. If it shows **Paused**, click **Activate** (top right)
3. **Check with Amanda before activating** — she may want to review the prospect list or timing first

---

## The "fake import" trick — isolating people already in Outreach

**When to use this:** You have a Salesforce export and want to target only the people from that list who are *already* in Outreach — so you can add them to a sequence or work with them as a group — without changing any of their existing data.

**Why it works:** Every import in Outreach gets an ID. After the import completes, Outreach shows you the count of people it matched. That number is clickable — clicking it filters the entire Prospects page to show exactly those people. That filtered view is your working audience.

**Step-by-step:**

**1.** Export your list from Salesforce as a CSV. Needs at minimum: First Name, Last Name, Email.

**2.** In Outreach, go to the left sidebar → **System activity** → **Imports**

**3.** Click the button to start a new import. Select type: **Prospects**, upload your CSV.

**4.** Work through the **Map fields** step: map First Name, Last Name, Email, Title, Company Name as usual.

**5.** On the next screen (the overrides screen), you'll see fields for Owner, Stage, Time zone, Source, Tags:
   - **Leave Owner blank**
   - **Leave Time zone blank** — Outreach tries to default this, leave it empty
   - Leave Stage and Source blank
   - You can optionally add a **Tag** here to label this batch for easy reference later

**6.** At the bottom of that screen: **"What would you like to do with duplicates?"**
   → Select **"Skip and keep existing fields"**

   This is the key setting. It tells Outreach not to overwrite anything on records that already exist — so the import touches nothing, it just matches.

**7.** Complete the import. When it finishes, a popup shows **Successes** and **Total** counts → click **Done**.

**8.** Back on the Imports list, find your completed import. The count (e.g., **22 of 22**) is a **clickable link**.

**9.** Click that number → Outreach opens the **Prospects** page filtered to only those people. The filter bar shows something like `For batch is [ID]`. This is your isolated audience.

**10.** From here: check the checkboxes → select all → add to a sequence, apply a tag, or do whatever you need with that group.

---

## Tasks

### 🟢 EASY: Check if a specific person is in a sequence

1. Go to Outreach → **Prospects** in the left nav
2. Search by name or email
3. Click their record → scroll to the **Sequences** tab
4. You'll see which sequences they're in and their status (Active, Paused, Finished, Bounced, etc.)

---

### 🟢 EASY: Check a sequence's status and stats

1. In Outreach, go to **Sequences** in the left nav
2. Search by name or scroll to find it
3. Click into the sequence to see:
   - How many people are enrolled
   - Open/reply/bounce rates
   - Whether it's currently Active or Paused

---

### 🟢 EASY: Pause a sequence (emergency stop)

1. In Outreach → **Sequences** → find the sequence
2. Click **Pause** (top right of the sequence view)
3. Confirm — all scheduled emails stop immediately until someone resumes it

> **When to do this:** Typo in an email, a board member got in accidentally, or Amanda/Angela asks you to stop.

---

### 🟡 MEDIUM: Add one person to an existing sequence

1. In Outreach, go to the sequence you want to add them to
2. Click **Add Prospects** (or **Enroll**)
3. Search for the person by name or email
4. If they exist in Outreach: select them, confirm enrollment
5. If they don't exist yet, create them first:
   - Go to **Prospects** → **+ New Prospect**
   - Fill in: First Name, Last Name, Email, Title, Company
   - Save — then go back to the sequence and enroll them

> Before adding anyone, search their email first to confirm they're not already in the sequence.

---

### 🟡 MEDIUM: Remove someone from a sequence (they replied or asked to stop)

1. Go to **Prospects** → search for the person → open their record
2. Click the **Sequences** tab
3. Find the active sequence → click **Finish** or **Remove**
4. All further emails in that sequence stop for them

---

## ⚠️ Things to never do in Outreach

- **Don't resume a paused sequence** without checking with Amanda or Angela first
- **Don't add board member contacts to sequences** — they're managed separately by Jade/Angela
- **Don't delete sequence steps** — it breaks the sequence permanently for everyone in it
