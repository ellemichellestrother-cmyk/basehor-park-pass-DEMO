# 🌸 Basehor Park Pass 2027

The digital Park Pass for **Basehor Parks & Rec — Basehor WELL: Growing Together**.
Kids check in at events, crack lockboxes hidden around town, stamp their pass (paper *and* digital), snap photos, and watch their six-petal WELL flower fill up.

No logins, no server, no database — it's a plain static website that runs free on **GitHub Pages**. Each family's progress and photos are saved in their own browser, with a one-tap backup file.

---

## How it works (for families)

1. **Check in at events** — scan the QR poster at each event → event stamp + petal points.
2. **Or do a challenge** — each lockbox has a challenge; finishing it reveals a secret word.
3. **Get a combo** — event codes and challenge words reveal a 4-digit lockbox combo.
4. **Follow the route map** to the box, open it, stamp the paper pass.
5. **Type the secret word** from the card inside → digital stamp + photo.
6. **Golden Seed Box** — the six words from the six petal boxes unlock the finale combo automatically.

### The flower
| Earn | Points |
|---|---|
| Event check-in | +1 to **each** petal the event is tagged with |
| Challenge | +1 to that box's petal |
| Lockbox stamp | +2 to that box's petal |

5 points fills a petal (change `petalGoal` in the EDIT section of `index.html`).

### Event → petal assignments
| Event | Petals | QR reveals |
|---|---|---|
| Build-a-Bear Night (Fri Feb 12) | Safety, Connection | 🛡️ Shield Box |
| Friday Night Flicks ×4 (Apr 23, May 21, Sep 10, Oct 8 — make-ups the next Friday) | Connection, Mind | 🤝 Buddy Box |
| Basehor's Blooming (Sat May 1) | Environment, Connection | 🌱 Sprout Box |
| Golfish (Thu May 13, 5:30) | Body, Environment | 💪 Wiggle Box |
| 3rd Thursday Concerts (May 20, Jun 17, Jul 15, Aug 19) | Mind, Connection | 🧩 Brainy Box |
| Whales & Scales (Sat Jun 5, 8:00 AM) | Environment, Purpose | 🌱 Sprout Box |
| Water Days (Fri Jun 11, Jul 9, Aug 6 · 4–7 PM) | Safety, Body | 🛡️ Shield Box |
| Basehor's Got Talent (Sat Sep 18, 5:00) | Purpose, Mind | 🎯 Goal Box |
| Fall Market Mornings (Sat Oct 2 & Nov 13 · 9–11 AM) | Connection, Environment | 🤝 Buddy Box |
| Skeleton Ruck (Sat Oct 16) | Body, Purpose | 💪 Wiggle Box |
| Candlelight Concert (Thu Nov 4) | Mind, Purpose | 🧩 Brainy Box |

Every petal can be filled several different ways, so kids who come to a little of everything bloom fastest.

---

## Put it on GitHub (about 10 minutes)

**Everything the site needs is inside `index.html`** — styles, scripts, events, codes and the logo. The other files are optional extras (home-screen icons, link-preview picture, offline support), so nothing breaks if one goes missing.

1. **Unzip the download first** (right-click → *Extract All* on Windows). Don't open files from inside the zip.
2. Sign in at **github.com** → **New repository** → name it `basehor-park-pass` → **Public** → **Create repository**.
3. Click **uploading an existing file**, select **all the files** from the unzipped folder, drop them in → **Commit changes**. (No folders to worry about — they all sit side by side.)
4. **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main`, folder `/ (root)` → **Save**.
5. Wait a minute, then visit `https://ellemichellestrother-cmyk.github.io/basehor-wellness-pass/`.

You can also just double-click `index.html` on your computer to try it — it works from a single file (the map, QR scanner and fonts need internet).

### If the page ever looks plain or broken
It shows a yellow **“Oops — the Park Pass didn’t load all the way”** box that says what went wrong. Most common fixes: refresh; make sure the newest `index.html` was uploaded; wait a minute after committing on GitHub.

---

## ✅ Launch checklist

- [ ] **Event details** — open `index.html` in any text editor (or click it on GitHub → ✏️ pencil) and search for **`EDIT YOUR PARK PASS HERE`**. Fill in each event's `place`, and the times for Basehor's Blooming, Skeleton Ruck and Candlelight Concert (`time: null` shows “Time coming soon”). Flicks times are dusk estimates. Event descriptions are placeholders — reword anything that doesn't match the real event.
- [ ] **Box locations** — only Basehor City Park (15940 Leavenworth Rd) is a real spot. Open **`admin.html` → Set box locations**: find the spot in Google Maps, copy its coordinates, paste them in, and copy the line it gives you into the same EDIT section. The preview shows how the trail map will look. Update each box's `place`, `hint` and challenge `where`.
- [ ] **Real codes** — open **`your-site/admin.html` → Combos & codes**:
  - enter each lockbox's real combo + the secret word you'll put inside,
  - pick challenge words and event codes (🎲 fills the blanks),
  - **Save staff setup (private)** → keep that file in a staff-only folder,
  - **Build & download upload files (.zip)** → unzip it → on GitHub, **Add file → Upload files**, drop in everything from the folder, commit. That replaces `index.html` and every calendar file, and the demo codes stop working.
  - Edited events locally and not uploaded yet? Click **📂 Use a different index.html** first so the codes match.
- [ ] **Print** (admin tab 2): event QR posters, challenge signs, secret-word cards for inside the boxes, lockbox tags. Enter your live site address first so the QR codes point to it. In the print dialog, turn on **Background graphics** for full color.
- [ ] Set `onlyCheckInFromEventDay: true` (same EDIT section) so event codes can't be used early.
- [ ] **Changed an event's date, time or place?** Run the admin build again (it re-makes the calendar files from your latest index.html) and upload the zip, so calendars match.
- [ ] After changing files, bump `VERSION` in `sw.js` (e.g. `bpp27-v5`) so phones that installed the app get the update right away.

> `admin.html` isn't linked from the kids' site, but it's a public URL. It never stores or uploads anything — the real combos only exist in the private setup file you save.

---

## 🧪 Demo codes (built into the current secrets.js — replace before launch!)

| Type | For | Code |
|---|---|---|
| Event QR | Build-a-Bear Night (2027-02-12) | `BEAR27` |
| Event QR | Friday Night Flicks (2027-04-23) | `FLICK127` |
| Event QR | Basehor's Blooming (2027-05-01) | `BLOOM27` |
| Event QR | Golfish (2027-05-13) | `GOLFISH27` |
| Event QR | 3rd Thursday Concert (2027-05-20) | `CONCERT527` |
| Event QR | Friday Night Flicks (2027-05-21) | `FLICK227` |
| Event QR | Whales & Scales (2027-06-05) | `WHALES27` |
| Event QR | Water Day (2027-06-11) | `WATER127` |
| Event QR | 3rd Thursday Concert (2027-06-17) | `CONCERT627` |
| Event QR | Water Day (2027-07-09) | `WATER227` |
| Event QR | 3rd Thursday Concert (2027-07-15) | `CONCERT727` |
| Event QR | Water Day (2027-08-06) | `WATER327` |
| Event QR | 3rd Thursday Concert (2027-08-19) | `CONCERT827` |
| Event QR | Friday Night Flicks (2027-09-10) | `FLICK327` |
| Event QR | Basehor's Got Talent (2027-09-18) | `TALENT27` |
| Event QR | Fall Market Morning (2027-10-02) | `MARKET1027` |
| Event QR | Friday Night Flicks (2027-10-08) | `FLICK427` |
| Event QR | Skeleton Ruck (2027-10-16) | `RUCK27` |
| Event QR | Candlelight Concert (2027-11-04) | `CANDLE27` |
| Event QR | Fall Market Morning (2027-11-13) | `MARKET1127` |
| Challenge word | Shield Box – Safety Scout | `SHIELDUP` |
| Challenge word | Buddy Box – Kindness Quest | `HIGHFIVE` |
| Challenge word | Wiggle Box – Move-It Mile | `WIGGLE` |
| Challenge word | Goal Box – Dream Big Goal | `DREAMBIG` |
| Challenge word | Sprout Box – Park Protector | `SPROUT` |
| Challenge word | Brainy Box – Quiet Spot Quest | `LISTEN` |
| Word inside box | Shield Box (combo 2417) | `HELMET` |
| Word inside box | Buddy Box (combo 8053) | `FRIENDS` |
| Word inside box | Wiggle Box (combo 3196) | `JUMP` |
| Word inside box | Goal Box (combo 7720) | `STARS` |
| Word inside box | Sprout Box (combo 4688) | `ACORN` |
| Word inside box | Brainy Box (combo 5931) | `WONDER` |
| Word inside box | Golden Seed Box (combo 1027 — revealed after all 6 words) | `SUNFLOWER` |

Codes ignore capitals, spaces and dashes. A QR code is just your site link with `?c=CODE` on the end, e.g. `https://ellemichellestrother-cmyk.github.io/basehor-wellness-pass/?c=BLOOM27`.

---

## What's in the folder

Upload **everything** to the top level of your GitHub repo (no folders):

```
index.html            ⭐ the whole Park Pass site (edit events in the "EDIT YOUR PARK PASS HERE" section)
admin.html            staff tools: codes + calendars → upload zip, QR posters, signs, box locations
cal-season.ics        whole-season calendar (families can subscribe — it updates itself)
cal-<event>.ics       one calendar file per event (21 files total) — what "Add to my calendar" opens on iPhone
sw.js                 offline support + faster loading
manifest.webmanifest  "add to home screen" app name & colors
icon-192.png, icon-512.png, apple-touch-icon.png   home-screen icons (new logo)
brand.jpg             the Basehor WELL logo, shown when the link is shared
.nojekyll             tells GitHub Pages to serve the files as-is (hidden file — fine to skip)
README.md             these notes
```

## Good to know
- **Saving:** progress lives in the browser's storage; photos are shrunk to ~300 KB each and kept in the browser's photo database. Clearing browser data or switching phones loses them **unless the family restores a backup file** (More → Save backup). The home screen nudges kids to back up after a few new stamps.
- **Siblings:** one phone can hold several explorers. When a code is entered, it asks who's there so the whole crew can check in at once.
- **Combos are scrambled:** the `park-secrets` block only stores fingerprints of the codes plus scrambled digits. Peeking at the site's source code won't reveal a combo without the matching code or word.
- **Logo & photo:** the new Basehor WELL logo (brown seal) and the sunflower photo behind the flower are built into `index.html`. Colors match the logo: Safety coral, Connection periwinkle, Body orange, Purpose gold, Environment green, Mind teal, navy and seal-brown accents.
- **Paper pass:** "Print a paper Park Pass" prints 2 pages — page 1 has stamp circles + the event checklist; page 2 is a big WELL flower with 5 stripes per petal to color in (earned stripes print pre-colored).
- **Calendar:** families can add one event or the whole season to their phone calendar.
- **The map** is an illustrated trail map built into the page — no map service, no API key, nothing to break. Pins are placed from each box's real coordinates (so they sit in the right spots relative to each other), and tapping a pin opens that box with **Google Maps directions**. “Open full route in Maps” opens every box as stops; “Closest box to me” uses the phone's location.
- **Calendar buttons** open the phone's own calendar: iPhone/iPad/Mac → Apple Calendar's “Add” screen (season → “Subscribe”, which auto-updates); Android → Google Calendar, pre-filled (season → subscribe); computers → a calendar file Outlook/Calendar opens. Each event also has an “or use Google Calendar” link.
