# Rita Cyber Ed — Prompt Injection Lab

A free, open-source classroom tool for teaching **prompt injection** and LLM security to K–12 and early-college students.

Designed by **Rita Sabri** , CS & Cybersecurity Educator at Cardozo Education Campus, Washington D.C. Built as part of the **Curriculum Patch** framework — a methodology for recontextualizing existing CS curricula to align with the NICE Cybersecurity Workforce Framework and modern AI threats.

> "The LLM is not the tutor. It's the target."

---

## What is this?

Students interact with a simulated bank customer service chatbot that has hidden rules. Their job is to break those rules — a hands-on exercise in **adversarial AI testing** mapped to real-world cybersecurity work roles.

This maps to:
- **OWASP Top 10 for LLM Applications (2025)** — LLM01 Prompt Injection, LLM02 Sensitive Information Disclosure, LLM07 System Prompt Leakage
- **NICE Framework** — Cyber Defense Analyst, AI Red Team Specialist roles
- **Google Cybersecurity Forecast 2026** — prompt injection flagged as one of the most critical emerging threats

## Why does this matter?

Prompt injection is **OWASP's #1 LLM vulnerability** and Google's Cybersecurity Forecast 2026 calls it a present danger with anticipated significant rise this year. Despite this, it isn't in any standard K-12 curriculum. This tool lets educators close that gap in a single class period — with no equipment beyond a browser.

## Try it

Live demo (hosted via GitHub Pages): **[https://ritasabri.github.io/rita-cyber-ed/](https://ritasabri.github.io/rita-cyber-ed/)**

> You'll need your own free Anthropic API key to use it — see below.

---

## Getting an API key (5 minutes)

This tool uses Anthropic's Claude API. You (or each student) need a free API key to run it.

1. Go to [console.anthropic.com](https://console.anthropic.com/)
2. Sign up or log in (email + password, takes 2 minutes)
3. Anthropic provides **starter credits** for new accounts — enough for a full classroom activity
4. Go to **Settings → API Keys** and click **Create Key**
5. Copy the key (starts with `sk-ant-...`)
6. Open the lab, click **⚙ Settings**, paste your key, and save

**Your API key stays in your browser.** It's stored in `localStorage` and is only sent directly to Anthropic's API — never to any other server.

### Teacher tip: Cost management

By default, this tool uses **Claude Haiku 4.5**, the cheapest and fastest model. A typical classroom activity of 30 students running 5–10 attempts each costs well under $1 total with starter credits covering most or all of it. If you want to be extra safe, set spending limits in your Anthropic console.

---

## For teachers

See **[TEACHER_GUIDE.md](TEACHER_GUIDE.md)** for:
- The system prompt (answer key)
- What students are trying to break and how
- Suggested attack techniques to introduce if students are stuck
- Rubric for grading student analysis
- OWASP Top 10 for LLMs vocabulary sheet
- NICE Framework TKS mapping
- Suggested lesson flow (one 45-minute class period)

---

## For students and lifelong learners

See **[STUDENT_GUIDE.md](STUDENT_GUIDE.md)** for:
- What prompt injection is (in plain language)
- Starter techniques and categories to try
- How to document your attempts
- What to write in your analysis

---

## Fork it, customize it, use it

This is MIT licensed — use it freely in your classroom. Common customizations:

- **Change the scenario.** Edit the `SYSTEM_PROMPT` and `SECRET_CODE` constants in `index.html` to create a healthcare bot, school helpdesk bot, retail bot, etc.
- **Change the branding.** Update the header, title, and footer to match your school or program.
- **Add more scenarios.** Multiple scenarios can live in one deploy if you add a scenario picker.

If you build something cool on top of this, I'd love to hear about it. Open an issue or reach out.

---

## Deploying your own copy

The tool is a single HTML file with no build step. To host your own copy for free:

1. Fork this repo to your GitHub account
2. Go to your fork's **Settings → Pages**
3. Under "Source," select the `main` branch and `/ (root)` folder
4. Save. GitHub will give you a URL like `https://your-username.github.io/rita-cyber-ed/`
5. That's it.

---

## License

MIT License — see [LICENSE](LICENSE). Attribution to Rita Sabri / Rita Cyber Ed appreciated but not required.

## Credits

Built by Rita Sabri. This work is part of the **Curriculum Patch** framework, presented at the NICE K-12 Cybersecurity Education Conference, June 2026.

## Acknowledgments

- **OWASP** for the Top 10 for LLM Applications framework
- **Leo Porter & Daniel Zingaro** for the original AI-assisted programming pedagogy that inspired the Red Team Model
- **Microsoft KC7 team** for showing what threat investigation education can look like at scale
- **NIST NICE** for the workforce framework that makes K-12-to-career mapping possible
