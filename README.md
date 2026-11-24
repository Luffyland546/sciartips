Live site: https://luffyland546.github.io/sciartips/
Repository: https://github.com/Luffyland546/sciartips/

Question: How can a staff view make tip calculations transparent and provide a safe voice channel for vulnerable workers without exposing them to retaliation?

Part 1: The people

Internal (Sciar): Aoife Rennick, CEO. She needs a phone-first alpha she can defend to investors: "Make it work on a phone." and "Investors will ask what happens when staff complain about the owner" (messages/04-aoife.md).

External (Halloran's): Rafael, kitchen porter. He needs to see how his pay is counted without risk: "i dont understand how they count it" and "please dont say it was me who ask" (messages/01-rafael.md).

Cultural difference and accessibility: Rafael's first language is Portuguese and his "phone screen is broken" (messages/01-rafael.md), so the staff view uses one narrow column, large type, short sentences, and accepts any English.

Part 4a: Theory behind the build

Leadership: leader-member exchange (Graen and Uhl-Bien, 1995). It explains Rafael's silence: his bond with Declan ("he is good to me with my visa letter") is a personal exchange he will not risk, and Niamh's "they come to me" routes every problem through such bonds. It misses structure. After Mehmet left, Rafael's average weekly hours rose from 40.3 to 51.2, yet his average weekly tips rose only from €55.83 to €58.09 (payouts.csv, staff_id = S12, weeks 1-8 vs 9-12). That comes from the split rule, not from a relationship.

Culture: organisational silence (Morrison and Milliken, 2000). Niamh's "Nobody has ever complained" shows that no safe channel exists, not that people are satisfied. Kitchen porters (2 of 13 staff) worked 266 of the 348 hours that earned no points (payouts.csv, all rows).

Design choice: silence is rational when the listener holds power, so concerns go to Sciar only, name optional, with a receipt the sender can see and withdraw.

Competitive advantage (inferred): an owner-only rule makes Sciar a payment utility that rivals can copy. Transparency and safe voice are harder to copy but may cost owners like Declan, who wants the points table hidden.

Limit: both theories are interpretive. They cannot separate culture, language and visa dependence as causes of Rafael's silence.

Part 4b: Decision record

Decision 1: Aoife asked me to drop "raise a concern" (04-aoife.md). I changed it. Options: drop it; send concerns to the owner or floor manager; keep it, routed to Sciar only. Criteria: Rafael's safety, the investor question, honesty about a demo. Sciar-only won: Rafael fears Declan finding out, and Niamh already answered him once with "is the system" (01-rafael.md). It still serves Aoife's need: it answers "what happens when staff complain" with a private, owner-blind route. I would change my mind if Sciar could not reply within days, since an ignored channel is worse than none.

Decision 2: AI suggestion rejected: the market scan's "lead with the 34% retention statistic" (05-market-scan.md). Options: use it; use it labelled "AI estimate"; leave it out. Criteria: every number needs a source I can open, and the brief bars unsourced statistics. Leaving it out won: "No sources were attached." A source I could open, or Sciar's own retention data, would change my mind.

Bias I caught: Automation bias—I initially trusted the AI's confident statistics from 05-market-scan.md until I spotted "No sources were attached" and switched to relying only on verified figures from payouts.csv and takings.csv.

Part 4c: The Struggle (no AI)

When building the site for GitHub Pages (luffyland546.github.io/sciartips/), I first tried loading the data directly from the CSV files, which broke the page because relative file paths failed on the live site and the layout squished on phone screens. I fixed this by linking the JavaScript data files (payouts.js and takings.js) and adjusting the CSS so the tables stacked properly on mobile. I also had to manually verify the post-23:00 shift hours in payouts.csv because the AI got stuck in a repetitive loop asking me to re-upload files I had already shared, burning through all my Claude tokens without giving a clear answer. If I started again, I would test my live GitHub Pages link much earlier and verify the CSV data myself first. You can see my fix in commit 21193b6.

Assumptions and notes: all figures come from data/ (payouts.csv, 152 rows; takings.csv, 72 rows). The staff view picker is a demo only. Concerns are saved in the browser, not sent. The landing page makes no legal claim. AI sessions are in ai-log/.
