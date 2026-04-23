# POSSIBLE 2026 Registration Management

POSSIBLE is MMA's flagship annual conference. Aaron manages the process of:
- Verifying which registrants are members vs. non-members
- Keeping the SF campaign up to date as new people register
- Handling registrant data questions from the team

**Campaign in Salesforce:** POSSIBLE 2026_registration  
**Registration file:** Managed by Leah; password is `PossiBle2025!?`

---

## Tasks

### 🟢 EASY: Check if a specific person is registered for POSSIBLE

**When this comes up:** Someone on the team asks "Is [name] registered?"

1. Go to **Salesforce** → search the person's name or email in the top search bar
2. Open their **Contact** record
3. Scroll down to the **Campaign History** section (or click the "Campaign History" related list)
4. Look for **POSSIBLE 2026_registration** in the list
5. Their **Status** column will say: `Registered` (they're in) or it won't appear at all (not registered)

> **Can't find them?** Also search under **Leads** — some people may be leads, not contacts.

---

### 🟢 EASY: Check how many members are registered (campaign count)

1. Go to **Salesforce** → search for `POSSIBLE 2026_registration` in the search bar
2. Click on the **Campaign** record
3. The **Campaign Statistics** section shows total members, responded, etc.
4. For a breakdown, click **View Campaign Members** to see the full list with statuses

---

### 🟢 EASY: Look up whether a registrant's company is an active member

**When this comes up:** Someone asks if Company X is a member.

1. Go to **Salesforce** → search the company name
2. Open the **Account** record
3. Look at the **Status** field:
   - `Active-Parent`, `Active-Subsidiary`, or `Active-Local Council` = they are a member ✅
   - `Inactive/Cancelled` or `Non-Member` = they are not a current member ❌
4. Also check **X2026_Dues_Charged__c** — if this is $0 and status is Inactive, they are definitely not active

---

### 🟡 MEDIUM: Someone registered but their status shows "Invited" — should be "Registered"

**When this comes up:** A registrant's campaign status is "Invited" but they've confirmed.

1. Go to **Salesforce** → find the campaign **POSSIBLE 2026_registration**
2. Click **View Campaign Members**
3. Find the person → click into their **Campaign Member** record
4. Change **Status** from `Invited` to `Registered`
5. Save

---

### 🟡 MEDIUM: Erin Disney or Amanda asks for a list of member company contacts not yet registered

This requires building a Salesforce report. See [Salesforce Data Management → Building a Report](../04-salesforce-data/README.md#building-a-report).

- Report type: **Contacts with Campaign History**
- Filter: Account Status = Active-Parent or Active-Subsidiary or Active-Local Council
- Filter: NOT in campaign POSSIBLE 2026_registration

If you can't build it from scratch, ask Erin Disney — she's done this kind of report before.

---

### 🔴 HARD: Bulk importing new registrants into Salesforce campaign

**Normally done by:** Aaron using a Python script  
**Do not attempt manually for large batches (50+ people)**

Aaron's process:
1. Reads the registration file ("for salesforce" tab)
2. Matches each person to their SF contact by email (checks 4 email fields) or name
3. Adds matched people to the campaign as "Registered"
4. Creates new SF contacts for people not in SF

**For coverage:** If a new wave of registrants comes in and Aaron is unreachable, do this:
1. Open the Excel registration file (ask Leah or Angela for the current version)
2. Identify which people marked "Y" in the Member column are **not yet** in the SF campaign
3. For people already in SF: manually add them to the campaign (see below)
4. For people **not** in SF: flag them in a list and hold — do not create contacts without verifying the company is an active SF account

**Manually adding one person to a SF campaign:**
1. Open their Contact record in Salesforce
2. Click the **Campaign History** related list
3. Click **Add to Campaign**
4. Search for `POSSIBLE 2026_registration`
5. Set Status = `Registered`
6. Save

> **Note:** For batches larger than ~10 people, this is very time-consuming manually. It's okay to hold and wait for Aaron to return if it's not urgent.
