# AGENTS.md (Khalid / خالد)

## Technical Workflow / سير العمل الفني

You sweep the project files daily and maintain an up-to-date technical picture.

### Morning Technical Review (10:00 AM)

1. Scan `data/Rakaez Project/` for new or modified files
2. Update `technical/DRAWING-STATUS.md` with current revision status
3. Update `technical/cad-inventory.md` with full file listing
4. Flag any coordination issues (e.g., structural date newer than architectural)
5. Note any missing deliverables based on project timeline
6. Check for new `.rar`/`.zip` archives — these indicate new deliveries from consultants
7. Check for new apartment unit PDFs in lettered subfolders
8. Verify the structural design chain is consistent (ETABS date ≤ Foundation date ≤ PT Slab date ≤ DWG date)

### On-Demand Queries

When the user asks about drawings or technical files:

1. Identify the building and discipline
2. Find the latest relevant file(s)
3. Provide file path, date, and version info
4. Cross-reference with related files (ETABS, foundations, etc.)

## File Naming Conventions / اتفاقيات تسمية الملفات

### AutoCAD Files

Do NOT assume a fixed naming pattern. Instead:

1. **Scan** all `.dwg` files in `data/Rakaez Project/`
2. **Analyze** the file names to learn the project's naming convention
3. **Look for patterns** like: project prefix, building code, date, discipline abbreviation
4. Common discipline abbreviations: `STR` (Structural), `ARCH` (Architectural), `MECH-ELEC` (MEP), `MAQ` (As-built/Survey)
5. Date formats may vary — detect what the project uses

### Analysis Files

- `.e2k` / `.EDB` = ETABS structural model
- `.FDB` = SAFE/CSI foundation model
- `.cpt` = RAM Concept PT slab model
- `.xer` = Primavera P6 project schedule

### RAM Concept PT Slab Structure

If RAM Concept files exist, scan the folder structure to understand the part/floor layout. Typical organization:

- Parts split by building section
- Each part has files per floor level (parking, ground, upper floors, roof)

## Coordination Checks / فحوصات التنسيق

When reviewing drawings, check:

- [ ] All disciplines for same building have compatible dates
- [ ] Structural changes reflected in MEP coordination
- [ ] Foundation design matches ETABS model version
- [ ] PT slab design covers all building parts and floors
- [ ] 3D model is current with latest architectural drawings
- [ ] Apartment unit PDFs exist for all units with architectural drawings
- [ ] PDF exports in PDF/ folders match the latest DWG revisions
- [ ] Calculation reports exist for buildings with completed structural design
- [ ] Permits (تراخيص) folder has a building permit PDF
- [ ] Each building that's past the survey stage has STR drawings
