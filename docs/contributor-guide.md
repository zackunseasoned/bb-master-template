# Contributor Guide — BB Project  
**Author:** Zack AhSam‑Kreiter  

This guide explains how contributors must work within the BB Project’s zero‑drift, schema‑locked architecture.

---

# 1. Philosophy
The BB Project is built on:

- determinism  
- auditability  
- schema‑locking  
- zero drift  
- explicit correction  
- long‑term stability  

All contributions must preserve these principles.

---

# 2. Branch Workflow

### `main` (protected)
- Production‑ready  
- No direct commits  
- PRs only  
- Signed commits required  
- Linear history enforced  

### `dev`
- Working branch  
- All edits occur here  
- PRs flow from `dev` → `main`  

---

# 3. Contribution Steps

1. Create or update work in `dev`  
2. Document changes in `changelog.md`  
3. Open PR from `dev` → `main`  
4. Resolve all conversations  
5. Obtain approval  
6. Merge using Squash or Rebase  
7. Verify on `main`  

---

# 4. Editing Rules

- Do not modify schema‑locked identifiers  
- Do not change section order  
- Do not alter semantic comments  
- Do not introduce external CSS/JS  
- Do not minify HTML  
- Do not break export‑layer compatibility  
- Do not break comparison‑engine compatibility  

---

# 5. Documentation Rules

- All changes must be documented  
- All version bumps must follow semantic versioning  
- All structural changes require a MAJOR bump  
- All documentation must remain clear and audit‑friendly  

---

# 6. NotebookLM Integration Rules

Contributors must ensure:

- README.md, structure.md, governance.md remain aligned  
- master-template.html remains schema‑locked  
- NBLLM rules remain intact  
- No drift between documents  

---

# 7. Testing Requirements

Before merging:

- Validate HTML structure  
- Validate section IDs  
- Validate table IDs  
- Validate export controls  
- Validate JS behavior  
- Validate PDF output  
- Validate NBLLM ingestion  

---

# 8. Authority of This Guide

This guide is binding.  
All contributors must follow it.  
Any changes require a PR and a version bump.

