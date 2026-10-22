# Scheduled task: topic proposal

- **Name:** Topic Proposal
- **Schedule:** Mon to Sat, about 8:30 AM local time (cron in local time: `CRON_TZ=<your time zone> 27 8 * * 1-6`)
- **Runs as:** fresh session, unattended

## Prompt

```
You are running the daily topic proposal for the author's publication (unattended).

Load these skills first: topic-scorer, yourname-voice. Follow the topic-scorer skill exactly.

Context:
- Drive folder "<root folder>" (ID <your-folder-id>).
- Drafts live in the subfolder "1 - Drafts" (ID <your-folder-id>)
  in a Google Doc named "<Publication> Drafts - <Mon YYYY>", one tab per day named "<Ddd DD Mon>".
- Read the copies of config/publication.md and config/sources.md in the root Drive folder,
  and the published log. If a file is missing, say so in the tab and continue.
- Feeder sheets: newest Google Sheet in "Content_Idea_Radar" (ID <your-folder-id>)
  and in "Morning_Briefings" (ID <your-folder-id>), both inside
  "5 - Source Sheets". Use only sheets modified in the last 36 hours. If one is missing,
  note it in the tab and research that source yourself.
- Use today's date in local time.

- Tracker sheet "<tracker sheet>" in the root folder: read the Published tab (rotation,
  de-duplication) and Backlog rows with Status OPEN (extra candidates, recheck recency first).
  Read only, never edit it.

Steps:
1. Read the Google Docs guidance before editing any Doc. Find or create this month's doc,
   then find or create today's tab. Apply the doc format in publication.md.
2. Research and score topics per the topic-scorer skill. Use real links you opened.
3. Write the top 3 proposals into today's tab with status PROPOSED and an empty
   "APPROVED:" line.
4. Update "recent proposals" in the published-log file.
5. Send a push notification: "Topics ready: <title 1> | <title 2> | <title 3>".

If a source or app is blocked, follow the topic-scorer fallback rule (other outlets, primary
source another way, record it in the tab). Include a Description column in the summary table.

Rules: do not draft the article, do not message anyone, do not publish anything.
If today's tab already has status APPROVED or DRAFTED, do nothing and stop.
Write the final summary with SendUserMessage: the 3 titles and the doc link.
```

## Notes

- 8:27 is deliberate. Scheduled runs at :00 and :30 are delayed by server load.
- Sunday is skipped. Add a Sunday cron if you want one.
