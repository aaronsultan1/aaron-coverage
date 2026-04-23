# Hard Tasks — Flagged for Aaron's Review

These are tasks Aaron currently handles that are **not feasible without Python scripts** or require deep system expertise. Listed here so Aaron can decide:
1. Whether to document a manual workaround
2. Whether to defer them entirely during leave
3. Whether to brief someone specific before he goes

---

## 1. POSSIBLE Registrant Bulk Import

**Frequency:** Every time a new wave of registrations comes in (every few days leading up to the event)  
**What it does:** Reads registration file → matches to SF contacts by email/name → adds to POSSIBLE 2026_registration campaign → creates new contacts for people not in SF  
**Script:** `possible2026_campaign_update.py` + the `/sf-campaign-update` Claude skill  
**Risk if skipped:** Campaign count falls behind; members don't get registered status in SF  
**Suggested coverage plan:** Erin Disney has done some SF campaign work before; she could manually add individual members if asked by Amanda. For bulk batches, Aaron should consider running this before he leaves and deferring further runs.

---

## 2. Apollo Enrichment / SF Contact Enhancement

**Frequency:** Ad hoc (when a new wave of contacts is added or Angela requests enrichment)  
**What it does:** Sends contact records to Apollo → gets back updated titles, LinkedIn URLs, emails → writes back to SF  
**Scripts:** `apollo_event_sync.py`, `apollo_event_sync_delta.py`  
**Risk if skipped:** New contacts remain missing LinkedIn URLs and may have blank titles; not urgent  
**Suggested coverage plan:** Defer. Apollo enrichment can wait 2 weeks without major impact.

---

## 3. Rasa AI Newsletter Engagement Sync

**Frequency:** Nightly (should run automatically)  
**What it does:** Syncs open/click data from the Rasa custom object to Contact-level SF fields  
**Script:** `sync_rasa_ai_newsletter.py`  
**Risk if skipped:** SF contact engagement fields fall 2 weeks behind; reports show stale data  
**Suggested coverage plan:** Confirm the cron job is active before leaving. If it stops running, ask IT or re-run manually once Aaron returns. Not customer-facing, so low urgency.

---

## 4. Renewal Status Bulk Update

**Frequency:** When the Membership Business Tracker spreadsheet is updated by Shauna  
**What it does:** Reads renewal statuses (Paid, Verbal Yes, Likely OK, etc.) from the tracker → writes `Renewal_Status__c` to SF account records  
**Script:** `populate_renewal_status.py`  
**Risk if skipped:** SF renewal status fields fall behind the tracker  
**Suggested coverage plan:** Defer 2 weeks. Shauna tracks the actual status in the spreadsheet regardless; SF is a secondary view.

---

## 5. Outreach Sequence Bulk Enrollment

**Frequency:** At the start of each campaign wave (e.g., CCS invites, POSSIBLE session comms)  
**What it does:** Takes a list of contacts from SF and bulk-enrolls them into an Outreach sequence  
**Script:** `add_prospects_to_sequence.py`  
**Risk if skipped:** Email outreach to a new wave of prospects is delayed  
**Suggested coverage plan:** Amanda Hyland can manually enroll small batches in Outreach. For large batches (100+), defer to Aaron's return. Aaron should check Outreach calendar before leaving to see if any large sends are planned during his 2 weeks.

---

## 6. Kargo Campaign Report

**Frequency:** Ad hoc (when Kargo sends raw impression/delivery data)  
**What it does:** Processes Kargo raw data files → produces formatted Excel report with campaign performance metrics  
**Script:** `update_kargo_report.py`  
**Risk if skipped:** Delayed reporting on a Kargo campaign; not urgent unless a deadline is tied to it  
**Suggested coverage plan:** Defer. Check with Angela if any Kargo reports are expected in the next 2 weeks.

---

## 7. CCS Invitation Cleanup / Reporting

**Frequency:** Periodic, ahead of CCS (CMO & CEO Summit)  
**What it does:** Pulls data on which member companies have been invited, who has RSVP'd, which members haven't been touched  
**Script:** `ccs_invitation_cleanup.py`, `ccs_outreach_to_sf_campaign.py`  
**Risk if skipped:** CCS invitation tracking falls behind; some members may not get followed up  
**Suggested coverage plan:** Amanda Hyland and Andrew Somer can track manually in SF reports. Aaron should generate the latest CCS report before leaving so the team has a current view.

---

## 8. Board Email Audit

**Frequency:** Periodic (quarterly or before large outreach waves)  
**What it does:** Checks that board member email addresses in SF are current and match LinkedIn  
**Script:** `board_email_audit.py`, `board_email_audit_v2.py`  
**Risk if skipped:** Low — board contacts are handled by Jade anyway  
**Suggested coverage plan:** Defer. Jade manages board contacts directly.

---

## 9. Pardot Duplicate Cleanup

**Frequency:** Periodic  
**What it does:** Identifies and resolves duplicate Prospect records in Pardot  
**Script:** `cleanup_pardot_duplicates.py`  
**Risk if skipped:** Low — minor data quality issue  
**Suggested coverage plan:** Defer 2 weeks.

---

## 10. Engagement Reports (Word/PDF)

**Frequency:** Ad hoc (when leadership requests a summary)  
**What it does:** Generates formatted engagement reports using SF data  
**Scripts:** `engagement_report.py`, `engagement_report_docx.py`  
**Risk if skipped:** Angela/Dan would need to request a manual export and format it themselves  
**Suggested coverage plan:** Aaron should check if any reports are expected in the next 2 weeks and either run them in advance or brief Dan Whiting on the manual alternative (SF report export + Excel pivot).
