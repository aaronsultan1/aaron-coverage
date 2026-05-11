# Quick Reference — Aaron's Coverage

## "Someone asked me to..." → where to go

| Request | Where to look |
|---|---|
| "Is [company] a member?" | [SF → Check account status](sections/04-salesforce-data/README.md#easy-check-a-companys-membership-status) |
| "Can you pull a list of [event] registrants?" | [SF → Pull a campaign member list](sections/04-salesforce-data/README.md#medium-pull-a-campaign-member-list) |
| "Can you add [person] to the [event] sequence?" | [Outreach → Add one person to a sequence](sections/03-outreach-sequences/README.md#medium-add-one-person-to-an-existing-sequence) |
| "Can you make a Pardot list for [email]?" | [Pardot → Build a static list](sections/02-pardot-email/README.md#medium-build-a-pardot-list-from-a-salesforce-export-static-list) |
| "The suppression list needs updating" | [Pardot → Add to a suppression list](sections/02-pardot-email/README.md#medium-add-people-to-a-suppression-list) |
| "Can you send an invite sequence to [audience]?" | [Outreach → Full workflow](sections/03-outreach-sequences/README.md#the-full-workflow-salesforce--outreach) |
| "[Person] bounced in Outreach" | [Outreach → Remove from sequence](sections/03-outreach-sequences/README.md#medium-remove-someone-from-a-sequence-they-replied-or-asked-to-stop) |
| "I need to see who's already in Outreach from this list" | [Outreach → Fake import trick](sections/03-outreach-sequences/README.md#the-fake-import-trick--isolating-people-already-in-outreach) |
| "Export our member contact list" | [SF → Build a report](sections/04-salesforce-data/README.md#medium-build-a-report-or-run-a-list-view) |
| "Is [person] opted out of email?" | [SF → Check opt-out status](sections/04-salesforce-data/README.md#easy-check-a-contacts-email-opt-out-status) |
| "Is [person] mailable in Pardot?" | [Pardot → Check mailable status](sections/02-pardot-email/README.md#easy-check-someones-mailable-status) |
| "Can you pause the [sequence]?" | [Outreach → Pause a sequence](sections/03-outreach-sequences/README.md#easy-pause-a-sequence-emergency-stop) |

---

## Tasks by effort

### 🟢 Do it yourself

- Look up a contact or account in Salesforce
- Check if someone is in a Pardot list
- Check email opt-out / mailable status
- Find an existing Pardot list
- Check if someone is in an Outreach sequence
- Check a sequence's status and open/click stats
- Pause an Outreach sequence
- Export a Salesforce report

### 🟡 Doable with the guide

- Build a Pardot list from a Salesforce report (static or dynamic)
- Add/update a suppression list
- Add one person to an Outreach sequence
- Remove someone from an Outreach sequence
- Use the fake import trick to isolate an audience in Outreach
- Full Salesforce → Outreach workflow for a new sequence
- Build a Salesforce report or run a list view
- Pull a campaign member list from Salesforce
- Add a contact to a Salesforce campaign manually

---

## Platform logins

| Platform | URL | Login |
|---|---|---|
| Salesforce | https://mmaglobal.lightning.force.com | MMA email + SF password |
| Pardot | https://pi.pardot.com | Same as Salesforce (SSO) |
| Outreach | https://app.outreach.io | Separate MMA login |
