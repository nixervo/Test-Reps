============================================================
  NINJARIFT CLAN REPUTATION TRACKER — SETUP GUIDE
============================================================

WHAT THIS DOES
--------------

Creates a free website for your clan showing:
  - Live season countdown
  - Daily/Half-Hour/Hourly reputation gains for every member
  - Season goal progress (100K, 500K, 750K, 1M, 1.6M)
  - Click-to-sort, search filter, CSV export
  - Member Changes (who left, who joined)
  - Auto-updates every 30 minutes
  - Dark theme, mobile-friendly

Example: https://nixervo.github.io/Clairvoyant-Reps/

You don't need to code anything. Everything is done in your browser.
No passwords, no login, no servers. Entirely free.


STEP 1 — CREATE A GITHUB REPOSITORY
-----------------------------------

a) Go to https://github.com and log in (sign up if needed — it's free)
b) Click the green "New" button (top-left corner)
c) Name it: YourClanName-Reps (example: ShadowNinja-Reps)
d) Set to PUBLIC (required for free hosting)
e) Do NOT check "Add a README file"
f) Click "Create repository"


STEP 2 — DOWNLOAD THIS TEMPLATE
--------------------------------

a) All the files you need are in this folder
b) You already have them if someone shared this with you


STEP 3 — FIND YOUR CLAN ID
---------------------------

In the NinjaRift game on your phone:
a) Go to the "Clan" screen
b) Your Clan ID is shown at the top or in the clan profile
c) Write it down. Example: 2527


STEP 4 — CHANGE THE CLAN ID
----------------------------

a) Right-click the file "clan_snapshot.py" -> "Open with" -> "Notepad"
b) Find this line near the top (line 12):

    CLAN_ID = 9999

c) Change 9999 to your Clan ID. Example:

    CLAN_ID = 2527

d) Save (Ctrl+S) and close Notepad


STEP 5 — REPLACE THE LOGO (OPTIONAL)
-------------------------------------

a) Replace "clan_logo.png" with your own clan's logo
   - Must be named EXACTLY "clan_logo.png"
   - Square image, any size (132x132 recommended)

b) Replace "favicon.ico" with your own browser tab icon
   - Must be named EXACTLY "favicon.ico"

Skip this step if you don't have a logo.


STEP 6 — UPLOAD TO GITHUB
--------------------------

a) Go to your GitHub repository from Step 1
b) Click "uploading an existing file" OR "Add file" > "Upload files"
c) Drag ALL files and folders from this template into the upload box
d) Scroll down and click "Commit changes"


STEP 7 — ENABLE THE WEBSITE
----------------------------

a) In your repository, click the "Settings" tab (top-right)
b) Left sidebar -> click "Pages"
c) Under "Branch", select: main -> /(root)
d) Click "Save"
e) Wait 30 seconds. You'll see a blue box saying:
   "Your site is live at https://your-username.github.io/YourClan-Reps/"


STEP 8 — RUN THE FIRST SNAPSHOT
--------------------------------

a) Click the "Actions" tab at the top of your repository
b) Left sidebar -> click "Clan Snapshot"
c) Right side -> click "Run workflow" -> "Run workflow"
d) A yellow dot appears. Wait 2 minutes.
e) Open your website URL from Step 7.
f) You should see your clan's data!


IT'S DONE
---------

The script runs every 30 minutes automatically. You never need to
touch it again. The website updates itself.

Every day at 1PM GMT+8, a daily snapshot is saved to an Excel file.


CUSTOMIZATION (OPTIONAL)
------------------------

Edit "clan_snapshot.py" anytime to change:

    - Clan ID:    CLAN_ID = 9999
    - Rep goals:  GOAL_TIERS (look near line 20)
    - Timezone:   TARGET_TZ (line 16)
    - Season end: search for "datetime(2026,"

After editing, run the workflow again from the Actions tab.


TROUBLESHOOTING
---------------

Problem: Website not updating
Fix:    Go to Actions tab -> run the workflow manually

Problem: "No members found" or blank page
Fix:    Check your Clan ID is correct in clan_snapshot.py

Problem: Countdown shows "--"
Fix:    Click Actions -> Clan Snapshot -> Run workflow

Problem: Logo not showing
Fix:    File must be named EXACTLY "clan_logo.png" (lowercase)

Problem: Page shows 404
Fix:    Wait 2 minutes. GitHub Pages takes a moment to deploy.

Problem: Run keeps failing
Fix:    Go to Actions tab -> click the failed run -> copy the red
        error text and ask whoever shared this template for help.


HOW IT WORKS
------------

1. A small script runs on GitHub's free servers every 30 minutes
2. It reads your clan's public data from NinjaRift's API
3. It calculates rep gains and builds an HTML webpage
4. The webpage is hosted free on GitHub Pages
5. JavaScript on the page refreshes live data every 60 seconds

No game login, no passwords, no paid servers.
