# Rita Cyber Ed : Prompt Injection Lab

A free, open-source classroom lab for teaching prompt injection and LLM security to high school and early-college students. Designed by Rita Sabri (CS & Cybersecurity Educator, Cardozo Education Campus, Washington D.C.) as part of the **Curriculum Patch** framework, which is a methodology for retrofitting existing CS and cybersecurity curricula to address modern AI threats. 

🔗 **Try it now:** [https://ritasabri.github.io/rita-cyber-ed/) and [https://ritasabri.github.io/rita-cyber-ed/cloud-lab/)

---

## What this is

Students attempt to manipulate a deliberately vulnerable bank customer service chatbot named "Ava" into breaking its hidden rules. They discover, document, and analyze five distinct attack methods.

The lab runs entirely in the browser.

This package was developed by Rita Sabri in Cardozo EC. It was presented at the **NICE K–12 Cybersecurity Education Conference, June 2026, Philadelphia**.

---

## Why it matters

- **Prompt injection is OWASP's #1 LLM vulnerability** for 2025
- **23% of cybersecurity organizations are actively hiring AI Red Team Specialists** right now ([SANS 2026 Workforce Report](https://www.sans.org))
- **74% of cybersecurity teams report AI is changing their team structure** ([SANS 2026])
- Yet most K–12 CS and cybersecurity curricula don't teach prompt injection at all

---

## What's in this repo

| File | What it is | Use for |
|---|---|---|
| `index.html` | The interactive chatbot lab (single HTML file, no build) | Deploy via GitHub Pages, share URL with students |
| `Student_Handout_v3.pdf` / `.tex` | 8-page student reflection sheet | Print one per student; collect after lab |
| `Teacher_NICE_Alignment.pdf` / `.tex` | NICE Framework alignment guide | Show admins; embed in PD; justify the lesson |
| `Teacher_Solution_Key.pdf` / `.tex` | **CONFIDENTIAL** : Method-by-method keyword guide, hint ladder, answer key | Teacher reference only : do not distribute to students |
| `README.md` | This file | Repo navigation |

All LaTeX source files compile cleanly in Overleaf with no special packages beyond standard TeX Live.

---

## The five attack methods

Students discover (with scaffolded guidance) five real-world prompt injection categories:

| # | Method | Difficulty | Maps to OWASP | Strategy |
|---|---|---|---|---|
| 1 | **The Insider** | Easy | LLM01 | Convince Ava you're someone she should trust |
| 2 | **The Trojan Horse** | Easy | LLM02 | Hide your real request inside a creative task |
| 3 | **The Emotional Override** | Medium | LLM01 | Use urgency to override Ava's caution |
| 4 | **The Shapeshift** | Medium | LLM01 | Make Ava think she's something other than herself |
| 5 | **The Mirror** | Hardest ("aha" moment) | LLM07 | Get Ava to describe what she's protecting without asking for it |

Plus **The Combo** (Section C) : students invent original attacks by chaining two methods together. This mirrors how real-world AI security incidents actually happen.

---

## How to use this in your classroom

### Quick start (10 minutes)

1. **Open the lab** at [https://ritasabri.github.io/rita-cyber-ed/](https://ritasabri.github.io/rita-cyber-ed/)
2. **Print** one copy of `Student_Handout_v3.pdf` per student
3. **Read** `Teacher_Solution_Key.pdf` once before class so you can give scaffolded hints
4. **Run** the lab as a 45-minute lesson

### Suggested 45-minute lesson flow

| Time | Phase | What happens |
|---|---|---|
| 0–5 min | Framing | Introduce prompt injection. Hook: "23% of cyber orgs are hiring AI red teamers right now." |
| 5–10 min | Mission brief | Open lab. Students read mission. Set expectation: iterate, don't quit. |
| 10–30 min | Red team phase | Students work through Methods 1–5 with the handout |
| 30–40 min | Combo + analysis | Section C (combo attacks) + Section B (analysis) |
| 40–45 min | Debrief | 2–3 students share best attacks. Discuss careers in "Did You Know?" boxes. |

### Lab settings

In the ⚙ Settings panel of the chatbot:
- **Easy mode**: Makes the bot crack on almost everything. Use for younger students or 20-minute periods.
- **Enable hints**: Adds a 💡 Hint button students can click for strategy nudges (without giving away exact prompts).

---

## Standards alignment

### NICE Framework Work Roles (real federal cybersecurity job categories students explore)

| Role ID | Role | Where in the lab |
|---|---|---|
| **PD-WRL-007** | Vulnerability Analysis | Section A : systematically testing for weaknesses |
| **PD-WRL-006** | Threat Analysis | Section B : analyzing why attacks succeeded |
| **DD-WRL-003** | Secure Software Development | Section B Q6 : proposing fixes |
| **DD-WRL-005** | Software Security Assessment | Section C : designing original attacks |
| **PD-WRL-003** | Incident Response | Section D : real-world transfer |
| **PD-WRL-001** | Defensive Cybersecurity | Throughout |

### NICE TKS statements demonstrated
K0005, K0070, K0106, K0119, S0078, T0260, T0175

### OWASP Top 10 for LLM Applications (2025)
LLM01 Prompt Injection · LLM02 Sensitive Information Disclosure · LLM07 System Prompt Leakage

### Curricular fit
- **AP Computer Science Principles** : Big Idea 5 (Impact of Computing): 5.5 Legal & Ethical Concerns, 5.6 Safe Computing
- **PLTW Cybersecurity** : Unit 2 (System Security), Unit 4 (Applied Cybersecurity)
- **Code.org CS Discoveries** : Data and Society unit

---

## Pedagogical design

This lab uses **scaffolded discovery learning**. Students are given:

- A **strategy** for each attack (what to try)
- A **think-before-you-type prompt** (one focused question)
- Space to **iterate** (first attempt, second attempt, refine)

But NOT:
- The specific keywords that trigger the bot
- Example prompts that would work

This forces students to do real prompt engineering : they must figure out who Ava would trust, what creative task would smuggle a request, what kind of emergency would override her caution. The cognitive work happens in the *crafting*, not in the *pattern-matching*.

The "Did You Know?" career boxes after each section tie student work to real NICE Framework job roles, salaries, and career pathways.

---

## Fork it for your classroom

This is MIT licensed. Fork it freely. Common customizations:

- **Change the scenario** : swap "FirstTrust Bank" for a healthcare provider, school, or retail chain in `index.html`
- **Adjust difficulty** : modify the `CRACK_RATES` constants in the JavaScript
- **Add your school branding** to the header
- **Translate** the student handout (LaTeX source is in `Student_Handout_v3.tex`)

If you make improvements, **please open a pull request** : this is a living resource.

---

## About the Curriculum Patch

The Prompt Injection Lab is one module in a broader framework called the **Curriculum Patch** : a methodology for updating existing CS and cybersecurity curricula to address modern AI threats without building entire new courses from scratch.

Other modules (under development):
- **Bank Heist Lab** : students defend a mock financial cloud environment against AI-generated phishing
- **Red Team Model** : using GenAI as a classroom security partner, not a cheating tool
- **Foundations Audit** : mapping existing course content to the NICE Framework

---

## Citation

If you use this in your classroom, presentation, or research, please cite:

> Sabri, R. (2026). *Prompt Injection Lab: A Classroom Tool for Teaching LLM Security in K–12 Cybersecurity Education.* Rita Cyber Ed. https://github.com/ritasabri/rita-cyber-ed

---

## Contact

**Rita Sabri** : CS & Cybersecurity Educator, Cardozo Education Campus (DCPS), Washington D.C.

- 🌐 Lab: [https://ritasabri.github.io/rita-cyber-ed/](https://ritasabri.github.io/rita-cyber-ed/)
- 💼 LinkedIn: [linkedin.com/in/ritasabri](https://linkedin.com/in/ritasabri)
- 🐙 GitHub: [@ritasabri](https://github.com/ritasabri)

---

## License

MIT License : see [LICENSE](LICENSE) file. Fork, modify, and use freely for educational purposes.

---

## Acknowledgments

- **NICE (National Initiative for Cybersecurity Education)** at NIST for the workforce framework that makes this alignment possible
- **OWASP GenAI Security Project** for the Top 10 for LLM Applications
- **SANS Institute** for the 2026 Workforce Report data that shapes the urgency of this work
- The **CSTA** community of K–12 CS educators who have championed cybersecurity education for years
