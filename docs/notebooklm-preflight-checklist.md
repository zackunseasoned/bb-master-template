# NotebookLM Pre‑Flight Checklist  
**BB Project — Deterministic Reconstruction Protocol**

NotebookLM must complete **all** steps below before generating any HTML output.

---

## 1. Source Ingestion Verification
NotebookLM must confirm it has fully ingested:

- README.md  
- structure.md  
- governance.md  
- changelog.md  
- master-template.html (raw)  
- All VA text files provided by the user  

NotebookLM must ingest all files **line‑by‑line**.

---

## 2. Schema & Structure Alignment
NotebookLM must verify:

- All 14 sections are present in structure.md  
- All section IDs match master-template.html  
- All table IDs match master-template.html  
- All semantic comments (`<!-- X. Section Name -->`) are present  
- All schema‑locked identifiers are intact  

If any mismatch exists, NotebookLM must halt.

---

## 3. VA Text File Integrity Check
NotebookLM must:

- Count the number of sections in the VA text file  
- Confirm all sections are present  
- Detect missing or truncated content  
- Validate ordering  
- Confirm no lines were skipped  

If any section is missing, NotebookLM must halt.

---

## 4. Output Planning (Mandatory)
Before generating any HTML, NotebookLM must:

1. Estimate total token usage  
2. Determine how many output chunks are required  
3. Present the plan to the user:

   - “This reconstruction will require X output sections.”  
   - “Section 1 will contain…”  
   - “Section 2 will contain…”  

4. Wait for explicit user approval  

NotebookLM must not generate HTML prematurely.

---

## 5. Confirmation Gate
NotebookLM must:

- Generate only **Section 1**  
- Present it to the user  
- Wait for confirmation  
- Only then proceed with remaining sections  

---

## 6. No Silent Truncation
NotebookLM must:

- Split output into multiple chunks if needed  
- Guarantee no content loss  
- Report chunk boundaries  
- Never silently truncate output  

---

## 7. Final Pre‑Flight Declaration
Before generating HTML, NotebookLM must state:

- All files ingested  
- All schema checks passed  
- All VA text sections accounted for  
- Output plan approved  
- Ready to begin Section 1  

Only then may reconstruction begin.
