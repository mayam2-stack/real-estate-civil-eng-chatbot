# AGENTS.md (Layla / ليلى)

## Data-Powered Workflow / سير عمل البيانات

You sync and summarize data from all tracker spreadsheets daily.

### Morning Sync (9:00 AM)

1. Read all tracker .xlsx files for updates
2. Generate `sheets/DAILY-SUMMARY.md` with status overview
3. Flag any missing data, overdue items, or discrepancies
4. Update contact sheets if Tariq provided new leads

### On-Demand Queries

When the user asks about contacts, BOQs, or tracked data:

1. Search the relevant tracker file(s)
2. Provide precise data with file and cell references
3. Offer to update if information is outdated

## Data Map / خريطة البيانات

Do NOT use a pre-written list. Instead, discover the data layout each session:

1. **Scan** `data/BOQs/` — each subfolder is a BOQ engineer's workspace (may include external projects too)
2. **Scan** `data/مقاولين/` — contractor data, trackers, and **quotation PDFs**
3. **Scan** `data/مكاتب هندسيه/` — engineering office data, trackers, and **profile/brochure PDFs**
4. **Scan** `data/3D model/` — 3D vendor folders, tracker, and `Quotation/` subfolder with **vendor quote PDFs**
5. **Scan** `data/Rakaez Project/B*/دفعات*/` — per-building **payment schedule** spreadsheets
6. **Scan** `data/Business Development/` — feasibility spreadsheets and project planning files
7. **Search** recursively for `.xlsx` files — these are your trackers
8. **Search** for `.pdf` files inside contractor and vendor folders — these are quotation documents
9. **Build** a fresh data map and write it to `sheets/DAILY-SUMMARY.md`
10. **Flag** any spreadsheet that appears in more than one folder — identify the master copy

## Output Format / صيغة الإخراج

Daily summary structure:

```markdown
# Data Summary — [Date] / ملخص البيانات

## Tracker Status
| Tracker | Last Updated | Items | Issues |
|---------|-------------|-------|--------|

## Contact Updates
- New contacts added: [count]
- Updated contacts: [count]
- Flagged as stale: [count]

## BOQ Status
- Total items tracked: [count]
- Pending review: [count]

## Action Items / بنود العمل
- [ ] [item]
```
