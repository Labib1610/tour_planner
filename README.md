# 🧭 BD Tour Planner

A simple trip planner for Bangladesh, built for use on your phone. It covers Chattogram division in the most detail.

## ▶️ Open the app

**👉 https://labib1610.github.io/tour_planner/**

Open the link in Chrome or Safari on your phone and allow location when it asks.
To keep it like an app: browser menu → **Add to Home screen**.

---

## Two ways to use it

**Trip account (recommended for groups)**
Type a **trip name** and a **4-digit PIN**, then tap Open trip. The first time, the app asks to create it.
Anyone who enters the same name and PIN on any phone sees and edits the same plan. Changes show up on the other phones within about 10 seconds.

**Guest**
Saved on this phone only. No name or PIN needed.

You can switch any time in **Tools → Account**.

## What it does

- **Nearest places.** About 350 tourist places, sorted by distance from your live location or from your hotel. Filter by type or division, or search.
- **Place details.** Description, distance, travel time, best season, entry fee and how long to spend there.
- **Directions from my location.** Opens Google Maps with the route from where you are.
- **Itinerary.** Day 1, Day 2… each with a date, where you're staying, breakfast, lunch, dinner, transport and notes. Each entry can have a Google Maps link.
- **Near your stay.** Add the hotel's location and the day shows the closest places to it. Explore can also sort every place by distance from the hotel.
- **My list** and **Visited**, to track where you want to go and where you've been.
- **Members.** Everyone on the tour, with phone, room or role.
- **Notes & photos** for each place, **your own places**, a **packing checklist** and **emergency numbers**.
- **Day / Night mode.**

### Adding a hotel or restaurant location

In Google Maps, **long-press the spot**. The coordinates appear at the top (like `22.3268, 91.8105`). Copy them and paste them into the app.
Full Google Maps links also work. Short share links (`maps.app.goo.gl/…`) open fine with the Map button, but the app can't read their location for nearby suggestions.

---

## One-time setup for trip accounts (site owner only)

Trip accounts save to your free Firebase database (no card needed).

1. In Firebase, check that **Realtime Database → Rules** is:
   ```json
   {
     "rules": {
       "bdtour": {
         "$code": { ".read": true, ".write": true }
       }
     }
   }
   ```
2. Copy the database link from the **Data** tab (`https://…firebasedatabase.app`).
3. In this GitHub repo: **Add file → Create new file**. Name it `config.json` and paste in:
   ```json
   { "firebase": "https://YOUR-DATABASE-LINK.firebasedatabase.app" }
   ```
   Then click **Commit changes**.

That's it. Every visitor's phone now uses that database for trip accounts.

## Update the app

Replace `index.html` in this repo (**Add file → Upload files → Commit**). The live link updates in about a minute.

## Notes

- A 4-digit PIN is easy to guess. Use a trip name that isn't obvious, and don't store anything private.
- Distances are straight-line. Travel times are rough road estimates.
- Entry fees and access rules change, especially for Saint Martin's, Bandarban's remote areas and the Sundarbans. Check locally before you go.
- Emergency: **999** (police, fire, ambulance).
