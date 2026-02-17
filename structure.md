# Structure — BB Project Master Template  
**Author:** Zack AhSam‑Kreiter  

This document defines the authoritative structural map of `master-template.html`.  
It reflects the exact ordering, identifiers, semantic anchors, table schemas, behavioral logic, and UI patterns present in the canonical single‑file HTML template used for VA Blue Button reconstruction and multi‑year comparison.

All structures listed here are **schema‑locked**.  
Any modification requires a **MAJOR** version bump and must be documented in `changelog.md`.

This file is a **source‑of‑truth reference** for:

- reconstruction engines  
- NotebookLM ingestion  
- comparison engines  
- export layers  
- audit workflows  

---

# 1. Document Metadata Block  

The file begins with a top‑level HTML comment containing:

- Project name  
- Template purpose  
- Version (semantic versioning)  
- Status (Authoritative Source of Truth)  
- Repository URL  
- Last Updated date  
- Editing rules (dev‑only edits, PR workflow, schema‑lock rules, no external dependencies)

This metadata block is a **semantic anchor** and must remain intact.  
NotebookLM must ingest this block **line‑by‑line**.

---

# 2. Document Root  

The document root consists of:

- `<!DOCTYPE html>`  
- `<html lang="en">`  
- `<head>`  
- `<body>`

These elements define the global document structure and must not be altered.

---

# 3. Global Styles (Inline CSS)  

All CSS is embedded within `<style>` inside `<head>`.  
No external CSS is permitted.

### 3.1 Layout & Typography  
- Body styling  
- Header alignment (`.center`)  
- Section styling (`section`, `.sec-header`, `.sec-content`)  

### 3.2 Navigation  
- `.nav-panel`  
- `.nav-btn`  
- `.nav-top-link`  

### 3.3 Tables  
- Unified table styling  
- Sticky headers  
- Alternating row backgrounds  
- `.table-container` scroll behavior  

### 3.4 Sorting  
- `.sortable`  
- `.sort-indicator`  

### 3.5 Expandable Notes / Messages  
- `.note-body`  
- `.msg-body`  
- `.toggle-btn`  

### 3.6 Print/PDF Optimizations  
- Hide navigation and controls  
- Remove shadows  
- Disable sticky headers  

All CSS must remain inline and unminified.

---

# 4. Header Section  

Located at the top of `<body>`.

Contains:

- `<h1>` Department of Veterans Affairs  
- `<h2>` Care summaries and notes  
- `.period` reporting date range  
- `.patient-bar` patient identity summary  
- `id="top"` navigation anchor  

This header is schema‑locked.

---

# 5. Navigation Panel  

A list of `.nav-btn` elements that call `openAndScroll()`.

Canonical navigation order (schema‑locked):

1. patient-info  
2. military  
3. allergies  
4. problems  
5. vaccines  
6. vitals  
7. medications  
8. results  
9. past-appts  
10. upcoming-appointments  
11. secure-messaging  
12. notes  
13. social-history  
14. account-summary  

NotebookLM must treat this ordering as **authoritative**.

---

# 6. Global Controls  

A `.global-controls` block containing:

- Expand All  
- Collapse All  

These control **only section‑level** expansion, not internal message/note bodies.

---

# 7. Section Structure (Schema‑Locked Pattern)

Every section follows this exact structure:

```
<!-- X. Section Name -->
<section id="SECTION-ID">
    <div class="sec-header" onclick="toggleAccordion('SECTION-ID')">
        <h3>Section Title</h3>
        <span class="expand-indicator">+</span>
    </div>

    <div class="sec-content">
        <div class="table-container">
            <table id="TABLE-ID">...</table>
        </div>

        <div class="export-controls">
            <button>Export CSV</button>
            <button>Export JSON</button>
        </div>

        <a href="#top" class="nav-top-link">↑ Return to Navigation</a>
    </div>
</section>
```

This pattern is **locked** and must not be altered.

---

# 8. Canonical Section List (1–14)

Below is the exact section list, in order, with IDs and table IDs.

### 1. Patient Information  
- Section ID: `patient-info`  
- Table ID: `patient-info-table`  

### 2. Military Service  
- Section ID: `military`  
- Table ID: `military-table`  
- Includes Privacy Guard notice  

### 3. Allergies  
- Section ID: `allergies`  
- Table ID: `allergy-table`  

### 4. Health Conditions  
- Section ID: `problems`  
- Table ID: `problems-table`  

### 5. Vaccines  
- Section ID: `vaccines`  
- Table ID: `vaccines-table`  

### 6. Vitals  
- Section ID: `vitals`  
- Table ID: `vitals-table`  

### 7. Medications  
- Section ID: `medications`  
- Table ID: `medications-table`  

### 8. Laboratory Results  
- Section ID: `results`  
- Table ID: `results-table`  

### 9. Past Appointments  
- Section ID: `past-appts`  
- Table ID: `past-appts-table`  

### 10. Upcoming Appointments  
- Section ID: `upcoming-appointments`  
- Table ID: `upcoming-appointments-table`  

### 11. Secure Messaging  
- Section ID: `secure-messaging`  
- Table ID: `secure-messaging-table`  
- Includes local controls  
- Uses `.msg-body` expandable content  

### 12. Care Summaries and Notes  
- Section ID: `notes`  
- Table ID: `notes-table`  
- Includes local controls  
- Uses `.note-body` expandable content  

### 13. Social History  
- Section ID: `social-history`  
- Table ID: `social-history-table`  
- Key/value table pattern  

### 14. Account Summary  
- Section ID: `account-summary`  
- Table ID: `account-summary-table`  
- Key/value table pattern  

---

# 9. Table Patterns

### 9.1 Sortable Multi‑Column Tables  
Used in most sections.  
Sortable via `sortTable()`.

### 9.2 Key/Value Two‑Column Tables  
Used in:  
- Social History  
- Account Summary  

### 9.3 Expandable Content Tables  
Used in:  
- Secure Messaging (`.msg-body`)  
- Notes (`.note-body`)  

---

# 10. Export Layer Structure  

Every section includes an `.export-controls` block with:

- `exportTableToCSV(tableId, filename)`  
- `exportTableToJSON(tableId, filename)`  

Filenames are year‑scoped (e.g., `*_2013.csv`).

---

# 11. Behavioral Logic (Inline JS)

### 11.1 Accordion Controls  
- toggleAccordion  
- expandAll  
- collapseAll  

### 11.2 Navigation  
- openAndScroll  
- highlightNav  
- closeAllSections  

### 11.3 Expandable Content  
- expandNotes / collapseNotes  
- expandMessages / collapseMessages  
- toggleNoteText  

### 11.4 Sorting  
- sortTable  
- Supports numeric, text, and data-sort sorting  

### 11.5 Export  
- exportTableToCSV  
- exportTableToJSON  

All JS must remain inline and unmodified unless versioned.

---

# 12. Semantic Comments (Anchors)

Each section is preceded by a numbered comment:

- `<!-- 1. Patient Information -->`  
- …  
- `<!-- 14. Account Summary -->`  

These comments are **semantic anchors** used by:

- NotebookLM  
- comparison engines  
- export layers  
- audit workflows  

They must remain intact.

---

# 13. NotebookLM Structural Requirements

NotebookLM must:

- Ingest this file **line‑by‑line**  
- Treat all IDs, classes, and section numbers as locked  
- Use this structure to validate reconstruction  
- Refuse to generate output if structure is incomplete  
- Map VA text file content to these sections exactly  
- Perform section‑count verification before output  
- Declare how many output chunks will be required  

NotebookLM must not infer or invent structure.

---

# 14. Provenance & Privacy Notes  

- Privacy Guard notice in Military Service section  
- Year‑scoped export filenames  
- No external dependencies  
- Inline-only CSS/JS  

---

# 15. Authority of This Document  

`structure.md` is the authoritative structural reference for the BB Project master template.  
Any structural change must be:

1. Documented in `changelog.md`  
2. Reviewed via PR  
3. Approved  
4. Versioned appropriately  

This ensures zero drift and long‑term stability.
