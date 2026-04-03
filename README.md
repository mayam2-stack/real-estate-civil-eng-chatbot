# Diyar Aloula AI Chatbot Team / فريق ديار الأولى الذكي

A team of 5 bilingual AI agents that help manage a real estate development company's daily operations — from competitor research and BOQ tracking to AutoCAD drawing management and feasibility analysis.

Built on [OpenClaw](https://openclaw.ai), an open-source autonomous AI agent framework. You interact with the team through **Telegram** on your phone, in **Arabic or English**.

---

## The Team / الفريق

| Agent | Name | Role |
| ----- | ---- | ---- |
| 🎯 **Nadia** (نادية) | Chief of Staff | Your main contact. Routes questions to the right specialist. |
| 🔍 **Tariq** (طارق) | Research & BD | Competitor analysis, market intel, investor leads. |
| 📊 **Layla** (ليلى) | Data & Sheets | BOQ trackers, contractor contacts, payment schedules. |
| 🏗️ **Khalid** (خالد) | Technical | AutoCAD drawings, structural models, project schedules. |
| 💰 **Sara** (سارة) | Feasibility | Cost estimation, revenue projections, ROI analysis. |

**You only talk to Nadia.** She delegates to the others automatically.

---

## Quick Start / البداية السريعة

See [SETUP-GUIDE.md](SETUP-GUIDE.md) for a complete step-by-step installation guide (no coding experience needed).

**Summary:**

1. Open Terminal on your Mac
2. Install OpenClaw
3. Run `openclaw onboard` — it walks you through setup
4. Connect your Telegram bot
5. Text Nadia and start working

---

## Project Structure / هيكل المشروع

```text
├── SOUL.md              ← Nadia's personality & instructions
├── AGENTS.md            ← Global rules all agents follow
├── MEMORY.md            ← Long-term memory (agents fill this)
├── HEARTBEAT.md         ← Auto-recovery monitor
├── SETUP-GUIDE.md       ← Installation guide (start here!)
├── agents/
│   ├── tariq/           ← Research agent config
│   ├── layla/           ← Data agent config
│   ├── khalid/          ← Technical agent config
│   └── sara/            ← Feasibility agent config
├── data/                ← YOUR project files (AutoCAD, Excel, PDFs, etc.)
├── intel/               ← Tariq's research output
├── sheets/              ← Layla's data summaries
├── technical/           ← Khalid's technical reports
├── feasibility/         ← Sara's financial analysis
└── memory/              ← Daily activity logs
```

The `data/` folder is **your workspace** — put your project files there however you like. The agents scan it automatically each session and adapt.

---

## What It Can Do / ايش يقدر يسوي

- **Track AutoCAD drawings** across buildings and disciplines (STR, ARCH, MEP)
- **Monitor competitors** in KSA and Bahrain real estate markets
- **Manage BOQ data**, contractor contacts, and payment schedules
- **Analyze feasibility** with cost breakdowns and revenue projections
- **Cross-reference structural files** (ETABS, foundations, PT slabs, drawings)
- **Work bilingually** — ask in Arabic, get answers in Arabic. Same for English. Mix them.
- **Remember things** — tell Nadia "تذكّري إن..." and she'll store it for next time

---

## What It Cannot Do / ايش ما يقدر يسوي

- Cannot open `.dwg` files to see drawing contents (but can read file names, dates, and track revisions)
- Cannot extract `.rar`/`.zip` archives (but reads archive names for delivery dates)
- Cannot browse the internet in real-time without API integrations
- Cannot modify your project files in `data/` — it only reads them

---

## Requirements / المتطلبات

- macOS (any Mac)
- Internet connection
- Telegram app (free)
- Anthropic API key (for the AI model — [get one here](https://console.anthropic.com/))

---

## License

This project configuration is provided as-is for personal use by Diyar Aloula (ديار الأولى العقارية).
