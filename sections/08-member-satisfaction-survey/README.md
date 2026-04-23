# Member Satisfaction Survey

MMA runs an annual Member Satisfaction Survey through **SurveyMonkey**. Aaron helps Kayte Hamilton build the Pardot lists used to send the survey and follow-up emails.

**Key person:** Kayte Hamilton — she owns the survey, content, and timing  
**Email sends:** Jason Chase (Reach Marketing) sends the actual emails from Pardot

---

## Background

The survey goes to multiple audiences, typically split into 3 lists:
- **Must Respond** — board members, key accounts, high-priority contacts
- **Engaged** — contacts who have opened/engaged with recent MMA emails
- **Other** — remaining active member contacts

Each list is sent a version of the survey email on a specific day. Kayte manages the timing and which list goes out first.

There is also a regional split: some contacts go through **MMA (Pardot)**, others go through **Reach Marketing** (because they're unmailable in Pardot).

---

## Tasks

### 🟢 EASY: Check survey response counts in SurveyMonkey

1. Go to **SurveyMonkey** and log in
2. Find the survey (Kayte can share the link)
3. Click **Analyze** → see total responses, completion rate, etc.

---

### 🟢 EASY: Export partial/complete responders from SurveyMonkey

1. In SurveyMonkey, click **Analyze** → **Export**
2. Choose **All Responses** or filter by completion status (Complete / Partial)
3. Export as CSV or Excel
4. This CSV is used to build suppression lists in Pardot

---

### 🟡 MEDIUM: Build a suppression list for the survey follow-up email

When Kayte asks for a suppression list update:
1. Export **complete responders** from SurveyMonkey (see above)
2. The CSV should have at minimum: email address
3. In Pardot, find the survey suppression list (Kayte or Jason can tell you which one)
4. Click **Import** on the list → upload the CSV → map the email column
5. Pardot will add everyone in the CSV to the suppression list
6. Let Jason know the suppression list is updated before he sends

---

### 🟡 MEDIUM: Build a Pardot list for partial responders

When Kayte asks for a follow-up email to go to people who started but didn't finish:
1. Export **partial responders** from SurveyMonkey (filter: Status = Partial)
2. Clean the CSV — remove anyone who has since completed (cross-reference against completes)
3. In Pardot, create a new static list: "Member Satisfaction Survey 2026 - Partials Follow-up"
4. Import the CSV
5. Give Jason the list name to use for the send

---

### 🔴 HARD: Building the initial survey send lists (Must Respond, Engaged, Other)

Aaron uses Python plus Salesforce SOQL queries and Pardot API to build these segmented lists. This requires access to multiple systems and involves deduplication logic across all three lists.

For coverage: if Kayte asks for the initial list build and Aaron is unavailable, she can ask Dan Whiting for help — he has Claude access and has worked with this data before.

---

## Key things to remember for survey

- **Ecosystem field is important** — one of the cross-tabs in the year-over-year report is by Primary Ecosystem (Marketer, Agency, Seller, Enabler). Make sure any contacts imported have their Ecosystem filled in.
- **Do NOT include non-member contacts** in survey lists
- **Regional split matters** — NA + Global contacts go in the Pardot send; regional teams (LATAM, EMEA, APAC) handle their own regions
- **Partial responders** get a different follow-up email — Kayte will brief on timing
