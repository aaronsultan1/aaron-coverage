# Platform Access Management

Aaron is the admin for Salesforce, Pardot, and Outreach. When someone needs access to one of these platforms, they ask Aaron to set them up.

---

## Tasks

### 🟢 EASY: Grant Salesforce access to a new user

1. In Salesforce, click the **gear icon** (top right) → **Setup**
2. In the left search bar, type **Users**
3. Click **Users** → **New User**
4. Fill in:
   - First Name, Last Name
   - Email (this becomes their username)
   - Username (usually email address)
   - Role — ask Angela/Shauna what role to assign
   - Profile — ask Angela what profile (usually "Standard User" or a custom MMA profile)
5. Click **Save**
6. SF will send them an activation email

> **Tip:** New users can't log in until they set their password from the activation email. If they don't get it, check spam, then use **Reset Password** in SF Setup.

---

### 🟢 EASY: Resend a Salesforce activation email

1. Go to **Setup** → **Users**
2. Find the user
3. Click **Reset Password** — this sends them a new email to set their password

---

### 🟢 EASY: Grant Pardot access

Pardot uses the same login as Salesforce (single sign-on). If someone can log into Salesforce, they may also need to be added to Pardot separately:

1. In **Pardot**, go to **Admin** → **User Management** → **Users**
2. Click **+ Add User**
3. Enter their email (must match SF email exactly)
4. Set their Role (usually "Marketing" for regular users)
5. Save — they'll get an email

---

### 🟡 MEDIUM: Set up an Outreach account for a new user

Outreach is a separate platform with separate billing.

1. Go to **Outreach**: https://app.outreach.io
2. Click your profile icon → **Settings** → **Users**
3. Click **Invite User**
4. Enter their email
5. Assign a role (Sales Rep, Admin, etc.) — ask Angela what level
6. Send invite

> **Note:** Outreach seats cost money. Check with Angela before adding new users.

---

### 🟡 MEDIUM: Set up a Stova (Eventscloud) account

1. Go to **Stova**: https://na-admin.eventscloud.com
2. Log in as admin
3. Go to **Admin Settings** → **Users**
4. Create a new user with their email
5. Send the welcome email (Stova requires this to be sent **manually** — it doesn't auto-send)

> **Common issue:** New users don't receive the invite. Try resending the password reset email manually from within Stova. If that fails, have them contact Aaron.

---

### 🔴 HARD: Setting up Pardot automation (flows, engagement programs)

This requires deep Pardot knowledge. Do not attempt to create or modify automation rules. Flag to Aaron.

---

## Troubleshooting common access issues

| Problem | What to check |
|---|---|
| User not getting SF activation email | Check spam; use Reset Password in SF Setup |
| User logged into SF but can't access Pardot | They may need to be added in Pardot User Management separately |
| User can log into Pardot but sees nothing | Their Pardot role may be too restricted — ask Angela what level they need |
| Outreach: user can't find their sequence | Check they're assigned to the correct team in Outreach settings |
| Stova: user never got setup email | Resend password reset manually from Stova admin panel |
