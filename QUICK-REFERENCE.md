# Quick Reference — Aaron's Coverage

## "Someone asked me X" → where to look

| Question | Where to go |
|---|---|
| "Is [person] registered for POSSIBLE?" | [POSSIBLE → Check if registered](sections/01-possible-registration/README.md#easy-check-if-a-specific-person-is-registered-for-possible) |
| "Is [company] a member?" | [SF Data → Check account status](sections/04-salesforce-data/README.md#easy-check-an-accounts-membership-status) |
| "Can you add [person] to the CCS invite list?" | [Outreach → Add one person to sequence](sections/03-outreach-sequences/README.md#medium-add-one-person-to-an-outreach-sequence) + [New Member → CCS/CATS/CARS](sections/07-member-onboarding/README.md#medium-add-a-new-member-to-ccscatsars-invite-lists) |
| "Can you make a Pardot list for [email]?" | [Pardot → Build a list](sections/02-pardot-email/README.md#medium-build-a-pardot-list-from-a-salesforce-report) |
| "The suppression list needs updating" | [Pardot → Suppression list](sections/02-pardot-email/README.md#medium-update-the-suppression-list-for-a-pardot-send) |
| "Can you give [person] SF access?" | [Access Management → Grant SF access](sections/09-access-management/README.md#easy-grant-salesforce-access-to-a-new-user) |
| "Pull the POSSIBLE registration numbers" | [Analytics → POSSIBLE registration count](sections/05-analytics-reporting/README.md#easy-check-possible-registration-numbers) |
| "Can you pull LinkedIn campaign performance?" | [Analytics → LinkedIn stats](sections/05-analytics-reporting/README.md#easy-pull-linkedin-campaign-performance-numbers) |
| "[Person] just joined as a new member" | [Member Onboarding](sections/07-member-onboarding/README.md) |
| "Export our member contact list" | [Analytics → Export SF report](sections/05-analytics-reporting/README.md#easy-export-a-salesforce-report-to-excelcsv) |
| "Add [webinar] attendees to SF" | [Event/Webinar → Add attendees](sections/06-event-webinar-management/README.md#medium-add-webinar-attendees-to-a-salesforce-campaign-small-batch) |
| "[Person] bounced in Outreach" | [Outreach → Remove from sequence](sections/03-outreach-sequences/README.md#medium-remove-someone-from-an-outreach-sequence) |
| "I need Pardot/Outreach/Stova access" | [Access Management](sections/09-access-management/README.md) |
| "How many DAMit attendees from [company]?" | [Renewals Support → Pull DAMit attendance](sections/10-renewals-support/README.md) |
| "Find me marketing contacts at member companies" | [Apollo → Find contacts at member companies](sections/11-apollo-database/README.md) |
| "Can you find [person] in Apollo?" | [Apollo → Search for contacts](sections/11-apollo-database/README.md) |
| "What's the status of the HubSpot migration?" | [HubSpot Migration — ask Angela Gray](sections/12-hubspot-migration/README.md) |

---

## Tasks by difficulty

### 🟢 Easy — do it yourself

- Look up a contact or account in Salesforce
- Check if someone is in a campaign or Pardot list
- Check email opt-out / mailable status
- Export a Salesforce report
- Check POSSIBLE registration count
- Pull LinkedIn campaign stats from Campaign Manager
- Grant Salesforce access to a new user
- Resend SF activation email
- Pause an Outreach sequence (emergency)
- Check webinar schedule in Stova/Sharepoint
- Export SurveyMonkey responses

### 🟡 Medium — doable with the guide

- Build a Pardot list from a Salesforce report
- Update a suppression list before a Pardot send
- Add one person to an Outreach sequence
- Remove someone from an Outreach sequence
- Manually add 1-10 people to a Salesforce campaign
- Merge non-board duplicate contacts in SF (verify on LinkedIn first)
- Update a contact's blank title
- Create a new contact in SF (under an existing Active account)
- Build a basic Salesforce report
- Add a webinar campaign to Salesforce
- Grant Pardot or Outreach access
- Build partial-responder list for survey follow-up email
- Pull GA traffic data for a campaign
- Search for contacts in Apollo by company or title
- Build a contact list in Apollo filtered to member companies
- Check credit usage in Apollo
- Pull DAMit/event attendance data for a specific company in SF
- Look up a member's engagement metrics (events attended, certificates earned)
- Check if a new member is in Apollo

### 🔴 Hard — hold for Aaron (or escalate to Angela)

- Bulk import of 50+ registrants into POSSIBLE campaign
- Any bulk Salesforce data import/update
- Apollo enrichment sync
- Rasa AI Newsletter engagement sync
- Kargo campaign report analysis
- Renewal status bulk update
- Outreach bulk sequence adds (100+ people)
- Creating Pardot/SF campaigns for new POSSIBLE sessions
- Reverting Apollo enrichment (wrong data overwrites)
- Building initial Member Satisfaction Survey send lists
- Fixing rogue Outreach resend issues
- Cleaning Pardot duplicate prospects

---

## Escalation path

1. **Try the guide first**
2. **Ask Erin Disney** — for SF/data questions
3. **Ask Amanda Hyland** — for Pardot/Outreach/email questions
4. **Ask Angela Gray** — for anything strategic or involving board contacts
5. **Text Aaron directly** — for anything urgent that can't wait

---

## Things that require Aaron's Python scripts (don't try manually)

These tasks have no manual equivalent for large batches. Put them on hold until Aaron returns:

- POSSIBLE registrant bulk import
- Apollo/Rasa/Kargo data sync
- Bulk Outreach sequence enrollment
- Renewal status propagation
- Pardot duplicate cleanup
- Engagement reports (PDF/Word)
- HubSpot migration work (hold for Aaron / Angela)
- Apollo bulk enrichment to Salesforce (script-based)
- Apollo email campaign setup (mailboxes still warming up)
- DemandTools deduplication runs (only on Shauna's laptop, requires training)
