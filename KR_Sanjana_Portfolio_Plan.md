# K R Sanjana — Portfolio Website Implementation Plan

---

## Overview

A professional, recruiter-friendly single-page portfolio website built as a **single HTML file** (HTML + CSS + JS inline), with a **separate AI-powered chatbot page**. Clean corporate aesthetic, smooth navigation, and fully static — no backend needed.

---

## Tech Stack

| Layer | Choice | Reason |
|---|---|---|
| Structure | HTML5 | Single-file, no build tools needed |
| Styling | CSS3 (inline in `<style>`) | No external dependency |
| Interactivity | Vanilla JavaScript | Lightweight, no framework overhead |
| AI Chatbot | Anthropic API (`claude-sonnet-4-6`) via fetch | Powers the "Ask Me" chatbot |
| Fonts | Google Fonts — Inter | Professional, recruiter-friendly |
| Icons | Font Awesome CDN | Skill badges, social links |

---

## File Structure

```
portfolio/
│
├── index.html          ← Main portfolio (single file)
└── chatbot.html        ← AI chatbot page ("Ask me anything")
```

---

## Part 1 — `index.html` (Main Portfolio)

### Section Breakdown

---

### 1. Hero / About Me

- **Full name** — K R Sanjana (large, bold heading)
- **Tagline** — "AI/ML Engineer | NLP | Deep Learning | LLMs"
- **Profile photo placeholder** — `<img src="photo.jpg" alt="K R Sanjana" />` ← *replace `photo.jpg` with your actual image file*
- **One-line intro** — Adapted from your resume objective, tightened for impact
- **CTA Buttons** — `Download Resume` | `View Projects` | `Chat with AI Me →`
- **Social links row** — LinkedIn, GitHub, HackerRank, Email

> ✏️ **Editable:** The objective line will be rewritten to be punchy and recruiter-focused (removing filler phrases).

---

### 2. Skills

Grouped into visual badge cards (not bullet lists):

| Group | Skills |
|---|---|
| Languages | Python, SQL, OOP |
| ML / DL | scikit-learn, TensorFlow, Keras, CNN, Transfer Learning |
| NLP & LLMs | NLTK, TF-IDF, Word2Vec, RAG, Prompt Engineering |
| Data & Viz | NumPy, Pandas, Matplotlib, Seaborn |
| Tools | Docker, n8n, Jupyter, PyCharm |
| Databases | MySQL |

Each skill rendered as a pill/chip badge. Section uses a 3-column responsive grid.

---

### 3. Experience

Two cards, styled as a vertical timeline:

**Card 1 — AI Intern, Duroflex Pvt Ltd** *(Jan 2026 – Present)*
- AI Call Analyzer (speech-to-text + NLP)
- Sales forecasting models
- Text-to-SQL modules
- n8n workflow automation

**Card 2 — AI Intern, NKB Playtech Pvt Ltd** *(Oct 2025 – Jan 2026)*
- SAM3-based component detection pipeline (~40% annotation reduction)
- 5+ pretrained model experiments (15% accuracy improvement)
- Scalable video dataset workflows

> ✏️ **Editable:** Bullet points can be reviewed/reworded before final build if anything feels overclaimed or needs more precision.

---

### 4. Projects

Three project cards in a grid layout. Each card has:
- Project title
- 2–3 line description (recruiter-scannable)
- Tech tags (e.g., `Python` `CNN` `TensorFlow`)
- GitHub button (links to your repo)

**Projects:**

| # | Title | Key Highlight |
|---|---|---|
| 1 | AI Casino Pipeline | SAM3 detection, 1000+ frames, 5+ model experiments |
| 2 | NIKE vs ADIDAS Logo Detection | CNN, 92%+ validation accuracy, end-to-end pipeline |
| 3 | Duplicate Question Pairs Detection | NLP, TF-IDF + Word2Vec, Random Forest F1: 0.83 |

> ✏️ **Editable:** Descriptions will be written fresh — you can review and flag anything that needs correction before the file is generated.

---

### 5. Certifications

Simple horizontal card row:

- **Data Science & Software Testing** — Palle Technologies, Bengaluru (2025)
- **Python (Basic)** — HackerRank (2023) ← with link to certificate

---

### 6. Contact / Social Links

Clean footer-style section:

- Email: krsanjana13@gmail.com
- LinkedIn, GitHub, HackerRank icon links
- Small note: "Open to full-time AI/ML Engineer roles"

---

## Part 2 — `chatbot.html` (AI-Powered Chatbot)

### Concept

A separate page titled **"Ask Me Anything — AI Version of Sanjana"**.  
Visitors type questions like *"What projects have you done?"* or *"Are you open to relocation?"* and the chatbot responds **in first person as Sanjana**, powered by the Anthropic API.

### How It Works

1. A detailed **system prompt** is hardcoded in the JS — it contains all your resume facts (experience, skills, projects, education, goals)
2. User types a question in a chat input box
3. A `fetch()` call hits `https://api.anthropic.com/v1/messages` with `claude-sonnet-4-6`
4. Response streams back and appears in the chat UI as "Sanjana"
5. No backend — runs entirely in the browser

### Chatbot UI Layout

```
┌─────────────────────────────────────────┐
│  🤖 Chat with AI Sanjana               │
│  "Ask me about my projects, skills..." │
├─────────────────────────────────────────┤
│                                         │
│  [AI Sanjana]: Hi! I'm Sanjana...      │
│                                         │
│  [You]: What projects have you built?  │
│                                         │
│  [AI Sanjana]: I've built three main.. │
│                                         │
├─────────────────────────────────────────┤
│  [ Type your question...     ] [Send]  │
└─────────────────────────────────────────┘
```

### System Prompt Strategy

The system prompt will be written to:
- Speak **in first person** ("I am Sanjana, an AI/ML engineer...")
- Cover all resume facts accurately
- Deflect anything outside the resume scope gracefully ("I'd prefer to discuss that in person!")
- Maintain a professional, warm tone

> ⚠️ **Note on API Key:** The chatbot needs your Anthropic API key entered in the HTML file (in a `const API_KEY = "sk-..."` variable). This is fine for personal/demo use — do not host this publicly with a real key exposed.

---

## Visual Design Spec

| Element | Style |
|---|---|
| Color palette | White background, Navy `#1a2e4a` headings, Accent blue `#2563eb` |
| Font | Inter (Google Fonts) |
| Cards | Light shadow, 8px border radius, subtle hover lift |
| Section spacing | Generous padding, clear visual hierarchy |
| Mobile | Responsive grid (collapses to 1-col on mobile) |
| Nav | Sticky top navbar with smooth scroll to sections |

---

## Implementation Steps (for when you're ready to build)

1. **Confirm this plan** — flag any section content you want changed
2. **Provide your photo** — drop the image file name, it'll be placed in the Hero
3. **Build `index.html`** — full single-file portfolio generated
4. **Review content** — especially project descriptions and experience bullets
5. **Build `chatbot.html`** — AI chatbot page with system prompt based on your resume
6. **Add your API key** — paste your Anthropic key into the chatbot file
7. **Deploy** — drag both files to GitHub Pages or Netlify (free, takes 2 min)

---

## What to Prepare Before Building

- [ ] Your photo filename (e.g., `sanjana.jpg`)
- [ ] GitHub repo links for the 3 projects
- [ ] LinkedIn profile URL
- [ ] HackerRank profile URL
- [ ] Certificate link for HackerRank Python (already in resume)
- [ ] Anthropic API key (for chatbot only)
- [ ] Any corrections to project descriptions or experience bullets

---

*Plan version: June 2026 | Ready to build on your go-ahead.*
