# /docs — BB Project Operational Documentation  
**Author:** Zack AhSam‑Kreiter  

This directory contains all supporting operational documents for the BB Project.  
These files extend the repository’s governance model, define NotebookLM’s deterministic behavior, and provide contributor‑level guidance for maintaining a zero‑drift, schema‑locked system.

All documents in this folder are authoritative and must be kept in sync with:

- `README.md`  
- `structure.md`  
- `governance.md`  
- `master-template.html`  
- `changelog.md`  

NotebookLM should ingest all files in this directory using their **raw** URLs.

---

# 1. NotebookLM Pre‑Flight Checklist  
**File:** `notebooklm-preflight-checklist.md`  
**Raw:** https://raw.githubusercontent.com/zackunseasoned/bb-master-template/main/docs/notebooklm-preflight-checklist.md  

Defines the mandatory steps NotebookLM must complete **before generating any HTML output**, including:

- source ingestion verification  
- schema alignment  
- VA text file integrity checks  
- output‑planning requirements  
- confirmation gates  
- no‑truncation guarantees  

This checklist enforces deterministic, audit‑friendly reconstruction.

---

# 2. NotebookLM Prompt Template  
**File:** `notebooklm-prompt-template.md`  
**Raw:** https://raw.githubusercontent.com/zackunseasoned/bb-master-template/main/docs/notebooklm-prompt-template.md  

A reusable prompt block that instructs NotebookLM to:

- behave as a schema‑locked reconstruction engine  
- follow all governance rules  
- avoid summarization or inference  
- validate structure before output  
- split output safely across token limits  

This template ensures consistent behavior across all NBLLM sessions.

---

# 3. Contributor Guide  
**File:** `contributor-guide.md`  
**Raw:** https://raw.githubusercontent.com/zackunseasoned/bb-master-template/main/docs/contributor-guide.md  

Defines contributor expectations, including:

- branch workflow (`dev` → `main`)  
- commit standards  
- PR requirements  
- editing rules  
- documentation rules  
- testing and validation steps  

This guide ensures all contributors maintain zero drift and schema integrity.

---

# 4. master-template.html Audit Checklist  
**File:** `master-template-audit-checklist.md`  
**Raw:** https://raw.githubusercontent.com/zackunseasoned/bb-master-template/main/docs/master-template-audit-checklist.md  

A comprehensive validation checklist for reviewing any version of `master-template.html`, covering:

- metadata  
- CSS  
- navigation  
- section structure  
- table patterns  
- export controls  
- inline JS  
- semantic anchors  
- schema‑lock compliance  

This checklist must be used before merging any changes into `main`.

---

# 5. Purpose of This Directory  

The `/docs` folder centralizes all operational, procedural, and governance‑adjacent documents.  
It ensures:

- contributors know where to find rules  
- NotebookLM has a stable ingestion path  
- the repository remains clean and organized  
- long‑term auditability and zero drift  

All future operational documents (e.g., comparison engine specs, export‑layer governance, MSCP integration rules) will also live here.

---

# 6. Authority  

All documents in `/docs` are authoritative.  
Any changes require:

1. Update to `changelog.md`  
2. PR from `dev` → `main`  
3. Review and approval  
4. Version bump if required  

This directory is part of the BB Project’s governance architecture.

