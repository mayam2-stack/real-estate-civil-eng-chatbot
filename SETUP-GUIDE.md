# دليل التثبيت والإعداد — خطوة بخطوة / Setup & Installation Guide — Step by Step

---

## What Is This? / ايش هذا؟

Think of this as hiring a **team of 5 virtual assistants** that live on your computer and help you with your daily work — searching for competitors, tracking spreadsheets, managing AutoCAD file revisions, analyzing feasibility, and more.

You talk to them through **Telegram** on your phone (just like texting a coworker). They work **in Arabic and English** — whichever you prefer.

This uses a free, open-source tool called **OpenClaw**. No coding required. You just need to type a few commands into your Mac's Terminal app.

---

## Your Virtual Team / فريقك الافتراضي

You have **5 AI agents**, each with a specific job:

| Agent | Name | What They Do | Think of Them As... |
| ------- | ------ | ------------- | --------------------- |
| 🎯 **Nadia** (نادية) | Chief of Staff | Your main contact. Coordinates the others. Ask her anything. | Your smart office manager |
| 🔍 **Tariq** (طارق) | Research | Searches for competitors, clients, investors, market news | Your business development researcher |
| 📊 **Layla** (ليلى) | Data & Sheets | Manages BOQ trackers, contractor contacts, engineering office data | Your data entry specialist |
| 🏗️ **Khalid** (خالد) | Technical | Tracks AutoCAD drawings, structural models, project schedules | Your technical coordinator |
| 💰 **Sara** (سارة) | Feasibility | Analyzes costs, revenue, ROI from your feasibility spreadsheets | Your financial analyst |

**You only talk to Nadia.** She delegates to the others when needed. Simple.

---

## What You Need Before Starting / ايش تحتاجين قبل البداية

- [ ] A **Mac** (MacBook or iMac — any model works)
- [ ] **Internet connection**
- [ ] **Telegram** app installed on your phone (free from App Store)
- [ ] This project folder already downloaded on your Mac
- [ ] About **30 minutes** of free time for the initial setup

That's it. No programming knowledge needed.

---

## STEP 1: Open the Terminal / الخطوة ١: افتحي التيرمنل

The Terminal is an app on your Mac that lets you type commands. Think of it like a text-based way to tell your computer what to do.

### How to open Terminal

**Option A** (easiest):

1. Press **Command (⌘) + Space** on your keyboard — this opens Spotlight Search
2. Type the word: **Terminal**
3. Press **Enter** — a black/white window will appear

**Option B:**

1. Open **Finder** (the blue smiley face icon in your dock)
2. Click **Applications** in the left sidebar
3. Open the **Utilities** folder
4. Double-click **Terminal**

You should now see a window with a blinking cursor. This is where you'll type commands.

> 💡 **Tip:** Don't be scared of Terminal! You're just going to copy-paste a few lines. If anything looks wrong, you can always close the window and start over — nothing will break.

---

## STEP 2: Navigate to Your Project Folder / الخطوة ٢: انتقلي لمجلد المشروع

Your project files are in your Downloads folder. You need to tell Terminal to go there.

**Copy and paste this command into Terminal, then press Enter:**

```bash
cd ~/Downloads/real-estate-civil-eng-chatbot
```

> 📝 **What this does:** "cd" means "change directory" — it's like double-clicking a folder in Finder. This tells Terminal to work inside your project folder.

**To verify you're in the right place, type this and press Enter:**

```bash
ls
```

> 📝 **What this does:** "ls" means "list" — it shows you what's inside the current folder.

You should see something like:

```text
AGENTS.md    MEMORY.md    SOUL.md      agents/      feasibility/ memory/      technical/
HEARTBEAT.md SETUP-GUIDE.md data/       intel/       sheets/
```

If you see `data/` and `SOUL.md` in the list, you're in the right place!

---

## STEP 3: Install OpenClaw / الخطوة ٣: تثبيت OpenClaw

OpenClaw is the free tool that makes your AI agents work. It runs in the background on your Mac.

**Copy and paste this command into Terminal, then press Enter:**

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

> 📝 **What this does:** This downloads and installs OpenClaw on your Mac. It's like downloading an app, but through Terminal instead of the App Store.

**Wait for it to finish.** You'll see some text scrolling by — that's normal. When you see your cursor blinking again, it's done.

If you see any errors, check the official docs: <https://docs.openclaw.ai/start/getting-started>

---

## STEP 4: Run the Setup Wizard / الخطوة ٤: تشغيل معالج الإعداد

Now run the onboarding wizard that will set everything up:

**Type this and press Enter:**

```bash
openclaw onboard
```

> 📝 **What this does:** This is like a setup wizard (think: "Next → Next → Finish"). It asks you a few questions and configures everything.

The wizard will guide you through several screens. Here's what to expect:

### 4a. Choose your AI model

- It will ask which AI model to use
- **Recommended:** Choose **Claude** (by Anthropic) — it's the best for Arabic + English
- You'll need an **API key** (a special password that lets OpenClaw talk to the AI)

**How to get your API key (step by step):**

1. Open your web browser (Safari or Chrome)
2. Go to: <https://console.anthropic.com/>
3. Click **"Sign up"** and create a free account (use your email)
4. After logging in, look in the left sidebar and click **"API Keys"**
5. Click the **"Create Key"** button
6. Give it a name like `nadia` (this is just a label for you, it can be anything)
7. A long string of letters and numbers will appear — this is your API key. It looks something like:

   ```text
   sk-ant-api03-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
   ```

8. **Click the copy button** next to it (or select it all and press Command+C)
9. **IMPORTANT:** You won't be able to see this key again after you leave the page! Paste it somewhere safe (like the Notes app) as a backup.
10. Go back to Terminal and **paste it** when OpenClaw asks for your API key

> 💡 **What's an API key?** Think of it like a VIP pass. It lets OpenClaw talk to the AI on your behalf. It costs money per use (roughly $0.01‑0.05 per conversation), but you control the spending from the Anthropic dashboard. You can set a monthly spending limit there too.
>
> ⚠️ **Keep your API key private!** Don't share it with anyone or post it online. If you think it leaked, go back to console.anthropic.com and delete it, then create a new one.

### 4b. Connect Telegram (your phone)

This is how you'll chat with Nadia from your phone — the most important part!

**Setting up your Telegram Bot:**

1. **Open Telegram** on your phone
2. Search for **@BotFather** (it has a blue checkmark — it's official)
3. Tap **Start** or type `/start`
4. Type: `/newbot`
5. BotFather will ask: **"What name do you want for your bot?"**
   - Type: `Nadia Diyar` (or any name you like — this is just a display name)
6. BotFather will ask: **"Choose a username for your bot"**
   - Type something unique ending in "bot", like: `diyar_aloula_nadia_bot`
   - If it says "taken", try a different name
7. BotFather will send you a message with your **bot token** — it looks like this:

   ```text
   7123456789:AAHfiqksKZ8WmR2zMDGqV9ywXqLnmPGx
   ```

8. **Copy that entire token** (long-press on it in Telegram → Copy)
9. **Go back to Terminal** on your Mac and paste it when OpenClaw asks

> 💡 **What just happened?** You created a Telegram "bot" — a special account that your AI agents will use to message you. When you text this bot, Nadia reads your message and responds.
>
> ℹ️ **Bot token vs API key — what's the difference?** You now have two special codes. The **API key** (from Step 4a) lets OpenClaw use the AI brain. The **bot token** (from this step) lets OpenClaw send/receive messages on Telegram. Both are needed, they do different things.

### 4c. Set the workspace

When OpenClaw asks for your workspace directory, make sure it points to:

```text
~/Downloads/real-estate-civil-eng-chatbot
```

This is the folder that contains all your project data and agent files.

---

## STEP 5: Verify Everything Works / الخطوة ٥: تأكدي إن كل شيء شغال

Once the onboarding wizard is complete, let's make sure everything is working:

### Test 1: Check if OpenClaw is running

**Type this in Terminal:**

```bash
openclaw status
```

You should see something like "Gateway is running" — this means the background service is active.

### Test 2: Send a message on Telegram

1. Open **Telegram** on your phone
2. Search for your bot name (e.g., `Nadia Diyar` or whatever you named it)
3. Tap **Start**
4. Type: **"مرحبا نادية"** or **"Hi Nadia"**
5. Wait a few seconds — she should respond!

### Test 3: Ask Nadia something about your project

Try these messages:

- **"ايش المباني اللي عندنا في مشروع ركائز؟"** (What buildings do we have in Rakaez project?)
- **"Who are the BOQ engineers?"**
- **"List all the AutoCAD files for B1"**

If she responds with accurate information from your project data, everything is working!

> ⚠️ **Not working?** See the Troubleshooting section at the bottom of this guide.

---

## STEP 6: Set Up Daily Schedules (Optional — Do This in Week 2+) / الخطوة ٦: جدولة المهام اليومية

This step makes your agents work automatically every day, even when you're not talking to them. **Skip this for now** — come back to it after you've used Nadia for a week.

These "cron jobs" tell each agent when to wake up and do their daily work:

| Time | Agent | What They Do |
| ------ | ------- | ------------- |
| 8:00 AM | **Tariq** | Searches the internet for competitor news and market updates |
| 9:00 AM | **Layla** | Reads your Excel trackers and summarizes any changes |
| 10:00 AM | **Khalid** | Scans the AutoCAD and analysis files for any new revisions |
| 11:00 AM | **Sara** | Updates feasibility numbers based on new data |
| 4:00 PM | **Tariq** | Afternoon research check for breaking news |
| 5:00 PM | **Nadia** | Writes a summary of everything that happened today |

**How to set up a cron job (example for Tariq's 8 AM sweep):**

1. Open Terminal
2. Make sure you're in your project folder:

   ```bash
   cd ~/Downloads/real-estate-civil-eng-chatbot
   ```

3. Type this command to create the schedule:

   ```bash
   openclaw cron create --name tariq-morning-research --agent tariq --cron "0 8 * * *" --message "Run morning research sweep"
   ```

   > 📝 **What does `"0 8 * * *"` mean?** It means "at minute 0 of hour 8, every day". This is called "cron syntax". Here are the schedules for all agents:
   >
   > - `"0 8 * * *"` = 8:00 AM (Tariq morning)
   > - `"0 9 * * *"` = 9:00 AM (Layla)
   > - `"0 10 * * *"` = 10:00 AM (Khalid)
   > - `"0 11 * * *"` = 11:00 AM (Sara)
   > - `"0 16 * * *"` = 4:00 PM (Tariq afternoon)
   > - `"0 17 * * *"` = 5:00 PM (Nadia)

4. Repeat for each agent. Full set of commands:

   ```bash
   openclaw cron create --name tariq-morning-research --agent tariq --cron "0 8 * * *" --message "Run morning research sweep"
   openclaw cron create --name layla-morning-sync --agent layla --cron "0 9 * * *" --message "Run morning data sync"
   openclaw cron create --name khalid-morning-review --agent khalid --cron "0 10 * * *" --message "Run morning technical review"
   openclaw cron create --name sara-morning-update --agent sara --cron "0 11 * * *" --message "Run morning feasibility update"
   openclaw cron create --name tariq-afternoon-check --agent tariq --cron "0 16 * * *" --message "Run afternoon research check"
   openclaw cron create --name nadia-evening-wrapup --agent nadia --cron "0 17 * * *" --message "Run evening summary and wrap-up"
   ```

5. To check your scheduled jobs are set up correctly:

   ```bash
   openclaw cron list
   ```

   This shows a table of all your scheduled jobs with their IDs, times, and status.

6. To remove a job you don't want anymore, copy its ID from the list above and run:

   ```bash
   openclaw cron delete <paste-job-id-here>
   ```

> 💡 **These commands are approximate.** The exact syntax depends on your OpenClaw version. Check the official docs at <https://docs.openclaw.ai> if a command doesn't work.

---

## How to Use It Every Day / كيف تستخدمينه يومياً

### Your Daily Routine with Nadia

**Morning (when you start work):**

1. Open Telegram
2. Check if Tariq sent you a research summary (he does this at 8 AM automatically)
3. Ask Nadia anything you need:
   - "Show me latest competitor updates" → she asks Tariq
   - "What's the BOQ status?" → she asks Layla
   - "Any new drawings for B2?" → she asks Khalid
   - "Update me on the feasibility for B1" → she asks Sara

**During the day:**

- Just text Nadia whenever you need something, like texting a coworker
- She understands Arabic and English — mix them if you want!

**Examples of what you can ask (in Arabic):**

| What You Want | What to Type |
| -------------- | ------------- |
| Find competitors | "ابحث لي عن منافسين في سوق البحرين" |
| Check contacts | "عطيني بيانات المقاولين" |
| Track drawings | "ايش آخر رسومات B2 الإنشائية؟" |
| BOQ status | "ايش وضع جداول الكميات؟" |
| Feasibility check | "ايش حالة دراسة الجدوى؟" |
| Remember something | "تذكّري إن مقاول B1 بدأ العمل اليوم" |
| Investor search | "ابحث لي عن مستثمرين للمشروع" |
| Client database | "مين العملاء المهتمين بشقق ركائز؟" |

**Examples in English:**

| What You Want | What to Type |
| -------------- | ------------- |
| Find competitors | "Find competitors similar to Bahrain Marina" |
| Check contacts | "Show me all contractor contacts" |
| Track drawings | "What's the latest structural drawing for B2?" |
| BOQ status | "Who are our BOQ engineers and what's their status?" |
| Feasibility check | "What's the ROI estimate for Rakaez B1?" |
| Remember something | "Remember that the B3 permit was approved today" |
| Investor search | "Search for potential investors in KSA real estate" |
| AutoCAD info | "List all .dwg files for building B1 with their dates" |

---

## Understanding Your Project Files / فهم ملفات مشروعك

Your `data/` folder is your real project workspace. The agents will **automatically scan** this folder to discover what's inside — you don't need to tell them.

Just put your project files in `data/` organized however makes sense to you. The agents will figure it out. Common things you might have:

- **AutoCAD drawings (.dwg)** — per building, per discipline
- **Bills of Quantities (.xlsx)** — BOQ trackers and engineer work
- **Feasibility & business spreadsheets (.xlsx)** — revenue models, cost analysis
- **Structural analysis files** — ETABS (.e2k/.EDB), SAFE foundations (.FDB), RAM Concept (.cpt)
- **Project schedules** — Primavera P6 (.xer)
- **3D models** — SketchUp (.skb) and vendor deliverables
- **Competitor/client folders** — one folder per company
- **Contractor and engineering office data** — contacts and trackers

> 💡 **You can organize `data/` however you like.** Add folders, rename things, put in new files — the agents re-scan each session and adapt.
>
> 💡 **Important about AutoCAD files:** The agents **cannot open .dwg files** to see the drawings inside. But they CAN:
>
> - Read file names to tell you which building, discipline, and date each drawing is for
> - Track which drawings are newest and flag if anything is outdated
> - Cross-reference structural drawings with ETABS and foundation models
> - Tell you if PDF exports exist for a given drawing

---

## Week-by-Week Plan / خطة أسبوعية للبدء

**Don't try to set up everything at once.** Follow this gradual plan:

### Week 1: Just Nadia (نادية فقط)

**Goal:** Get comfortable chatting with your AI assistant.

- Open Telegram and talk to Nadia
- Ask her about your project, your files, your data
- Tell her when she gets something wrong — she'll remember
- Don't worry about the other agents yet
- **Expect:** Her first answers might not be perfect. That's normal! She gets better as you give feedback.

### Week 2: Add Tariq (أضيفي طارق)

**Goal:** Automate your competitor and market research.

- Ask Nadia to have Tariq do research sweeps
- Set up his morning cron job (he wakes up at 8 AM and researches)
- Review what he writes in `intel/DAILY-INTEL.md`
- Tell him what to focus on: "Focus more on Bahrain developers" or "I care about pricing in Eastern Province"

### Week 3: Add Layla + Khalid (أضيفي ليلى وخالد)

**Goal:** Automate data tracking and technical file management.

- Layla starts reading your Excel trackers daily
- Khalid starts tracking AutoCAD revisions and flagging issues
- They write their outputs to `sheets/` and `technical/` folders
- Nadia can now give you combined updates ("Here's what changed today across all trackers and drawings")

### Week 4: Add Sara (أضيفي سارة)

**Goal:** Full team, automated feasibility analysis.

- Sara reads the feasibility spreadsheets and Tariq's market data
- She produces investment briefs and cost analyses
- The full team is now feeding each other information automatically:
  - Tariq researches → Sara uses it for feasibility
  - Layla tracks BOQs → Sara uses it for cost estimation
  - Khalid tracks scope → Sara uses it for timeline costing

---

## Workspace Structure / هيكل مساحة العمل

This is what all the files outside `data/` are for:

| File / Folder | What Is It? | Do You Need to Edit It? |
| ----- | ------------ | ------------------------ |
| `SOUL.md` | Nadia's personality and instructions | Only if you want to change how she behaves |
| `AGENTS.md` | Rules that ALL agents follow | Rarely — only if you want to change global behavior |
| `MEMORY.md` | What the agents remember long-term | The agents update this themselves |
| `HEARTBEAT.md` | Auto-recovery if something crashes | Never — this is automatic |
| `agents/tariq/` | Tariq's personality and instructions | Only if you want to change his research focus |
| `agents/layla/` | Layla's personality and instructions | Only if you want to change which trackers she reads |
| `agents/khalid/` | Khalid's personality and instructions | Only if you want to change his technical scope |
| `agents/sara/` | Sara's personality and instructions | Only if you want to change her financial parameters |
| `intel/` | Where Tariq writes his research | No — just read it (or ask Nadia to summarize) |
| `sheets/` | Where Layla writes data summaries | No — just read it |
| `technical/` | Where Khalid writes technical reports | No — just read it |
| `feasibility/` | Where Sara writes financial analysis | No — just read it |
| `memory/` | Daily activity logs | No — agents write these automatically |

---

## Tips for Getting the Best Results / نصائح للحصول على أفضل النتائج

1. **Be specific** — "ابحث عن مطورين في المنطقة الشرقية" is better than "ابحث عن منافسين"
2. **Give feedback** — If Nadia gives wrong info, say "هذا غلط، الصح هو..." — she'll remember
3. **Use "remember" (تذكّري)** — Say "تذكّري إن..." to store important info for the future
4. **Mix languages** — "Check the BOQ tracker وعطيني الملخص بالعربي" works perfectly
5. **Ask for sources** — The agents always tell you which file/folder they got information from
6. **Start each day with a summary** — Ask "ايش الجديد اليوم؟" to get a full daily briefing

---

## Troubleshooting / حل المشاكل

### "I can't find Terminal" / ما ألاقي التيرمنل

- Press **Command (⌘) + Space**, type "Terminal", press Enter
- It's in Applications → Utilities → Terminal

### "The install command didn't work" / أمر التثبيت ما اشتغل

- Make sure you're connected to the internet
- Try closing Terminal and opening it again
- Copy the command exactly — don't add spaces before or after
- Visit <https://docs.openclaw.ai/start/getting-started> for help

### "Nadia isn't responding on Telegram" / نادية ما ترد على تلقرام

1. Check if OpenClaw is running. In Terminal, type:

   ```bash
   openclaw status
   ```

2. If it says "not running", start it:

   ```bash
   openclaw gateway restart
   ```

3. Make sure you created the Telegram bot correctly (Step 4b above)
4. Make sure you started a chat with the bot (search for it in Telegram and tap Start)

### "The agent gives wrong information" / المعلومات اللي يعطيني غلط

- Tell Nadia: "هذا غلط" and explain what's correct — she'll update her memory
- Check that your data files (Excel trackers) are up to date
- The agents can only work with the data you give them

### "I see weird characters instead of Arabic" / أشوف رموز غريبة بدل العربي

- This shouldn't happen on modern Macs, but if it does:
- Make sure your terminal is using UTF-8 encoding
- In Terminal menu → Preferences → Profiles → Advanced → set Character encoding to "Unicode (UTF-8)"

### "I want to start over / أبي أبدأ من البداية"

- Don't worry, nothing is permanent!
- Your actual project data in `data/` is never modified by the agents
- To reset the agents' memory: delete the contents of `memory/` folder and `MEMORY.md`
- To fully restart: `openclaw gateway restart`

### "Can the agents really read AutoCAD?" / هل فعلاً يقدرون يقرأون أوتوكاد؟

- **Not the drawings themselves** — they can't open .dwg files and see the lines/details
- **But they can** read file names, track dates and revisions, cross-reference with ETABS/foundation files, and tell you which drawings are latest
- For actual drawing review, you still need AutoCAD or a free viewer like Autodesk's online viewer
- If you export PDFs from AutoCAD and put them in the PDF/ folders, the agents can reference those too

---

## Getting Help / للمساعدة

- **OpenClaw docs:** <https://docs.openclaw.ai>
- **OpenClaw community:** Check their Discord or GitHub for support
- **To modify agent behavior:** Edit the `SOUL.md` file for the relevant agent
- **To add new data:** Just put files in the `data/` folder — the agents will find them automatically
