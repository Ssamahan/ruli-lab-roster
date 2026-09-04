# Ruli District Hospital — Laboratory Smart Roster

**Live link (after you enable Pages):** `https://ssamahan.github.io/ruli-lab-roster/`

Single-file web app for:
- Monthly Working Plan (full month + first week next month)
- Weekly Unit Roster (Reception, Phlebotomy, Hematology, Biochemistry, Serology, Parasitology, TB/Molecular)
- Leave engine (Statute 30d, Contractual 18d, Maternity 14 weeks, Wedding day 💍)
- Version history, Dashboard KPIs, Trainings mirror, Links Hub
- Exports: PDF + Excel in Trebuchet, A4 landscape, faint grey lines
- Live Sync: Firebase Realtime Database — Manager edits, staff observers live read-only

## How to update
Just replace `index.html` in this repo. The link stays the same forever.

## Firebase Live Sync (optional but recommended for observer mode)
1. Create project at https://console.firebase.google.com
2. Realtime Database → Create → locked mode → Rules:
```json
{
  "rules": {
    "labRoster": {
      ".read": true,
      ".write": "auth != null"
    }
  }
}
```
3. Authentication → Email/Password → Enable → Add user (you = manager)
4. Project Settings → Web app → copy firebaseConfig
5. Open your live site → ☁️ Live Sync tab → paste config → Connect → Sign in → Push

After that, staff just open the link — they automatically see live updates read-only.

Built for Lab Manager: Kelvin SAMAHANI
Verified by: Dr. Judson B. MUMBERE
Approved by: Jean de Dieu SIBOMANA
