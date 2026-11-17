# Leader-board-
ICT Leaderboard 
Quick update: no need to upload the logo — the PDF has it as vector artwork, so I'm extracting it directly (navy #1E2656, red #AF2024). Now pulling the logo out as a clean SVG.

The logo extracted cleanly from your PDF as vector art, so you don't need to upload anything. Next I'm checking the best way to publish the site, then I'll build it.

I'll build a branded static site with Production, Quarterly Bonus, and Activity tabs driven by a single JSON data file, plus an importer to convert your workbook into that format. Let me verify a few remaining data details first.

Now I'll write the importer, locating each section by title so it keeps working as you add months, and reconciling name variants like "M. Bazar"/"Michael B" and "Sara"/"Sara J."

Now writing the importer.

Data checks out—office totals match the sheet exactly. Now I'll validate the chart colors, then build the page.

Ramps pass the separation checks (the remaining flags only apply to multi-hue palettes). Writing the site now.

Fixing a few small things I spotted on review, then inserting the logo.

I'll fix three issues from the screenshots: the Book growth tile's incorrect total calculation, the phone tab bar clipping under the Rotate button, and the oversized podium on phone screens.

Now the README — how to update it today, how to host it, and the data contract the CRM feed will need to match.

Building the publishable copy and publishing it as a private page so you can see it live.

I've built the leaderboard site and published it as a private page:

**https://claude.ai/artifact/AgxjEUoUxrsgF1S1uk6oR2**

It's private for now. Your team can't open it until you share it from the page's Share menu.

**Your logo:** you don't need to upload it. The logo in your PDF was vector artwork, so I pulled it out directly. It's sharp at any size and gets a white-and-red version in dark mode. The colors are your navy (#1E2656) and red (#AF2024), and the navy/red stripe at the top comes from your documents.

**What's on it:**
- **Production (26 Prod tab):** five tiles at the top: production, policies sold, supp policies, supp premium and book growth. Each tile shows the office total, and clicking one ranks the agents by it. You can look at the year to date, a single quarter or a single month. There's a top 3, how far each agent moved since last month, a comparison with the same months of 2025, and a small month-by-month chart for each agent. Managers and "Other" are listed below the ranking but not ranked, the same as the sheet.
- **Quarterly Bonus (Qt Bonus tab):** the $71,626 earned so far in 2026, broken out by quarter, and how the bonus works (10% goal, 15%/24% rates, 15% goal from Q1 2027). It ranks agents by their 2026 bonus total and shows each quarter's qualification table. Q4 has no numbers in the sheet yet, so that tab shows supp premium written so far in Q4 instead.
- **Activity Scorecard (SC tabs):** pick a week, month or quarter, going back to April. Agents are ranked by percent of goal, since goals differ (15, 50 or 2 a week). Each agent also has a row of dots showing which of the last 8 weeks they hit their goal.
- **Rotate** button: switches between the three boards every 20 seconds, for an office TV.

**Getting ready for the CRM:** the numbers live in a separate data file that the page reloads every 10 minutes. For now, an import script builds that file from your workbook. It finds each section by its title, so adding months or agents won't break it. When the CRM is connected, it only has to produce that same file and the website doesn't change. The README describes the file's layout.

**Decision for you:** I rank production by health and life combined, which is what "Total as of 10/1" is. Your typed-in "2026 Ranking" looks closer to health only. Combined puts Josh at #2, because of his $125K in life. Want me to make health only the default, or add a switch between the two?

**Formula problems in the workbook:** the site does its own math, so these don't affect what it shows, but they're worth fixing in the sheet:
- The book-growth column ("Change over 2025") uses the 8/1 snapshot instead of 10/1.
- In the YoY Sales section, Josh's row is compared against Deuce's 2025 numbers, and Andrew's against Sara J.'s.
- Five weeks in SC Weekly calculate Josh's and Niki's % from the wrong goal cell.

The README lists all of these.

**Next step:** which CRM do you use? Once I know, I can work out how to pull these numbers from it automatically.

This session's computer gets wiped after a while, so download the zip I sent. It has the site, the data file, the import script and the README.
