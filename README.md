# 🧭 BD Tour Planner

A simple trip planner for Bangladesh, built for use on your phone. It covers Chattogram division in the most detail.

## ▶️ Open the app

**👉 https://labib1610.github.io/tour_planner/**

Open the link in Chrome on your phone and allow location when it asks.
To keep it like an app: Chrome menu **⋮ → Add to Home screen**.

---

## What it does

- **Nearest places.** About 300 tourist places, sorted by distance from where you are right now (live GPS). Filter by type (beach, hill, waterfall…) or division, or search by name.
- **Place details.** Description, distance, estimated travel time, best season, entry fee and how long to spend there.
- **Directions from my location.** Opens Google Maps with the route from your current position.
- **Nearby from here.** Every place lists the 6 closest other places, so you can chain stops.
- **My list.** Places you want to visit, sorted by distance.
- **Visited.** Tick off places as you go and track your progress.
- **Day-by-day itinerary.** Add places to Day 1, Day 2… See the distance and time between stops, and open the whole day's route in Google Maps.
- **Notes & photos.** For each place.
- **Your own places.** Add any spot that's missing (Tools → New place).
- **Packing checklist and emergency numbers.** Tap a number to call it.
- **Day / Night mode.**

## Where your data is saved

- Everything is saved **on your phone automatically**. There's no login, and each person has their own data.
- **Backup:** Tools → Export backup downloads a file with everything, including photos. Import it on a new phone.
- **Sync (optional):** keeps two or more phones showing the same plan. See below.

## Sync between phones (free)

Sync is useful when you plan on one phone and travel with another, or when your tour group should see the same plan. Add a place to Day 2 on one phone and it shows up on the other.

What syncs: my list, visited places, itinerary days, notes, packing list, contacts and custom places.
What doesn't: photos (they stay on the phone that took them).

**One-time setup (about 5 minutes, free, no card):**

1. Go to https://console.firebase.google.com, sign in, and **Create a project** (turn off Analytics).
2. **Build → Realtime Database → Create database.** Choose Singapore and **Locked mode**.
3. On the **Rules** tab, replace the text with the rules below and click **Publish**:
   ```json
   {
     "rules": {
       "bdtour": {
         "$code": { ".read": true, ".write": true }
       }
     }
   }
   ```
4. On the **Data** tab, copy the database link (`https://…firebasedatabase.app`).
5. In the app: **Tools → Sync between phones**, paste the link and tap **Turn on**.
6. Tap **Share link** and open it on your other phone. Done.

Keep the share link private. Anyone who has it can see and edit that plan.

## Update the app

Replace `index.html` in this repo (**Add file → Upload files → Commit**). The live link updates in about a minute.

## Notes

- Distances are straight-line. Travel times are rough road estimates.
- Entry fees and access rules change, especially for Saint Martin's, Bandarban's remote areas and the Sundarbans. Check locally before you go.
- Emergency: **999** (police, fire, ambulance).
