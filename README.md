# GCBS Bot — Vercel Serverless Starter

This is a minimal server endpoint you can deploy to Vercel to power your GoldenCity BotSpot chatbot widget.

## Files
- `api/chat.js` — POST endpoint that accepts `{ message }` and returns `{ reply }` using OpenAI.
- `vercel.json` — pins Node 18 runtime (optional but recommended).
- `package.json` — uses the official `openai` SDK.

## Deploy Steps
1. Create a new GitHub repo named `gcbs-bot-vercel` and add these files.
2. In Vercel → Project → Settings → **Environment Variables**, add:
   - `OPENAI_API_KEY` = your OpenAI API key
   - `ALLOWED_ORIGINS` = https://goldencitybotspot.com,https://www.goldencitybotspot.com (or your domains)
3. Import repo into Vercel → Deploy.
4. Test the endpoint:
   ```bash
   curl -X POST https://YOUR-PROJECT.vercel.app/api/chat \
     -H "Content-Type: application/json" \
     -d '{"message":"Hello GCBS"}'
