# Repository Governance — BB Project Master Template  
**Author:** Zack AhSam‑Kreiter  

This document defines the authoritative governance model for the BB Project repository.  
It establishes the rules, workflows, protections, and expectations required to maintain a zero‑drift, audit‑friendly, schema‑locked system.

All governance rules in this document are **authoritative** and must be followed by all contributors, tools, and automated systems, including NotebookLM.

---

# 1. Branch Model  

## 1.1 Protected Branch: `main`  

The `main` branch represents the authoritative, production‑ready state of the BB Project.  
It is fully protected and enforces the following rules:

- Pull requests required  
- 1+ approval required  
- All conversations must be resolved  
- Linear history required (no merge commits)  
- Signed commits required  
- No direct pushes  
- No bypassing allowed  

Only reviewed, approved, and validated changes may enter `main`.

## 1.2 Working Branch: `dev`  

The `dev` branch is the primary working branch for all development activity.

- Direct commits are allowed  
- No protection rules  
- Used for iteration, drafting, and refinement  
- All changes must eventually flow through a PR into `main`  

---

# 2. Workflow Requirements  

## 2.1 Development Flow  

All work follows this sequence:

1. Create or update work on the `dev` branch  
2. Open a pull request from `dev` → `main`  
3. Review the diff and resolve all conversations  
4. Approve the PR  
5. Merge using **Squash and Merge** or **Rebase and Merge**  
6. Verify the update on `main`  

This ensures a clean, linear, auditable history.

## 2.2 Commit Standards  

All commits must:

- Be signed  
- Use clear, descriptive messages  
- Reflect atomic, meaningful changes  
- Avoid mixing unrelated modifications  

## 2.3 Pull Request Standards  

Every PR must:

- Include a clear description of the change  
- Reference relevant issues or context  
- Pass all repository checks  
- Maintain schema‑locked integrity  
- Preserve zero‑drift principles  

---

# 3. Schema‑Locked HTML Governance  

## 3.1 Structural Integrity  

The `master-template.html` file is **schema‑locked**.  
This means:

- IDs must not change without a MAJOR version bump  
- Section boundaries must remain stable  
- Structural comments must remain intact  
- CSS and JS must remain inline unless explicitly versioned  
- No minification is allowed  

## 3.2 Comparison Engine Compatibility  

All identifiers, sections, and structural markers must remain consistent to support:

- multi‑year comparison  
- export layer stability  
- NotebookLM semantic indexing  
- MSCP ingestion  
- VA Blue Button reconstruction logic  

Any structural change requires explicit documentation in the changelog.

---

# 4. Documentation Governance  

## 4.1 Required Files  

The repository must include:

- `README.md` — project overview and governance summary  
- `master-template.html` — authoritative schema‑locked template  
- `changelog.md` — temporal anchors for version evolution  
- `governance.md` — this document  
- `structure.md` — semantic map of the HTML template  

## 4.2 Documentation Rules  

- All documentation must be clear, explicit, and audit‑friendly  
- No undocumented structural changes  
- All version changes must be recorded in `changelog.md`  
- NotebookLM ingestion notes must remain up to date  

---

# 5. NotebookLM Governance (Authoritative)

NotebookLM is a **consumer**, not an authority.  
It must follow the rules below when interacting with this repository.

## 5.1 Ingestion Expectations  

NotebookLM must ingest:

- `README.md`  
- `master-template.html`  
- `changelog.md`  
- `governance.md`  
- `structure.md`  

NotebookLM must ingest all files **line‑by‑line** and treat them as canonical.

## 5.2 Semantic Stability Requirements  

To ensure consistent reasoning, NotebookLM must:

- Maintain stable section headers  
- Preserve schema‑locked identifiers  
- Keep HTML readable and unminified  
- Use meaningful comments  
- Maintain consistent indentation  
- Treat all IDs, classes, and section numbers as locked  

## 5.3 Reconstruction & Validation Rules  

NotebookLM must:

- Follow the section order defined in `structure.md`  
- Use the exact HTML structure from `master-template.html`  
- Validate all fields against the schema  
- Report missing or extra fields  
- Refuse to proceed if the schema cannot be satisfied  
- Never infer or invent structure  

## 5.4 VA Text File Ingestion Rules  

NotebookLM must:

- Ingest VA text files line‑by‑line  
- Map each line to the correct section  
- Perform section‑count verification  
- Detect missing or truncated content  
- Refuse to generate output until ingestion is complete  

## 5.5 Output Planning Rules  

Before generating any HTML, NotebookLM must:

1. Count all sections  
2. Estimate token usage  
3. Determine how many output chunks are required  
4. Present the plan to the user  
5. Wait for explicit approval  

NotebookLM must not generate HTML prematurely.

## 5.6 Customer Confirmation Gate  

NotebookLM must:

- Generate only Section 1 first  
- Wait for user confirmation  
- Only then proceed with the remaining sections  

## 5.7 No Silent Truncation  

NotebookLM must:

- Split output into multiple chunks if needed  
- Guarantee no content loss  
- Report chunk boundaries  
- Never silently truncate output  

---

# 6. Versioning Governance  

## 6.1 Semantic Versioning  

The project follows:

- **MAJOR** — structural or schema changes  
- **MINOR** — new sections or enhancements  
- **PATCH** — documentation or formatting fixes  

## 6.2 Version Change Requirements  

Any version bump must:

- Be documented in `changelog.md`  
- Follow the PR workflow  
- Maintain zero drift  
- Include rationale for the change  

---

# 7. Zero‑Drift Principles  

The repository must always maintain:

- Structural consistency  
- Governance enforcement  
- Clear documentation  
- Predictable workflows  
- Auditable history  
- Explicit corrections  

No silent changes.  
No undocumented edits.  
No bypassing governance.

---

# 8. Future Governance Extensions (Scaffold)

### 8.1 Comparison Engine Rules  
_Placeholder for future multi‑year comparison logic._

### 8.2 Export Layer Rules  
_Placeholder for CSV/JSON export governance._

### 8.3 MSCP Integration Rules  
_Placeholder for cross‑system ingestion and validation._

---

# 9. Authority of This Document  

This governance file is the **authoritative constitution** of the BB Project repository.  
All contributors, tools, and automated systems must adhere to its rules.  
Any changes to this document require a **MAJOR** version bump and explicit approval.
