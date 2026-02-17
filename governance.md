# Repository Governance — BB Project Master Template  
**Author:** Zack AhSam‑Kreiter  

This document defines the authoritative governance model for the BB Project repository.  
It establishes the rules, workflows, protections, and expectations required to maintain a zero‑drift, audit‑friendly, schema‑locked system.

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
- `structure.md` (future) — semantic map of the HTML template  

## 4.2 Documentation Rules  
- All documentation must be clear, explicit, and audit‑friendly  
- No undocumented structural changes  
- All version changes must be recorded in `changelog.md`  
- NotebookLM ingestion notes must remain up to date  

---

# 5. NotebookLM Governance  

## 5.1 Ingestion Expectations  
NotebookLM is expected to ingest:

- `README.md`  
- `master-template.html`  
- `changelog.md`  
- `governance.md`  
- `structure.md` (when added)  

## 5.2 Semantic Stability  
To ensure consistent reasoning:

- Maintain stable section headers  
- Preserve schema‑locked identifiers  
- Keep HTML readable and unminified  
- Use meaningful comments  
- Maintain consistent indentation  

## 5.3 Source‑of‑Truth Principle  
NotebookLM is a **consumer**, not an authority.  
The repository remains the single source of truth.

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

