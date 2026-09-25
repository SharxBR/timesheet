# 💵 Hours & Money Tracker

A free, private app for tracking your work hours, income, expenses, and budget —
on your computer **and** your phone, synced automatically. No subscription, no ads,
no company holding your data.

**👉 Open the app: https:/sharxbr.github.io/timesheet/**
*(replace this link with your own once you've set up hosting — see "Host your own copy" below)*
*If you would like to make changes you must host your own copy, otherwise you are subject to any changes the owner makes.*
---

## Is my data private?

Yes — this is the whole point of the app.

- Your data (hours, income, bank expenses) is **scrambled with AES-256 encryption
  inside your own browser** before it's ever uploaded anywhere.
- It's stored in **your own private GitHub Gist** as unreadable gibberish.
- **Only your passphrase can unlock it**, and that passphrase never leaves your
  device. Not even GitHub — or the person who shared this app with you — can read
  your data.
- Everyone who uses this app has **their own separate storage**. Your data and
  theirs never mix.

> ⚠️ **The one rule:** there is **no password reset** for your data. If you forget
> your passphrase, your synced data cannot be recovered — that's what makes it
> truly private. **Write your passphrase down somewhere safe.**

---

## Set up your own private storage (about 10 minutes, one time)

You'll create two things on GitHub — a **token** (so the app can save for you) and a
**secret gist** (where your encrypted data lives) — then enter them into the app once
per device.

### Step 1 — Get a free GitHub account
If you don't already have one, sign up at **https://github.com/signup**
(just an email and password — no credit card).

### Step 2 — Create a token that can ONLY touch gists
This is a key that lets the app save your data. We lock it down so it can do nothing
else on your account.

1. Go to **https://github.com/settings/personal-access-tokens/new**
   *(this is Settings → Developer settings → Fine-grained tokens → Generate new token)*
2. **Token name:** `timesheet-sync`
3. **Expiration:** pick anything (1 year is fine). When it expires you just make a new
   one — your data isn't affected.
4. **Repository access:** leave it on the default **Public Repositories (read-only)**.
5. **Account permissions:** scroll down, find **Gists**, and set it to
   **Read and write**. Leave everything else on **No access**.
6. Click **Generate token** at the bottom, then **copy** the value that starts with
   `github_pat_...`. GitHub only shows it once — paste it somewhere for a moment.

### Step 3 — Create a secret gist to hold your data
1. Go to **https://gist.github.com**
2. **Filename:** `timesheet-data.json`
3. **Content:** just type `{}` (two curly braces)
4. Click the small **dropdown arrow** next to the green button and choose
   **Create secret gist**. (Secret = not listed publicly.)
5. Look at the web address of the page you land on:
   `https://gist.github.com/your-name/`**`abc123def456...`**
   Copy that long code after your username — that's your **Gist ID**.

### Step 4 — Connect the app
1. Open the app (the link at the top of this page).
2. Click the **Sync & Devices** tab.
3. Paste in your **GitHub token** and your **Gist ID**.
4. Choose a **passphrase** and type it twice. This encrypts your data — **use the same
   passphrase on every device**, and write it down.
5. (Optional) Tick **"Remember passphrase on this device"** so you don't have to type
   it every time — good for your own phone, skip it on a shared computer.
6. Click **Connect & sync**. Done — your data now saves automatically.

---

## Add it to your phone

1. Open the app link in **Safari** (iPhone) or **Chrome** (Android).
2. Tap the browser's share/menu button and choose **Add to Home Screen**.
   It then opens like a normal app.
3. Open it, go to **Sync & Devices**, and enter the **same** token, Gist ID, and
   passphrase you used on your computer. Your data appears.

---

## How to use it day to day

- **Dashboard** — your month (or whole year) at a glance: hours, income, expenses,
  and what's left over.
- **Timesheet** — log a work day by typing your start/end times or clicking the time
  grid. It auto-deducts your break (30 min or 1 hour, your choice) on long shifts and
  multiplies by your hourly rate.
- **Budget** — track expenses by category, add **other income** (e.g. side jobs), and
  import a bank statement from a CSV file. Flip on **Year to date** to see the whole
  year.
- **Money Flow** — a visual chart of where your money comes from and goes.
- **Export** — download a clean Excel or CSV report anytime.

Everything syncs across your devices automatically, encrypted the whole way.

---

## Host your own copy (optional — makes you fully independent)

If someone shared this app with you and you'd rather not depend on their link, you can
host your own free copy in about 10 minutes:

1. Create a free GitHub account (Step 1 above) if you don't have one.
2. Create a new repository at **https://github.com/new** — name it `timesheet`,
   set it to **Public**, and click **Create repository**.
3. On the repo page click **Add file → Upload files**, upload the app file, and make
   sure it's named **`index.html`**. Click **Commit changes**.
4. Go to the repo's **Settings → Pages**. Under "Build and deployment" set
   **Source = Deploy from a branch**, **Branch = main**, folder **/ (root)**, and
   **Save**.
5. Wait 1–2 minutes. Your own copy is now live at
   `https://YOUR-USERNAME.github.io/timesheet/`.

Your data still lives in **your own** private gist regardless of who hosts the app —
hosting only affects where the (data-free) code is served from.

---

## Questions people ask

**Does the person who shared this see my data?** No. Your data is encrypted with your
passphrase in your own gist. They have no access to either.

**Does it cost anything?** No. GitHub Pages (hosting) and gists (storage) are free.

**Do I need the internet?** To sync, yes. The app itself still works offline; it syncs
next time you're online.

**I lost my phone — is my data gone?** No. It's safe in your gist. Just open the app on
a new device and enter your token, Gist ID, and passphrase.

**I forgot my passphrase.** The synced data can't be recovered — there's no backdoor,
by design. This is why writing it down matters.
