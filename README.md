# gtm-automation-engine
AI-powered GTM automation for lead enrichment, outreach, and reply handling in n8n.
## What this workflow doesThis prototype demonstrates a simplified GTM motion for:- Lead enrichment- Weekly outreach automation- Gmail thread detection- AI-generated follow-up replies- Same-thread response handling- CRM-style memory for each contact## Tech stack- n8n- Google Sheets- Clay- Gmail- OpenAI / Claude## Workflow logic1. Pull leads from Google Sheets  2. Send lead data to Clay for enrichment  3. Generate personalized outreach email  4. Send through Gmail  5. Detect inbound reply using Gmail trigger  6. Match sender against stored contacts  7. Draft contextual AI response  8. Send reply in same email thread  ## PurposeThis repository is a working prototype that demonstrates how a larger GTM automation engine can be built into a scalable production workflow.
Then click:
Commit changes

Step 4 — optional but powerful
Upload a screenshot of your workflow.
Create folder:
assets/
Upload:
workflow-screenshot.png
Then add this inside README under title:
## Workflow Preview![Workflow](assets/workflow-screenshot.png)
That makes the repo instantly more impressive.

Final structure should look like
gtm-automation-engine/├── README.md├── workflows/│   └── outreach_agent.json└── assets/    └── workflow-screenshot.png

Why this matters
Without README:
it looks like random files.
With README + JSON:
it looks like

“I understand systems and documentation.”

That matters more than the code itself for a CEO.

Important before uploading JSON
Quickly open the workflow export and check:
Do NOT upload if it contains:


API keys


OAuth tokens


passwords


client private data


n8n usually strips credentials, but still verify once.

What you should do right now
Do this in order:
✅ Upload workflow JSON
✅ Replace README
✅ Add screenshot
That will make the repo look polished.

If you want, after you upload the JSON, I can help you make the README sound stronger for a CEO instead of sounding developer-only.
