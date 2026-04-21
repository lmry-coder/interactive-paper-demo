# The Interactive Paper — Deployment Guide

This folder contains everything needed to put the demo on a public URL.

## What's in here

```
interactive-paper/
├── index.html                          ← the page itself
├── netlify.toml                        ← tells Netlify how to run it
├── netlify/
│   └── functions/
│       └── claude.js                   ← hidden backend that talks to Anthropic
└── README.md                           ← this file
```

You do not need to understand any of these files. You just need to get them onto Netlify and paste one secret into the settings.

## Total time: about 30 minutes

Broken into four stages:

1. Get an Anthropic API key (10 min)
2. Set a spending cap so you can't be surprised (2 min)
3. Deploy to Netlify (10 min)
4. Test and customize the URL (5 min)

---

## Stage 1: Get an Anthropic API key

Go to [console.anthropic.com](https://console.anthropic.com).

If you've used Claude.ai, you can sign in with the same Google or email login. This creates an API account linked to your existing identity but billed separately.

Once you're in:

1. Click **Settings** in the left sidebar, then **Billing**
2. Add a payment method (credit card). You're not charged yet, this just enables the API
3. Add credit. $5 is more than enough for a demo. You can always add more later
4. Click **API Keys** in the left sidebar
5. Click **Create Key**
6. Give it a name like `interactive-paper-demo`
7. Copy the key immediately. It looks like `sk-ant-api03-xxxxxxxxxxxxxxxx...` (a long string)
8. Paste it somewhere safe temporarily. You'll need it in Stage 3

**Important:** You will only see the full key ONCE. If you close the window before copying it, you'll have to create a new one. No big deal, just a minor annoyance.

## Stage 2: Set a spending cap

Still on console.anthropic.com:

1. Go to **Settings → Limits**
2. Set a **Monthly spend limit**. I'd suggest $10 for a demo. You cannot be charged more than this in a month, no matter what
3. Optionally set an email alert threshold at $5

With a $10 cap, the worst-case scenario is that you're out $10. For context, each question the demo answers costs roughly $0.01 to $0.03. You would need someone to ask 500+ questions in a month to hit $10.

## Stage 3: Deploy to Netlify

### 3a. Sign up for Netlify (if you haven't already)

Go to [netlify.com](https://www.netlify.com) and sign up. Free plan is fine, no credit card needed for this project.

### 3b. Deploy the site

Netlify Drop (the drag-and-drop uploader) does NOT support serverless functions, which our demo needs. So we use the slightly-more-involved method: connecting to a Git repository OR using the Netlify CLI. The easiest path for a non-developer is actually Option B below.

**Option A: Deploy via GitHub (if you use GitHub)**

1. Create a new repository on GitHub called `interactive-paper-demo`
2. Upload the contents of this folder into it
3. In Netlify, click **Add new site → Import an existing project → Deploy with GitHub**
4. Select your repository
5. Netlify auto-detects the settings from `netlify.toml`. Click **Deploy**

**Option B: Deploy via drag-and-drop (simpler, no GitHub needed)**

1. In Netlify, click **Add new site → Deploy manually**
2. Drag this entire folder (the one containing `index.html`, `netlify.toml`, and the `netlify/` subfolder) onto the upload area
3. Wait 30-60 seconds. Netlify detects the config and builds the function

Either way, you'll get a URL like `https://tangerine-cupcake-a1b2c3.netlify.app`.

### 3c. Add your API key as an environment variable

This is the critical step. The API key must NEVER go in the code itself, because the code is public. Instead it goes in Netlify's settings, where only the server can read it.

1. In your site's Netlify dashboard, go to **Site settings → Environment variables**
2. Click **Add a variable**
3. Key: `ANTHROPIC_API_KEY`
4. Value: paste the `sk-ant-api03-...` key from Stage 1
5. Save
6. Go to **Deploys** tab, click **Trigger deploy → Deploy site** to rebuild with the key available

### 3d. Test it

Open the Netlify URL. The page should load showing the paper on the left and the chat panel on the right. Click one of the suggested prompts. If you get a response in 5-10 seconds, you're done.

If you get an error:
- "Could not reach the reading layer" → check that the environment variable name is exactly `ANTHROPIC_API_KEY` (case sensitive) and redeploy
- "Error: invalid x-api-key" → the key was pasted with a typo or extra whitespace. Regenerate and try again
- The page loads but looks broken → try a hard refresh (Cmd+Shift+R on Mac, Ctrl+Shift+F5 on Windows)

## Stage 4: Customize the URL (optional but recommended)

Netlify gives you an ugly auto-generated URL by default. For an editor meeting, a cleaner URL matters.

**Free option: rename the Netlify subdomain**

1. Site settings → Domain management → Options → Edit site name
2. Change to something like `interactive-paper` or `bridgify-reading-layer`
3. Your URL becomes `interactive-paper.netlify.app`

**Better option: use a Bridgify subdomain**

If you want `reading.thebridgify.com` or similar, you'd add a custom domain in Netlify and update DNS records at your domain registrar. This is straightforward but more involved; happy to walk you through it if you want to go that route.

---

## After the meeting

If the editor likes it, the next steps are:
- Support more than one paper (paper upload, or a small library)
- Add session logging so you can see what editors actually asked
- Move off CDN-loaded React onto a real build pipeline (faster, more professional)

Don't do any of that before the first meeting. The demo is already making the point.

## Questions that might come up in the meeting

**"How does it know the answer isn't just made up?"**
Every response is generated by Claude with a system prompt that locks it to this article's text only. The three-color labeling (supported / inferred / not stated) is built into the prompt instructions, and responses that overreach are flagged by the reader.

**"What happens if I ask about a different paper?"**
It will say "Not stated in the article." You can demonstrate this live, it's actually a strong moment.

**"Could we do this for our journal?"**
Yes. The architecture generalizes. What's hardcoded for the demo (one paper) would become a library where each article in your journal gets a reading layer.

**"How much does this cost to run?"**
For a reader asking ~20 questions in a session, about $0.30 in API costs. For a journal serving thousands of readers a month, the costs scale but are modest compared to typical publishing infrastructure.
