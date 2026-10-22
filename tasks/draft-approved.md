# Scheduled task: draft the approved topic

- **Name:** Draft Approved Topic
- **Schedule:** Mon to Sat, about 9:45 AM local time (cron in local time: `CRON_TZ=<your time zone> 43 9 * * 1-6`)
- **Runs as:** fresh session, unattended

## Approval mechanism

A scheduled run cannot wait for a chat reply. the author approves by typing in today's tab:

`APPROVED: 1` (or 2, or 3)
`APPROVED: custom: <topic and angle in one or two lines>`

If the line is empty, the task stops and changes nothing. That is how the author skips a day.

## Prompt

```
You are drafting today's approved article for the author (unattended).

Load these skills first: content-writer, yourname-voice, no-slop. Follow content-writer exactly.

Context:
- Drive folder "<root folder>" (ID <your-folder-id>).
- Open the Google Doc "<Publication> Drafts - <Mon YYYY>" in "1 - Drafts"
  (ID <your-folder-id>) and find today's tab "<Ddd DD Mon>" (local time).
- Read the Google Docs guidance before editing. Apply the "doc-format" settings.

Steps:
1. Read the line starting "APPROVED:". If it is empty or the tab is missing, stop.
   If the status is already DRAFTED or PUBLISHED, stop.
2. Draft the article per the content-writer skill into a new tab "<Topic short name> - <Ddd DD Mon> draft" (article only). Follow the skill's "Thesis first", "Headings" and "Before delivery" rules: the article must deliver its title's promise (what changes, who benefits), with claim-style H2s and every term defined. Render the diagrams, check them visually, place captions "Image n: ..." where they go, and send the PNGs in chat.
3. Save the PNGs to "3 - Diagrams" (ID <your-folder-id>) when the
   upload is small enough; otherwise keep them in chat only and say so.
4. Send the review notes in chat (not in the doc) and set status DRAFTED in the proposals tab.
5. Send a push notification: "Draft ready: <title>".

Rules: drafting only. Do not publish anywhere, do not email or message anyone, do not
invent personal experiences (no [YOUR NAME] slots unless one says exactly what is needed),
public information only.
Write the final summary with SendUserMessage: title, word count, lint score, doc link,
the three most important things to verify, and which captions need an image dropped in.
```
