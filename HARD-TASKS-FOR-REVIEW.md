# Hard Tasks — Hold for Aaron

These tasks require Python scripts or deep system knowledge and are **not feasible for coverage staff to take over**. They are listed here so Aaron can decide whether to run them before leaving or defer them entirely.

---

## 1. Apollo Enrichment / SF Contact Enhancement

**Frequency:** Ad hoc (when a new wave of contacts is added or Angela requests enrichment)  
**What it does:** Sends contact records to Apollo → gets back updated titles, LinkedIn URLs, emails → writes back to SF  
**Scripts:** `apollo_event_sync.py`, `apollo_event_sync_delta.py`  
**Defer — low urgency. Apollo enrichment can wait 2 weeks without major impact.**

---

## 2. Outreach Sequence Bulk Enrollment

**Frequency:** At the start of each campaign wave (e.g., CCS invites, POSSIBLE session comms)  
**What it does:** Takes a list of contacts from SF and bulk-enrolls them into an Outreach sequence  
**Script:** `add_prospects_to_sequence.py`  
**Amanda Hyland can manually enroll small batches in Outreach. For large batches (100+), defer to Aaron's return.**

---

## 3. Kargo Campaign Report

**Frequency:** Ad hoc (when Kargo sends raw impression/delivery data)  
**What it does:** Processes Kargo raw data files → produces formatted Excel report with campaign performance metrics  
**Script:** `update_kargo_report.py`  
**Defer. Check with Angela if any Kargo reports are expected in the next 2 weeks.**

---

## 4. CCS Invitation Cleanup / Reporting

**Frequency:** Periodic, ahead of CCS (CMO & CEO Summit)  
**What it does:** Pulls data on which member companies have been invited, who has RSVP'd, which members haven't been touched  
**Scripts:** `ccs_invitation_cleanup.py`, `ccs_outreach_to_sf_campaign.py`  
**Amanda Hyland and Andrew Somer can track manually in SF reports. Aaron should generate the latest CCS report before leaving.**

---

## 5. Pardot Duplicate Cleanup

**Frequency:** Periodic  
**What it does:** Identifies and resolves duplicate Prospect records in Pardot  
**Script:** `cleanup_pardot_duplicates.py`  
**Defer 2 weeks — minor data quality issue.**
