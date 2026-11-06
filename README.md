# Base Gear Inventory / ציוד בבסיס

A mobile-first Hebrew/English app for tracking your gear at base: what's there, what's missing, and what to pack before every trip.

## Features
- **Gear tab:** a summary ring showing how much of your list is in place, quick +/− counters (tap the number to type one in), and grouped, collapsible categories
- **Two counts per item:** *how many I need* vs *how many I have*, with a "need N" or "+N spare" tag on each item
- **Three item types:**
  - 🔢 *Counted*: you track how many you have
  - ⏬ *Used up*: socks, underwear, shampoo. Each has a usage rate ("1 per day", "1 every 14 days"), and one **☀️ Day passed** tap lowers them all (with undo).
  - 🔒 *Always here*: towel, flip-flops. No counter; they sit in a quiet collapsed section. Tap "Missing?" if one disappears and it moves to the main list and the packing list.
- **Where it lives:** 🗄️ *stays at base* (closet), 🎒 *travels with me* (bag), or no fixed spot
- **Pack tab:** a checklist that saves your progress
  - *Bring to base*: everything that's short at base. Ticking an item updates its count at base.
  - *Bag checklist*: everything that travels with you, every trip
  - Share the list (WhatsApp, etc.) and start a new trip with one tap
- Filters you can combine (status + bag/closet + category) and search across names and notes
- Undo after deleting, resetting or importing
- Starter list of common items, duplicate-name warning, an "add another" mode for adding several items in a row
- Categories: pin, rename, delete
- Dark, light and auto themes; full Hebrew and English
- Export/import JSON with a backup reminder; copy the whole list as text
- Installable PWA that works offline (add to home screen)

## Usage
Open `index.html` in any browser. No install needed.
Data is saved locally in your browser (localStorage). Data from earlier versions loads automatically.

**Live site:** https://arcdemonx.github.io/base_list/

## Moving data after a username change
Data lives in the browser, tied to the site address (`<username>.github.io`), not to the repo. After a rename the app opens empty at the new address. The old data is still in the browser, under the old address.

`rescue.html` gets it back. Host it at the old address and open it in the same browser:
1. Create a GitHub account (or a free organization) with the old name, `PoH-rull`.
2. In that account, create a public repo named `poh-rull.github.io`. Upload `rescue.html` as `index.html`, then enable Pages (Settings → Pages → Deploy from branch → `main` / root).
3. Open https://poh-rull.github.io/ in the browser where you used the apps. Tap **Download backup** first, then **Move to new site** for each app.

The page only reads storage. The move puts the data in the URL `#hash`, which is never sent to any server. Anything already at the new address is kept under a `.before-restore` key.
