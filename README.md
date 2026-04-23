# Aaron Sultan — Coverage Guide (Paternity Leave)

**Coverage period:** ~2 weeks  
**Note:** This guide is designed for someone who does **not** have access to Claude Code or Python scripts. All tasks described here are done directly in Salesforce, Pardot, Outreach, or other platforms via their web interfaces.

---

## Who to contact for what

| Person | Role | When to ping |
|---|---|---|
| **Angela Gray** | VP, Membership & Marketing | Strategic decisions, board contacts, anything urgent |
| **Shauna Peck** | Membership Manager | Account status in SF (Active vs. Inactive), new member paperwork |
| **Amanda Hyland** | Marketing Coordinator | Pardot email sends, Outreach sequences, POSSIBLE/CCS comms |
| **Dan Whiting** | Content/Events | Webinar attendee imports, DAMit, content-related SF lists |
| **Kayte Hamilton** | Research | Member Satisfaction Survey, survey suppression lists |
| **Jade** | Operations | Board member records — **do not touch board contacts without Jade** |
| **Jason Chase (Reach)** | Email vendor | Pardot sends — he schedules and fires all emails |
| **Erin Disney** | Membership Coordinator | SF data questions, event attendee tracking |
| **Andrew Somer** | Sales | CCS/CATS/CARS CMO invite requests |

---

## Sections

Each section covers a specific area of work. Within each section, tasks are rated:

- 🟢 **Easy** — Step-by-step screenshot guide included
- 🟡 **Medium** — Instructions included; requires some judgment
- 🔴 **Hard** — Normally done via Python script; requires escalation or manual workaround

---

### [1. POSSIBLE 2026 Registration Management](sections/01-possible-registration/README.md)
Checking if registrants are members, looking up people in Salesforce, verifying campaign status.

### [2. Pardot Email Operations](sections/02-pardot-email/README.md)
Building Pardot lists, managing suppression lists, coordinating with Jason Chase/Reach Marketing.

### [3. Outreach Sequence Management](sections/03-outreach-sequences/README.md)
Adding prospects/members to sequences, handling bounces, checking sequence status.

### [4. Salesforce Data Management](sections/04-salesforce-data/README.md)
Looking up contacts, checking opt-out status, deduplication, protected contacts, access provisioning.

### [5. Analytics & Reporting](sections/05-analytics-reporting/README.md)
Exporting SF reports, GA analytics, LinkedIn ad performance pulls.

### [6. Event & Webinar Management](sections/06-event-webinar-management/README.md)
Stova/Eventscloud access, webinar attendee lists, SF campaign enrollment.

### [7. New Member Onboarding](sections/07-member-onboarding/README.md)
Creating new SF contacts, adding to member campaigns, CCS/CATS invite lists.

### [8. Member Satisfaction Survey](sections/08-member-satisfaction-survey/README.md)
Coordinating survey lists, partial follow-ups, suppression list updates.

### [9. Platform Access Management](sections/09-access-management/README.md)
Granting Salesforce, Pardot, Outreach, and Stova access to new users.

### [10. Renewals Support](sections/10-renewals-support/README.md)
Pulling DAMit attendance, engagement data, and at-risk account summaries for weekly renewals meetings.

### [11. Apollo — Contact Database & Enrichment](sections/11-apollo-database/README.md)
Finding contacts at member companies, filtering by SF criteria, building LinkedIn audiences, enriching SF records.

### [12. HubSpot Migration (Major Upcoming Project)](sections/12-hubspot-migration/README.md)
MMA is evaluating Salesforce → HubSpot. Nothing to do yet — but coverage person needs to know this is in flight.

---

## Key platforms and login info

| Platform | URL | Notes |
|---|---|---|
| Salesforce | https://mmaglobal.lightning.force.com | Ask Angela/Shauna for login help |
| Pardot | https://pi.pardot.com | Part of Salesforce — same login |
| Outreach | https://app.outreach.io | Separate login |
| Stova (Eventscloud) | https://na-admin.eventscloud.com | Separate login |
| Google Analytics | https://analytics.google.com | MMA property |
| LinkedIn Campaign Manager | https://www.linkedin.com/campaignmanager | MMA account |
| Asana | https://app.asana.com | Task tracking |
| Sharepoint | https://mmaglobalcom.sharepoint.com | File storage |
| Apollo | https://app.apollo.io | Contact database & enrichment |
| SurveyMonkey | https://www.surveymonkey.com | Member Satisfaction Survey |

---

## ⚠️ Hard rules — do not do these

1. **Never touch board member contact records.** If something needs to change for a board member, tell Jade.
2. **Never merge contacts without verifying on LinkedIn first** that they are the same person.
3. **Never create a Salesforce contact without an Account.** Every contact must be attached to a company.
4. **Never add Inactive/Cancelled member accounts as the account for a new contact** — verify the account is Active first.
5. **Never delete anything.** If something looks wrong, flag it for Aaron or Angela.
