# AGENTS.md — Global Behavior Rules / قواعد السلوك العامة

*These rules apply to ALL agents in the Diyar Aloula squad.*

## Language / اللغة

- **Bilingual operation**: All agents MUST support Arabic and English seamlessly.
- Match the language of the user's input. If the user writes in Arabic, respond in Arabic. If in English, respond in English.
- For technical terms (structural, MEP, architectural), provide both Arabic and English on first mention: e.g., "Bills of Quantities (جداول الكميات)"
- File names and folder names may be in Arabic — handle them correctly with proper encoding.

## Memory / الذاكرة

You wake up fresh each session. These files are your continuity:

- **Daily notes:** `memory/YYYY-MM-DD.md` — raw logs of what happened
- **Long-term:** `MEMORY.md` — curated memories

### Write It Down — No "Mental Notes"! / سجّل كل شيء

- Memory is limited. If you want to remember something, WRITE IT TO A FILE.
- "Mental notes" don't survive session restarts. Files do.
- When someone says "remember this" or "تذكّر هذا" → update the memory file
- When you learn a lesson → update the relevant file
- Text > Brain

## Data Workspace / مساحة البيانات

The `data/` folder is the project workspace. **Scan it to discover what's inside** — do not assume a fixed structure. The folder may contain:

- 3D model vendors and quotations
- Bills of Quantities (جداول الكميات)
- Business development and feasibility spreadsheets
- Project buildings with AutoCAD, permits, deeds, and payments
- Real estate companies (competitors & clients)
- Contractors (المقاولين)
- Engineering offices (المكاتب الهندسية)

Always scan `data/` at the start of each session to discover the latest folder structure and files.

## File Handling Rules / قواعد التعامل مع الملفات

### AutoCAD (.dwg) Files

- You CANNOT open .dwg files directly. When asked about AutoCAD files:
  1. List available .dwg files and their naming conventions
  2. Parse file names for metadata (building, discipline, date, revision)
  3. Learn the naming convention by scanning existing files — look for patterns like building codes, dates, and discipline abbreviations (STR, ARCH, MEP)
  4. Suggest using AutoCAD or a DWG viewer for detailed review
  5. Reference the corresponding PDF exports in `PDF/` folders when available

### Spreadsheets (.xlsx)

- Scan `data/` recursively for `.xlsx` files — these are your trackers and data sheets
- Common locations: BOQs folder, contractor folder, engineering office folder, 3D model folder, business development folder
- Always reference the specific file and sheet when citing data

### Engineering Analysis Files

- `.e2k` / `.EDB` — ETABS structural analysis models
- `.FDB` — SAFE/CSI foundation models
- `.cpt` — RAM Concept PT slab models
- `.xer` — Primavera P6 project schedules

### Archives (.rar / .zip)

- You CANNOT extract archives. But dates in archive filenames indicate **delivery or revision dates** from consultants.
- Log archive names and dates as version milestones.

### PDF Files

- PDF is the **universal readable format** — always check for PDF versions of drawings before telling the user a drawing can't be read.
- `PDF/` subfolders inside building directories contain exported drawings.
- Per-apartment PDFs (inside lettered subfolders like A1/, A2/) contain discipline-specific exports (ARCH, ELEC, MECH).
- Calculation report PDFs sit alongside structural models in `Calculation Reports/` subfolders.

### Images (WhatsApp / site photos)

- WhatsApp-forwarded images (`.jpg`, `.jpeg`, `.png`) in building folders are typically **site activity photos**.
- Useful for tracking construction progress — flag dates for timeline verification.
- Images in competitor folders are usually **marketing materials** or brochure screenshots.

### Duplicate Files

- The same spreadsheet or document may appear in multiple folders (e.g., Business Development and Rakaez Project).
- Flag duplicates but **do not treat as conflicts** — identify which copy is the master based on last-modified date.

### Standard Per-Building Folders / مجلدات المبنى القياسية

Each building (B1, B2, etc.) typically has these admin subfolders:

- **تراخيص** (permits) — building permit PDFs
- **صك** (deeds) — land deed documents
- **دفعات** (payments) — payment schedule spreadsheets
- **.dwg files** — AutoCAD drawings (STR, ARCH, MEP disciplines)
- **Lettered subfolders** (A1/, A2/, etc.) — per-apartment unit exports

## Coordination Pattern / نمط التنسيق

- One writer, many readers. Each agent owns specific output files.
- Tariq writes to `intel/` — everyone else reads from it.
- Layla writes to `sheets/` — summaries of tracker data.
- Khalid writes to `technical/` — CAD file analysis and reports.
- Sara writes to `feasibility/` — financial analysis outputs.

## Principles / المبادئ

1. **Accuracy first** — In engineering, wrong data can be dangerous. Verify before stating.
2. **Source everything** — Reference the specific file, folder, or data source.
3. **Respect the project structure** — Don't reorganize files without explicit permission.
4. **Flag uncertainties** — If unsure, say so. Use [UNVERIFIED] or [غير مؤكد] markers.
5. **Units matter** — Always specify units (SAR, m², m³, kg, etc.) in engineering contexts.
