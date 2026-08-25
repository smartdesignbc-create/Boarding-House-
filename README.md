Michaelhouse Boarding House Allocation Dashboard
A single-file, self-contained web app for managing boarding house room and bed
allocations across Michaelhouse's ten boarding houses — festival/event team
allocation, room availability, a live bed-capacity heat map, and a duty roster,
all in one HTML file with no backend required.
→ Open the live dashboard
(update this link once GitHub Pages is switched on — see below)
What's inside
Bed Capacity Heat Map — all ten houses at a glance, colour-graded by bed count
Duty Roster — MIC, Intern, and Functions Manager/Coordinator on duty
Per-house allocation — enter up to 3 teams per festival (students, coach,
manager), auto-populate systematically into rooms, or select rooms manually
Room management — mark rooms/blocks available or unavailable, edit or
add rooms, flag unconfirmed rooms pending house-mother verification
Search — find any guest name or room number across all ten houses
Save Progress / Load Progress — exports/imports a JSON snapshot of all
data, since the app itself has no backend or database yet
Status: trial / building stage
This is a working prototype, not a production system. Specifically:
No backend. All data lives in the browser tab's memory. Refreshing or
closing the page clears everything unless you've used Save Progress
first (top right of the dashboard) to download a snapshot, and Load
Progress to bring it back in next time.
Single-user at a time. Two people can't edit the same live session
together — each browser tab is its own isolated copy of the data.
Room data is still being confirmed. Some houses (Founders, East,
Tatham) have no room data loaded yet. Others carry an on-page "Data note"
flagging bed counts that don't fully reconcile with the original inspection
sheets, pending a walkthrough confirmation.
None of this affects how the tool behaves for a single person working through
allocations in one sitting — it's only relevant once several people need to
share the same live data, at which point this should move to a proper backend
(Supabase or similar).
Hosting this on GitHub Pages (get a permanent link)
Create a new public GitHub repository (e.g. boarding-house-dashboard).
Upload index.html — rename the dashboard file to exactly index.html
before uploading, since GitHub Pages looks for that filename by default.
In the repo, go to Settings → Pages.
Under Build and deployment → Source, choose Deploy from a branch.
Pick the main branch and the / (root) folder, then Save.
Wait a minute or two — GitHub will show you the live URL, typically:
https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/
That's your permanent, shareable link. Update it at the top of this file
once you have it.
Any time you make changes to the dashboard, just upload the new index.html
over the old one (or push a commit) — the live link stays the same.
Updating room data
All house data lives near the top of the <script> section, in a HOUSES
object. Each house has a name and a list of blocks, each with a list of
rooms (id, beds, available). To load a house that currently has
blocks: [], replace it with the same structure used for an existing house,
or use the Edit Rooms button on that house's page inside the app itself —
no code changes needed for day-to-day corrections.
File structure
This is intentionally a single file — index.html contains all HTML, CSS,
and JavaScript. There's nothing else to deploy.
License / ownership
Internal tool for Michaelhouse. Not for external distribution.
