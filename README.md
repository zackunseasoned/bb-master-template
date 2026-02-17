# BB Project — Master Template (Single‑File HTML)

## Overview
This repository contains the authoritative **single‑file HTML master template** for the **VA Blue Button Reconstruction & Comparison Engine** (“BB Project”).  
The template is a fully self‑contained document that includes all structural scaffolding, embedded CSS, embedded JS (if used), and schema‑locked identifiers required for accurate reconstruction of VA Blue Button data.

The goal of this repository is to maintain a **zero‑drift**, **audit‑friendly**, and **version‑controlled** master file that can be reliably used for:
- medical record reconstruction  
- multi‑year comparison  
- CSV/JSON export generation  
- longitudinal analysis  
- audit and verification workflows  

This repository is intentionally minimal to preserve clarity and prevent schema drift.

---

## Files

### `master-template.html`
The complete, authoritative, single‑file HTML template.  
Contains:
- section scaffolding  
- semantic structure  
- embedded CSS  
- embedded JS (if applicable)  
- export‑layer anchors  
- comparison‑engine hooks  
- schema‑locked IDs and classes  

This file is the **source of truth** for all BB Project reconstruction and comparison operations.

### `README.md`
Repository documentation, rules, branching model, and versioning standards.

### `changelog.md`
A chronological record of all modifications to the master template.  
Every change must be logged to maintain auditability.

---

## Branching Model

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

## Editing Rules
To maintain integrity and auditability of the BB Project:

1. **Do not edit `main` directly.**  
2. All changes must be made in `dev` and submitted via pull request.  
3. Every modification must be documented in `changelog.md`.  
4. Schema‑level changes require a **MAJOR** version bump.  
5. The master template must remain a **single, self‑contained HTML file**.  
6. No external CSS, JS, or dependencies may be introduced.  
7. All IDs, classes, and structural anchors must remain **schema‑locked**.  
8. All changes must preserve:
   - export‑layer compatibility  
   - comparison‑engine compatibility  
   - accessibility and semantic structure  

---

## Versioning
This project uses **semantic versioning**:



