# master-template.html Audit Checklist  
**BB Project — Schema‑Locked Validation Guide**

Use this checklist to validate any version of `master-template.html` before merging into `main`.

---

# 1. Metadata Block
- [ ] Top‑level HTML comment present  
- [ ] Version number correct  
- [ ] Repository URL correct  
- [ ] Editing rules intact  
- [ ] Last updated date correct  

---

# 2. Document Root
- [ ] `<!DOCTYPE html>` present  
- [ ] `<html lang="en">` present  
- [ ] `<head>` present  
- [ ] `<body>` present  

---

# 3. Inline CSS
- [ ] All CSS inside `<style>`  
- [ ] No external CSS  
- [ ] Navigation styles intact  
- [ ] Table styles intact  
- [ ] Sorting styles intact  
- [ ] Expandable content styles intact  
- [ ] Print/PDF styles intact  

---

# 4. Header Section
- [ ] `<h1>` VA header present  
- [ ] `<h2>` Care summaries and notes  
- [ ] `.period` present  
- [ ] `.patient-bar` present  
- [ ] `id="top"` anchor present  

---

# 5. Navigation Panel
- [ ] All 14 nav buttons present  
- [ ] All IDs match structure.md  
- [ ] All onclick handlers correct  
- [ ] Order matches canonical sequence  

---

# 6. Global Controls
- [ ] Expand All present  
- [ ] Collapse All present  
- [ ] Controls only affect section‑level expansion  

---

# 7. Section‑Level Audit (Repeat for all 14 sections)
For each section:

- [ ] Semantic comment present (`<!-- X. Name -->`)  
- [ ] `<section id="...">` matches structure.md  
- [ ] `.sec-header` present  
- [ ] Expand indicator present  
- [ ] `.sec-content` present  
- [ ] `.table-container` present  
- [ ] `<table id="...">` matches structure.md  
- [ ] `.export-controls` present  
- [ ] CSV export button correct  
- [ ] JSON export button correct  
- [ ] Return‑to‑navigation link present  

---

# 8. Special Sections

## Secure Messaging
- [ ] Local expand/collapse controls present  
- [ ] `.msg-body` used correctly  

## Notes
- [ ] Local expand/collapse controls present  
- [ ] `.note-body` used correctly  

---

# 9. Inline JS Audit
- [ ] toggleAccordion  
- [ ] expandAll / collapseAll  
- [ ] openAndScroll  
- [ ] highlightNav  
- [ ] closeAllSections  
- [ ] expandNotes / collapseNotes  
- [ ] expandMessages / collapseMessages  
- [ ] toggleNoteText  
- [ ] sortTable  
- [ ] exportTableToCSV  
- [ ] exportTableToJSON  

All must be present and unmodified.

---

# 10. Final Validation
- [ ] No external dependencies  
- [ ] No minification  
- [ ] No schema drift  
- [ ] No missing IDs  
- [ ] No missing sections  
- [ ] No missing comments  
- [ ] All identifiers match structure.md  
- [ ] All behavior matches governance.md  

If all boxes are checked, the template is valid for merge.

