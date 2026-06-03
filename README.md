# CGC Shop Inventory

A browser-based inventory tracker for the shop. No login, no app to install. Just open the link and go.

---

## How to use it

**Open the app**
Bookmark this link on the shop computer: `https://yourusername.github.io/cgc-inventory`

**During a quantity check**
1. Walk the shop with the computer open or check shelf by shelf
2. Use the **−** and **+** buttons to update quantities on each item
3. The Status column updates automatically — red means order it, yellow means getting low, green means you're good

**Adding a new item**
Fill in the four fields at the top (item name, location, qty on hand, minimum qty) and hit **+ Add item**. Press Enter to save faster.

**Editing an existing item**
Click the pencil icon on any row to edit the name, location, quantity, or minimum. Click the checkmark to save.

**When you're done with a check**
Click **↓ Export CSV** and save the file. Upload it to the shared OneDrive folder so there's a backup on record.

---

## Status labels

| Status | What it means |
|---|---|
| OK | Quantity is at or above 1.5x the minimum. No action needed. |
| Running low | Quantity is between the minimum and 1.5x the minimum. Order soon. |
| Order now | Quantity is below the minimum. Order it. |
| Out of stock | Zero on hand. Urgent. |

---

## Minimum quantity

The **Min** column is the reorder point — the lowest quantity you want to have before placing an order. Set it based on how fast you use something and how long an order takes to arrive. Review these numbers quarterly and adjust as needed.

---

## Important notes

- Data saves automatically in this browser on this computer. It does not sync anywhere on its own.
- If browser history or cache is cleared, the data will be lost. **Export CSV after every check session** and upload it to OneDrive.
- The app works offline once loaded.

---

## Restoring from a backup CSV

If the browser data is lost, you can re-enter items manually from the most recent CSV backup in OneDrive. The CSV columns match the app fields: Item, Location, Qty On Hand, Min Qty.

---

## Making changes to the app

The entire app is a single file: `index.html`. To update it, edit the file and upload the new version to this repository. GitHub Pages will publish the update automatically within a minute or two.
