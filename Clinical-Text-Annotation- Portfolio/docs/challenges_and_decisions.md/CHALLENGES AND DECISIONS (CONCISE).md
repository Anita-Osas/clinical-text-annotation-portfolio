# Annotation Challenges & Key Decisions

## 1. Major Conceptual Challenges

**Clinical Course vs Disease Status**  
- **Issue:** Overlapping terms (e.g., resolved, acute) caused confusion  
- **Resolution:**  
  - **Clinical Course** → trajectory over time (improving, worsening, resolved)  
  - **Disease Status** → disease phase/nature (acute, chronic, active, resolved)  
  - *Note:* "Resolved" may appear in both contexts

**Temporal Entity vs Modifier**  
- **Issue:** Temporal expressions were both entity and modifier  
- **Resolution:**  
  - **TEMPORAL entity** → time expressions to highlight ("90 minutes ago," "3 days")  
  - Removed temporal modifier completely  
  - Moved temporal descriptors (acute, chronic) to Disease Status

**Negation Logic (Present vs Absent)**  
- **Issue:** Initially reversed  
- **Resolution:**  
  - **Present** = entity exists  
  - **Absent** = entity does not exist  
  - Highlight the entity, not the negation word

---

## 2. Schema Design Decisions

- **Removed DISEASE entity type:** Redundant with DIAGNOSIS  
- **Rate vs Frequency:** Separated to maintain clinical accuracy (continuous therapies vs repeated doses)  
- **Added PROCEDURE_RESULT:** For post-procedure outcomes (e.g., "Well-seated valve")  
- **EXPOSURE vs DIAGNOSIS:**  
  - **DIAGNOSIS** → past medical conditions ("history of hypertension")  
  - **EXPOSURE** → behavioral/environmental factors ("smoking," "sick sibling")

---

## 3. Relation Annotation Dilemmas

- **Medical knowledge vs explicit text:**  
  - Example: Urinalysis positive → UTI. *Decision:* Don’t annotate; text doesn’t state diagnosis  
- **Discharge medications → conditions:**  
  - Example: "Amlodipine for hypertension" → Annotate only if indication explicitly stated  
- **Discharge diagnosis linking organisms to infection:**  
  - Example: "Blood cultures grew E. coli" + "E. coli urosepsis" → Annotate  
- **Temporal causation:**  
  - Example: "Post-TAVR complete heart block" → Annotate; temporal causation acceptable

---

## 4. Modifier Issues

- **Pain Quality ≠ Severity:** Quality descriptors (crushing, sharp) included in entity span, not severity  
- **Severity ranges:** "Mild-to-moderate" → choose higher value (Moderate) for consistency

---

## 5. Key Edge Cases

| Text | Annotation Decision |
|------|------------------|
| "No relief with nitroglycerin" | `[Nitroglycerin]` MEDICATION, Present; `[Relief]` Optional, Absent |
| "Wheezing decreased minimally" | Clinical Course: Improving |
| "Likely RSV given sick contacts" | Annotate entities only; skip relation (no explicit causation) |

---

## 6. Lessons Learned

- Start conservative → easier to add annotations later  
- Use modifier defaults → saves time  
- Trust note structure for context  
- Discharge instructions require special rules (skip warning signs)  
- Document decisions immediately → ensures consistency for future cases

---

## 7. Impact

| Metric | Before Guidelines | After Guidelines |
|--------|-----------------|----------------|
| Time per note | 2–3 hours | 1–1.5 hours |
| Annotation consistency | ~60–70% | ~90%+ |
