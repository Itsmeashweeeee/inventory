# CGC Shop Inventory

A browser-based inventory tracker with live sync via Google Sheets. Any computer that opens the URL sees the same data in real time.

---

## One-time setup (do this first)

### Step 1 — Create the Google Sheet

1. Go to [sheets.google.com](https://sheets.google.com) and create a new blank spreadsheet
2. Rename it **CGC Inventory** (click the title at the top)
3. Rename the first tab at the bottom to **Inventory** (right-click the tab > Rename)
4. In row 1, add these headers exactly as written, one per column:

   | A | B | C | D | E | F |
   |---|---|---|---|---|---|
   | Item | Location | Qty | Min | Updated | Status |

5. Copy the Sheet ID from the URL — it's the long string between `/d/` and `/edit`:
   `docs.google.com/spreadsheets/d/`**`THIS-IS-YOUR-SHEET-ID`**`/edit`
   Save this — you'll need it shortly.

---

### Step 2 — Create a Google Cloud project and enable the Sheets API

1. Go to [console.cloud.google.com](https://console.cloud.google.com)
2. Click the project dropdown at the top left > **New Project**
3. Name it **CGC Inventory** > click **Create**
4. Once the project is created, go to **APIs & Services > Library**
5. Search for **Google Sheets API** and click **Enable**

---

### Step 3 — Create an API key

1. Go to **APIs & Services > Credentials**
2. Click **+ Create Credentials > API key**
3. Copy the key that appears — save it somewhere safe
4. Click **Edit API key** (the pencil icon next to it)
5. Under **API restrictions**, select **Restrict key**, then choose **Google Sheets API** from the dropdown
6. Click **Save**

---

### Step 4 — Share the Google Sheet with the API

1. Open your Google Sheet
2. Click **Share** (top right)
3. Change the access to **Anyone with the link can edit**

   This is required so the app can write data back to the sheet. The sheet URL itself is not public unless you share it — only the app uses it.

---

### Step 5 — Connect the app

1. Open the app URL: `https://yourusername.github.io/cgc-inventory`
2. You'll see a yellow banner at the top with two fields
3. Paste your **Sheet ID** in the first field
4. Paste your **API key** in the second field
5. Click **Connect →**

The app will load your sheet data immediately. Any computer that opens the URL and enters the same credentials will see live data.

To avoid entering credentials every time, each computer only needs to connect once — the app saves the config in that browser automatically.

---

## Daily use

**Updating quantities**
Use the − and + buttons on any row. Changes save to Google Sheets automatically within one second.

**Adding items**
Fill in the four fields at the top and hit + Add item (or press Enter).

**Editing an item**
Click the pencil icon on any row to edit name, location, quantity, or minimum.

**Refreshing**
Click ↺ Refresh to pull the latest data from the sheet manually. The app loads fresh data every time it opens.

---

## Status labels

| Status | What it means |
|---|---|
| OK | Quantity is at or above 1.5x the minimum. No action needed. |
| Running low | Quantity is between the minimum and 1.5x the minimum. Order soon. |
| Order now | Quantity is below minimum. Order it. |
| Out of stock | Zero on hand. Urgent. |

---

## Backup

Click **↓ Export CSV** at any time to download a copy. Upload it to OneDrive as a backup record. The Google Sheet itself is also a permanent backup — you can open it directly and see all the data there too.

---

## Troubleshooting

**"Load failed — check credentials"**
Double-check the Sheet ID and API key. Make sure the Sheets API is enabled in Google Cloud Console (Step 2).

**"Save failed — API key may need write access"**
Make sure the Sheet is set to "Anyone with the link can edit" (Step 4). Read-only sharing blocks writes.

**Data not updating on the other computer**
Click ↺ Refresh. The app loads fresh data on page open, but a manual refresh pulls any changes made since then.
