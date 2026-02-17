# BB Project — VA Blue Button Reconstruction & Comparison Engine  
Zack AhSam‑Kreiter

The BB Project is a standalone, schema‑locked system for reconstructing, validating, and comparing VA Blue Button medical records across multiple years. It produces:

- A clean, human‑readable HTML document per year  
- Machine‑readable CSV and JSON exports for every section  
- A multi‑year comparison engine for longitudinal analysis  
- A zero‑drift, audit‑friendly archive  

This repository contains the authoritative **single‑file HTML master template** and all governance documents required to maintain long‑term stability and reproducibility.

---

# 1. Overview

This repository maintains the **single‑file HTML master template** for the VA Blue Button Reconstruction & Comparison Engine (“BB Project”).  
The template is a fully self‑contained document that includes:

- section scaffolding  
- semantic structure  
- embedded CSS  
- embedded JS (if applicable)  
- export‑layer anchors  
- comparison‑engine hooks  
- schema‑locked IDs and classes  

The goal is to maintain a **zero‑drift**, **audit‑friendly**, and **version‑controlled** master file that can be reliably used for:

- medical record reconstruction  
- multi‑year comparison  
- CSV/JSON export generation  
- longitudinal analysis  
- audit and verification workflows  

This repository is intentionally minimal to preserve clarity and prevent schema drift.

---

# 2. Files

### `master-template.html`  
The complete, authoritative, single‑file HTML template.  
This file is the **source of truth** for all reconstruction and comparison operations.

### `README.md`  
Repository documentation, governance rules, NotebookLM operating rules, branching model, and versioning standards.

### `changelog.md`  
A chronological record of all modifications to the master template.  
Every change must be logged to maintain auditability.

### `governance.md`  
Repository governance, workflow rules, and schema‑lock requirements.

### `structure.md`  
Semantic map of the HTML template, including section ordering, IDs, and patterns.

---

# 3. Authoritative Section Order (14 Sections)

All documents must follow this exact order:

1. Patient Information  
2. Military Service  
3. Allergies  
4. Health Conditions  
5. Vaccines  
6. Vitals  
7. Medications  
8. Laboratory Results  
9. Past Appointments  
10. Upcoming Appointments  
11. Secure Messaging  
12. Care Summaries & Notes  
13. Social History  
14. Account Summary  

Section numbers, IDs, and names are **locked**.

---

# 4. HTML Structure Requirements

Each section must include:

- A `<section id="...">` matching the schema  
- A `.sec-header` with an expand indicator  
- A `.sec-content` container  
- A table (if applicable)  
- Export controls for CSV and JSON  
- A return‑to‑navigation link  

Notes and Secure Messaging must include **local expand/collapse controls** for internal text bodies.  
Global Expand All must **not** expand internal text bodies.

---

# 5. Export Layer Requirements

Every table must support:

- `exportTableToCSV()`  
- `exportTableToJSON()`  

Exports must:

- Use the exact schema column names  
- Contain no HTML artifacts  
- Preserve ordering  
- Be machine‑readable and audit‑friendly  

---

# 6. Multi‑Year Comparison Engine

The comparison engine must:

- Load each year’s CSV/JSON  
- Compare diagnoses, medications, labs, vitals, appointments, notes metadata, and more  
- Detect additions, removals, changes, and anomalies  
- Produce longitudinal intelligence  

This engine is schema‑locked and deterministic.

---

# 7. Zero‑Drift Architecture

The BB Project enforces:

- Locked schemas  
- Locked folder structure  
- Locked section numbering  
- No retroactive changes  
- Explicit correction workflows  
- Deterministic reconstruction  

This ensures long‑term auditability.

---

# 8. Branching Model

### `main`
- Protected  
- Production‑ready  
- Only updated via pull request  
- Must pass review and validation  

### `dev`
- Working branch  
- All edits occur here  
- Changes must be documented in `changelog.md` before merging  

This two‑branch model ensures stability, auditability, and zero drift.

---

# 9. Editing Rules

To maintain integrity and auditability:

1. **Do not edit `main` directly.**  
2. All changes must be made in `dev` and submitted via pull request.  
3. Every modification must be documented in `changelog.md`.  
4. Schema‑level changes require a **MAJOR** version bump.  
5. The master template must remain a **single, self‑contained HTML file**.  
6. No external CSS, JS, or dependencies may be introduced.  
7. All IDs, classes, and structural anchors must remain **schema‑locked**.  
8. All changes must preserve export‑layer and comparison‑engine compatibility.

---

# 10. Versioning

This project uses **semantic versioning**:

- **MAJOR** — schema changes or structural changes  
- **MINOR** — non‑breaking additions or enhancements  
- **PATCH** — small fixes or non‑structural corrections  

All version changes must be recorded in `changelog.md`.

---

# 11. NotebookLM Operating Rules (Authoritative)

NotebookLM must follow these rules when reading, interpreting, or generating content for the BB Project.

## 11.1 Source of Truth
NotebookLM must treat the following files as the **only authoritative sources**:

- `README.md`  
- `structure.md`  
- `governance.md`  
- `master-template.html` (raw)  
- All CSV/JSON schemas  

NotebookLM must not infer or invent structure not explicitly defined.

## 11.2 Ingestion Requirements
NotebookLM must:

- Fully ingest every linked raw file  
- Read every line of every schema  
- Treat all section numbers, IDs, and field names as locked  
- Treat the HTML template as canonical  

NotebookLM must not summarize these files — it must use them as construction blueprints.

## 11.3 Reconstruction Mandate
NotebookLM must:

1. Follow the section order in `structure.md`  
2. Use the exact IDs, headings, and class names from the HTML template  
3. Use the exact table schemas  
4. Include every required field  
5. Report missing fields explicitly  
6. Never omit or reorder schema elements  

NotebookLM must behave like a schema validator.

## 11.4 Completeness Audit Rules
NotebookLM must:

- Perform a line‑by‑line comparison against the schema  
- Identify missing fields  
- Identify extra fields  
- Identify mismatches in naming, order, or structure  
- Report discrepancies exhaustively  

## 11.5 No External Knowledge
NotebookLM must not:

- Pull in external medical knowledge  
- Infer meaning from VA terminology  
- Add fields not defined in the schema  

## 11.6 Behavior When Uncertain
If ambiguous, NotebookLM must:

- Refer to `structure.md`  
- Refer to the HTML template  
- Refer to the schema  
- Ask for clarification only if the schema does not define the answer  

NotebookLM must not guess.

## 11.7 Output Requirements
All output must:

- Follow the exact section numbering  
- Follow the exact HTML structure  
- Follow the exact schema  
- Include all required fields  
- Maintain strict consistency  

NotebookLM must behave like a deterministic reconstruction engine.

---

# 12. VA Text File Ingestion & Audit Rules (Authoritative)

## 12.1 Full Line‑By‑Line Ingestion
NotebookLM must:

- Read every line of every VA text file  
- Ingest all content without omission  
- Preserve ordering  
- Treat VA text files as mandatory input  

## 12.2 Schema‑Aligned Reconstruction
NotebookLM must:

- Map each line to the correct section  
- Validate each field  
- Report missing, extra, or malformed fields  
- Refuse to proceed if the schema cannot be satisfied  

## 12.3 Section Count Verification (Token‑Limit Protection)
Before generating output, NotebookLM must:

1. Count the number of sections in the VA text files  
2. Count the number of sections ingested  
3. Compare the counts  
4. Confirm all sections are present and complete  

If anything is missing, NotebookLM must halt and report.

## 12.4 Token‑Limit Safeguard
NotebookLM must:

- Estimate token usage  
- Detect when output may exceed limits  
- Split output into sequential parts  
- Ensure no content is lost  

## 12.5 Customer Confirmation Gate
Before delivering the full HTML document, NotebookLM must:

1. Generate only the first section  
2. Present it for verification  
3. Wait for explicit confirmation  
4. Only then proceed  

## 12.6 No Output Until Audit Completes
NotebookLM must not generate final HTML until:

- All text files are ingested  
- All schema fields are validated  
- Section counts match  
- Token checks pass  
- Customer confirms Section 1  

---

# 13. Output Planning & Section Count Rules (Authoritative)

## 13.1 Pre‑Flight Section Count Requirement
NotebookLM must:

1. Ingest all VA text files  
2. Identify all required sections  
3. Count the sections  
4. Estimate total output size  
5. Determine how many output chunks are required  

NotebookLM must explicitly state:

- Total number of sections  
- Estimated token size  
- Number of output chunks  
- Planned boundaries of each chunk  

## 13.2 Mandatory Output Plan Disclosure
NotebookLM must present:

- “I will need X output sections.”  
- “Section 1 will contain…”  
- “Section 2 will contain…”  

## 13.3 Customer Confirmation Gate
NotebookLM must:

- Wait for approval of the plan  
- Wait for approval of Section 1  
- Only then proceed  

## 13.4 No Partial or Premature Output
NotebookLM must not:

- Begin generating HTML early  
- Deliver partial sections  
- Skip the planning step  

## 13.5 Token‑Limit Protection
NotebookLM must:

- Estimate token usage per chunk  
- Ensure no chunk exceeds limits  
- Split further if needed  
- Report final chunk count  

NotebookLM must never truncate output.

---

# 14. NotebookLM Integration (Recommended Sources)

Add the following raw links to NotebookLM:

- README.md  
  https://raw.githubusercontent.com/zackunseasoned/bb-master-template/main/README.md  
- changelog.md  
  https://raw.githubusercontent.com/zackunseasoned/bb-master-template/main/changelog.md  
- governance.md  
  https://raw.githubusercontent.com/zackunseasoned/bb-master-template/main/governance.md  
- structure.md  
  https://raw.githubusercontent.com/zackunseasoned/bb-master-template/main/structure.md  
- master-template.html (raw)  
  https://raw.githubusercontent.com/zackunseasoned/bb-master-template/main/master-template.html  

---

# 15. Workflow Summary

- Work in `dev`  
- Document changes in `changelog.md`  
- Open PR from `dev` → `main`  
- Review, validate, and merge  
- Update NotebookLM sources if needed  

---

# 16. License
This project is maintained as an authoritative internal template.
