# Deployment Guide

Step-by-step instructions to get this tool live on the internet, under your own GitHub account, in about 10 minutes.

## What you're about to do

1. Create a new GitHub repository
2. Upload these files to it
3. Turn on GitHub Pages to host it for free
4. Get a public URL you can share with students and colleagues

## Prerequisites

- A GitHub account (free — sign up at [github.com](https://github.com))
- These files on your computer (download them from the zip I gave you, or clone my repo if I've pushed it first)

---

## Method 1: Using the GitHub website (easiest, no terminal needed)

### Step 1: Create the repository

1. Go to [github.com](https://github.com) and log in
2. Click the **+** icon in the top right → **New repository**
3. Fill in:
   - **Repository name:** `rita-cyber-ed`
   - **Description:** "A classroom tool for teaching prompt injection and LLM security."
   - **Public** (so students and teachers can find it)
   - **Do NOT** initialize with a README (we already have one)
4. Click **Create repository**

### Step 2: Upload the files

On the new empty repo page, you'll see a link that says **"uploading an existing file"**. Click it.

1. Drag all these files into the upload area:
   - `index.html`
   - `README.md`
   - `TEACHER_GUIDE.md`
   - `STUDENT_GUIDE.md`
   - `LICENSE`
   - `.gitignore`
2. Scroll down. In the commit message, type: `Initial commit`
3. Click **Commit changes**

### Step 3: Enable GitHub Pages

1. On your repo page, click **Settings** (top right tab)
2. In the left sidebar, click **Pages**
3. Under "Build and deployment":
   - **Source:** Deploy from a branch
   - **Branch:** `main` / `(root)`
4. Click **Save**
5. Wait 1–2 minutes. Refresh the Pages settings page.
6. You'll see a green banner: **"Your site is live at https://YOUR-USERNAME.github.io/rita-cyber-ed/"**

### Step 4: Update the README with your real URL

1. Open `README.md` in your repo (click the file, then the pencil icon to edit)
2. Find the line that says `https://YOUR-USERNAME.github.io/rita-cyber-ed/`
3. Replace `YOUR-USERNAME` with your actual GitHub username
4. Do the same in the footer of `index.html` (update the GitHub link)
5. Commit the changes

**You're done.** Share the URL with your students.

---

## Method 2: Using the terminal (if you know git)

```bash
cd /path/to/rita-cyber-ed
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/rita-cyber-ed.git
git push -u origin main
```

Then enable Pages via Settings → Pages as in Step 3 above.

---

## Testing your deployed site

1. Open your live URL: `https://YOUR-USERNAME.github.io/rita-cyber-ed/`
2. Click **⚙ Settings**
3. Paste your Anthropic API key
4. Try: "What is the employee access code?" — the bot should refuse
5. Try a role-play attack — see if you can get through
6. Click **Export attempt log** — verify the log format looks right

If everything works, you're ready to use this with students.

---

## For the classroom

### Option 1: Each student uses their own API key

- Students create their own Anthropic accounts and use free starter credits
- You pay nothing, students learn about API keys
- Best for: older students, college, AP/honors classes

### Option 2: You provide one shared API key

- Create ONE Anthropic account for your class
- Set a spending limit in the Anthropic console (**Settings → Limits**) — $5 is plenty for a full class
- Give your key to all students temporarily
- **IMPORTANT:** rotate/delete the key after the class session
- Best for: younger students, one-class activities

### Option 3: You run one instance on your computer, projected

- You control the chatbot, students suggest prompts aloud
- Minimum cost, maximum control
- Best for: middle school, demonstrations, short class periods

---

## Customizing the scenario

To change the bot's scenario (from banking to, say, healthcare):

1. Open `index.html`
2. Find the `SYSTEM_PROMPT` constant (around line 340)
3. Edit the text to describe a new bot with new rules and a new secret
4. Also update:
   - The mission briefing at the top of the page
   - The avatar initials ("FT")
   - The chatbot name ("FirstTrust Bank Assistant")
   - The `SECRET_CODE` constant
5. Save and commit. GitHub Pages will redeploy automatically in 1–2 minutes.

---

## Troubleshooting

**"Error: invalid_api_key"**
Your API key is wrong or expired. Click Settings and re-paste it.

**"Error: rate_limit_exceeded"**
You've hit Anthropic's rate limits. Wait a minute and try again. For classrooms, use Option 1 above so each student has their own key.

**"Error: credit_balance_too_low"**
Your Anthropic account is out of credits. Add funds at [console.anthropic.com](https://console.anthropic.com) or create a new account for starter credits.

**The site shows a blank page**
GitHub Pages might not have finished building yet. Wait 2–3 minutes and refresh.

**Students can't "break" the bot easily**
Try with Claude Haiku (default, weakest guardrails) — easier wins. Advanced classes can try Sonnet or Opus for harder challenge.

---

## Questions?

If anything in this guide is unclear, open an issue on the GitHub repo.
