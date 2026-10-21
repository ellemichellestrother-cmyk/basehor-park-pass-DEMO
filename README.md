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
- [ ] **Codes** — a full real set is already built in. To review or change them, open **`your-site/admin.html`**, load your private setup file (everything autofills), edit, then:
  - set each physical lock to its combo and put that box's word card inside,
  - **Save staff setup (private)** → keep that file in a staff-only folder,
  - **Build & download upload files (.zip)** → unzip it → on GitHub, **Add file → Upload files**, drop in everything from the folder, commit. That replaces `index.html` and every calendar file.
  - Edited events locally and not uploaded yet? Click **📂 Use a different index.html** first so the codes match.
- [ ] **Print** (admin tab 2): event QR posters, challenge signs, secret-word cards for inside the boxes, lockbox tags. Enter your live site address first so the QR codes point to it. In the print dialog, turn on **Background graphics** for full color.
- [ ] **Prizes** — once chosen, type them into `prizes` in the EDIT section (`box`, `golden`, `bloom`). Blank ones stay hidden; filled ones show in “How it works”, on the box screens and in the stamp celebration.
- [ ] **Launch switches** (staff tool → Build): turn **test mode OFF** and **event-day check-ins ON**, build, and upload. (Test mode is ON right now so staff can try everything.)
- [ ] **Changed an event's date, time or place?** Run the admin build again (it re-makes the calendar files from your latest index.html) and upload the zip, so calendars match.
- [ ] After changing files, bump `VERSION` in `sw.js` (e.g. `bpp27-v5`) so phones that installed the app get the update right away.

> `admin.html` isn't linked from the kids' site, but it's a public URL. It never stores or uploads anything — the real combos only exist in the private setup file you save.

---

## 🔑 Codes are private

The real combos, words and event codes are **not** in this repo. Only scrambled fingerprints are inside `index.html`. They live in the private staff setup file (`park-pass-STAFF-setup-PRIVATE.json`) and the printed staff key. Load that file into `admin.html` once and every code autofills. **Never upload the setup file or the staff key to GitHub.**

A QR code is just the site link with `?c=CODE` on the end. The staff tool prints all of them for you.

## 🗓️ Season rollout (keeps families coming back)

- **One new challenge a month.** Each challenge has an `opens` date in the EDIT section. Before that date its word won't work and the app shows "Opens June 1" instead.

  | Opens | Challenge | Word comes from |
  |---|---|---|
  | Feb 12 | Safety Scout | Staff (out loud) |
  | May 1 | Park Protector | Green sign in a park |
  | Jun 1 | Dream Big Goal | Staff at the Goal Board |
  | Jul 1 | Move-It Mile | Orange Mile Marker sign |
  | Aug 1 | Kindness Quest | Staff at the front desk |
  | Sep 1 | Quiet Spot Quest | Teal Listen Here sign |

  **Post each sign on its opening day, not before.** The staff key sheet lists the dates.
- **Earn the combo first.** A lockbox's secret word only stamps the pass once that child has unlocked the box's combo (from an event or the challenge). A photo of a word card can't be used to skip the trail.
- **Golden Seed finale opens Oct 1** (`finale.opens`). Kids can collect all six words any time, but the finale combo appears in their pass on that date, with a celebration.
- **Reminders:** the Home screen announces each new challenge and counts down to the next one. The pass shows a **season streak** (one Park Pass thing per month lights that month up). The subscribable season calendar includes every challenge drop and the finale, so families get a phone reminder each month.
- **Test mode (ON right now):** ignores every date so staff can try every challenge and the finale. A red “Test mode is on” banner shows on Home. Switch it off in the staff tool's **Launch switches** before launch.

## 🗂️ Bottom menu

**Home · Events · Challenges · 📷 Unlock · Lockboxes · More.** Each activity has its own tab with its own stamps: event stamps on **Events**, challenge stamps on **Challenges**, lockbox stamps (and the map) on **Lockboxes**. The season streak is on Home; the photo album, backup and printables are under More.

## 🎁 Mystery challenges (inside the lockboxes)

Each petal lockbox holds a **mystery challenge card** (staff tool → Print → *mystery challenge cards*). The task is on the front; fold the card backward and laminate so the **mystery word is on the back**. Kids do the task right there, flip the card, and type the word for **+2 points** (it only counts after they’ve stamped that box). The app keeps the task a surprise until the word is typed. Edit the tasks in `js/data.js` (`mystery:` on each box) and the words in the staff tool.

## 🌳 “While you’re here” prompts

Each box has `setting: 'park'` or `'cityhall'`. When a family opens a box, and right after they stamp it, the app lists the open challenges they can do at that spot, the mystery card, and a packing list. The Lockboxes tab has a **“Heading out to a lockbox?”** planner, and each challenge shows where it can be done (🌳 Park · 🏛️ City Hall · 🏠 Home).

## 🙋 Help for families (step-by-step guides)

- **❓ Help button** at the top of every screen opens a plain-language *How to play* guide: a glossary, the four ways to earn points, a worked example, and common questions.
- **Every challenge has its own step-by-step page**: what you need, how long it takes, numbered steps, where the secret word comes from, how to type it in, the Staff Bonus, a tip for grown-ups, and a progress checklist.
- **Every lockbox shows a checklist** (combo → open box → challenge → Staff Bonus) so families can see what's done and what's next.
- **Clearer messages**: if a word is typed too early, the app explains why and offers a button to the right steps.
- **Video guide (5 min)**: `howto.mp4` (the 5-minute full guide) plays inside the Help guide and from More → *Watch the video guide*. Captions are on screen (plus `howto.vtt` for screen readers). The same file can be posted on Facebook/Instagram.
- **Text size**: More tab → Text size → Normal, Large or Extra large (remembered on that phone).
- **Large-print handout**: More tab → *Print the large-print How to Play guide* (11 pages: the guide plus one page per challenge). Keep copies at the City Hall window and event check-in tables.
- Fill in `help` in `js/data.js` (hours, phone, email) to show them on every help page; blank lines are hidden.

## 🤝 Staff Bonus (kids come talk to us)

Every challenge has a **Staff Bonus worth +1 more point**. After finishing a challenge, a child shares it with a staff member **at the City Hall window or at any Park Pass event**, and staff give them the bonus word (say it, or let them scan the card).

| Challenge | What the child shares with staff |
|---|---|
| Safety Scout | Their drawing of the family fire-drill meeting spot |
| Park Protector | The 3 trees or birds they spotted (photo or drawing counts) |
| Dream Big Goal | One step they’ve taken toward their goal |
| Move-It Mile | Their mile (photo or map) + 10 jumping jacks together |
| Kindness Quest | Reading their thank-you card out loud |
| Quiet Spot Quest | Acting out 3 sounds they heard for staff to guess |

- The bonus word only counts **after** that challenge is done, and only from the challenge’s opening date.
- Bonus words exist only on the **Staff Bonus cards** (staff tool → Print). Keep a set at the City Hall window and at every event check-in table.
- Safety Scout now asks kids to learn their address, **their grown-up’s full name** and phone number, and tell staff all three.

## 🖐️ Stamps: what you need

- **Rubber stamps: 7**, one inside each lockbox (6 petal boxes + Golden Seed), plus spare ink pads. That's the only place physical stamps are used.
- **Events: no rubber stamp.** Scanning the QR gives a digital event stamp. Kids using a paper pass ask the check-in staffer to initial that event on page 1.
- **Challenges: no stamp.** They give +1 petal point and the box combo.

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
- **Changing a lock's combo mid-season** (leaked, box replaced): set the new combo on the lock, enter it in the staff tool, build and upload the zip. Keep the codes and words the same. Kids who already unlocked that box see the new combo automatically next time they open the pass.
- **What each thing earns** (also shown to families under “How it works”): event check-in = +1 to each of its 2 petals, an event stamp and a box combo · challenge = +1 to its box's petal and that box's combo · lockbox = +2 to its petal, a lockbox stamp and a Golden Seed word · Golden Seed Box = finale stamp · 30 points = full bloom (Basehor WELL Star).
- **Calendar buttons** open the phone's own calendar: iPhone/iPad/Mac → Apple Calendar's “Add” screen (season → “Subscribe”, which auto-updates); Android → Google Calendar, pre-filled (season → subscribe); computers → a calendar file Outlook/Calendar opens. Each event also has an “or use Google Calendar” link.
