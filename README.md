# MediCare Connect — Healthcare Support Platform
Made My Samaksh Parihar

**A full-featured NGO healthcare support web app with multi-API AI fallback.**

---

## 🚀 Live Demo
Deploy to Vercel/Netlify by dropping `index.html` — no build step needed.

---

## 📦 Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML5 / CSS3 / JavaScript (ES2022) |
| Fonts | Google Fonts — DM Serif Display + Inter + JetBrains Mono |
| Hosting | Vercel / Netlify / Firebase (static) |
| AI Model 1 | **Anthropic Claude** (claude-sonnet-4-6) |
| AI Model 2 | **Groq** (llama-3.3-70b-versatile) |
| AI Model 3 | **Google Gemini** (gemini-1.5-flash) |
| AI Model 4 | **OpenAI** (gpt-4o-mini) |
| AI Model 5 | **Cohere** (command-r-plus) |

---

## 🤖 AI / Automation Ideas Implemented

### 1. Multi-Model Chatbot with Automatic Failover
The core AI feature is a **5-model fallback chain**:
- Tries Claude → Groq → Gemini → OpenAI → Cohere in order
- If any model fails (API error, rate limit, invalid key), it silently moves to the next
- Visual API status panel shows which model is active/failed/ready
- Falls back to a curated local FAQ system if all APIs are unavailable
- A custom `SYSTEM_PROMPT` keeps all models in character as "HealthBot"

### 2. AI-Powered Patient Intake Analysis
When a patient submits a support request:
- The AI analyzes the urgency, description, and support type
- Generates a 3-sentence compassionate intake summary
- Suggests next steps and relevant resources
- Displayed inline on the form page

### 3. AI Auto-Response Generator
Contact form submissions trigger an AI-drafted response:
- Tailored to the specific inquiry type (Partnership, Donation, Press, etc.)
- Previewed on screen; can be sent via backend email integration

---

## 🏥 NGO Use Case

**MediCare Connect** simulates a real-world NGO deployment for:
- **Patient Registration** — intake form with urgency classification
- **Volunteer Onboarding** — skill matching, availability tracking
- **Community Queries** — 24/7 AI FAQ chatbot (no staff needed overnight)
- **Resource Allocation** — visual progress bars showing volunteer gaps

The multi-API design ensures **zero downtime** — critical for healthcare contexts where patients may need urgent guidance at any hour, regardless of which AI provider has an outage.

---

## 🔑 Setting Up API Keys

All keys are entered in the browser UI and stored **in memory only** (never persisted or transmitted anywhere other than the respective API).

| Provider | Get Key At |
|----------|-----------|
| Claude | https://console.anthropic.com |
| Groq | https://console.groq.com |
| Gemini | https://aistudio.google.com |
| OpenAI | https://platform.openai.com |
| Cohere | https://dashboard.cohere.com |

---

## 🚢 Deployment (Netlify — 30 seconds)

```bash
# Option 1: Drag & drop
# Go to https://app.netlify.com/drop and drag the index.html file

# Option 2: CLI
npm install -g netlify-cli
netlify deploy --prod --dir=. --message="MediCare Connect"
```

### Vercel
```bash
npx vercel --prod
```

---

## 📁 File Structure

```
healthcare-app/
└── index.html        # Entire app (self-contained, no dependencies)
└── README.md         # This file
```

---

## 🎨 Design System

- **Background:** Deep navy `#0a0f1e` with ambient gradient glows
- **Accent:** Sky blue `#38bdf8` (primary), Indigo `#818cf8` (secondary), Emerald `#34d399` (success)
- **Typography:** DM Serif Display (headings) + Inter (body) + JetBrains Mono (data/code)
- **Signature element:** Animated API status panel showing live model switching

---

## 🔒 Privacy Notes

- No patient data is stored server-side (pure static app)
- API keys never leave the browser session
- For production use, add a backend proxy to hide API keys from users

---

*Built for Misty's Healthcare NGO Support Challenge · 2025*
