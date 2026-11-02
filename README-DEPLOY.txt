TOOL QR CODES (FIX FOR "SITE IS PRIVATE")
  What was wrong: a tool sticker used the address the officer had open when the QR was made, and it opened the PIN-locked officer page. If that address was a private or preview Netlify address, people scanning from outside got "site is private".
  What is new: every tool QR now opens /scan.html, an open page with no PIN and no login. The phone scans the sticker and sees TOOL CHECKED OUT with the tool name, code, company and time. The tool is ticked on today's checklist and appears in the Operations Officer > Inventory tab ("Tools checked out today" list and a CHECKED OUT time next to the tool).
  DO THIS ONCE:
    1. Netlify > your site > Site configuration > Access & security > Visitor access: make sure NO password or "private" setting is on. Use the main site address, not a deploy-preview or branch address (those contain "--").
    2. Open public/config.js and put your public address in TCS_PUBLIC_URL, e.g. window.TCS_PUBLIC_URL = "https://your-site.netlify.app";
    3. Deploy, then open Operations Officer > Inventory > QR / Download and print NEW stickers. Old stickers still carry the old address and will keep failing if that address is private.
  The QR window warns in red if the address looks private or temporary.
  Special tools and parts QR codes now also use the public address (special tools open the full special-tool screen; parts still ask Top Management for the code).



WHAT'S NEW IN THIS VERSION
  CEO War Room: new Finance Room button above the first pie chart (invoices, bills, bank, VAT, cash flow, AI advisor, PDF report).
  MSG: Tumi (mechanic) and Rebecca (receptionist) added automatically the first time any page opens after deploy.
  After deploying, open the CEO page once so the new staff save to the shared system.
  Operations Officer: new "Required reports" tab (RCFA, QCP Data Book, FAT, Section 31, lifting inspections, warranty provisioning, inventory valuation) with due dates, PDFs and Send to CEO.
  Every PDF and ZIP now saves properly: Windows downloads straight to Downloads; iPhone and Android open the Save / Share sheet (Save to Files, WhatsApp, email) with Download and Open buttons as backup.
  Leaderboard & rewards replaces the keypad button on the staff page (points, ranks, race diagram, reward claims approved by the officer).
  NEW 4th page for the warehouse tablets: /4_Warehouse_Entrance_Keypad.html opens straight to the PIN pad and logs who arrived, when and where. Manual clock-in stays on the staff page.
  Live Floor board (CEO + Operations), CEO-only rewards with collect banner on every terminal, best-company alerts every Friday 16:00 and month end 16:00. Warehouse keypad page ignores the system lock.

FIX + NEW IN THIS BUILD
  Fixed: the reward / live-board code the pages called was missing, which would have crashed every page. It is now built in.
  Warehouse keypad page: opens straight to the PIN pad. No splash, no system-lock screen, no device-block screen.
  LIVE FLOOR diagram (CEO War Room and Operations Officer): live ring of who is on site, per-team tiles, staff bubbles, jobs done / open, tools out, urgent parts, issues, earnings race (Week / Month).
  CEO ONLY: a "Reward <name>" button appears under the KLB team and the MSG team for the top performer. Pressing it shows a flashing "<name> MUST come and collect their reward" banner on every terminal, including the warehouse keypad.
  When the person has collected, the CEO presses "Collected - check out" in the Rewards panel and the banner disappears everywhere.
  Reward rules (CEO > Rewards > Reward rules): weekly, monthly or both; Rand for each job, speed, tools returned, on-time, late, missing or broken tools, theft, laziness, disrespect, non-compliance, commendation, safety, warning, incident. Press Save rules and the board and alerts follow them.
  CEO alert when someone reaches the Rand amount the CEO set, and a best-company alert every Friday and at month end at the time the CEO set (default 16:00). The CEO can reward the whole winning team from that alert.
  Behaviour log (Operations) has new kinds: Theft, Laziness, Disrespect, Non-compliance. They count against the person's Rand.
  The best-company alerts are created the first time any page is open after the time passes (a free Netlify site cannot run a clock by itself). Keep the CEO page open or installed on the phone with alerts on.

FIX IN BUILD 104
  Operations Officer > Employees tab no longer crashes ("Script error") when someone was clocked in on a previous day and never clocked out. They now show "Clocked in <date/time> - never clocked out".
  Staff codes (set once, first page open after deploy): Takalani 7790, Evans 3677, Tumi 6214, Rebecca 8352, Monic 5148, Refilwe 9263.
  The grey "System locked" screen only accepts the Top Management code 8910. Staff codes are for the keypad / staff login.
