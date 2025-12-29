# Clinical Text Annotation Project

Annotated corpus for **Named Entity Recognition (NER)** and **Relation Extraction** in clinical notes.

---

## Project Overview

This project presents a **manually annotated clinical text corpus** designed to support the development and evaluation of **clinical NLP systems**.  
The dataset focuses on **entity recognition**, **relation extraction**, and **clinical reasoning** tasks using real-world clinical note excerpts.

The corpus includes **6 clinical notes** spanning **cardiovascular**, **pediatric**, and **emergency medicine** domains.

---

## Quick Stats

- **Clinical Notes:** 6  
- **Specialties Covered:** Cardiovascular, Pediatric, Emergency Medicine  
- **Entity Types:** 18  
- **Relation Types:** 4  
- **Modifiers:** 4  
- **Annotation Approach:** Conservative  
  - Explicit text only  
  - No clinical inference  

---

## Annotation Schema

### Entity Types (18)

- PATIENT_DEMOGRAPHICS  
- DIAGNOSIS  
- SYMPTOM  
- SIGN  
- VITAL_SIGN  
- DIAGNOSTIC_TEST  
- TEST_RESULT  
- LAB_VALUE  
- MEDICATION  
- DOSAGE  
- ROUTE  
- RATE  
- FREQUENCY  
- PROCEDURE  
- ANATOMY  
- EXPOSURE  
- TEMPORAL  
- PROCEDURE_RESULT  

---

### Relation Types (4)

- **DIAGNOSIS:** Finding/Test → Disease  
- **TREATS:** Treatment → Disease  
- **CAUSES:** Factor → Disease  
- **INDICATION:** Procedure/Medication → Reason  

---

### Modifiers (4)

**Severity**
- Mild, Moderate, Severe, Critical

**Clinical Course**
- Improving, Worsening, Stable, Progressive, Resolved, Persistent

**Disease Status**
- Acute, Chronic, Active, Inactive, Resolved, Recurrent, Remote

**Negation**
- Present (entity exists)  
- Absent (entity does not exist)

---
## Repository Structure
clinical-text-annotation-portfolio/
- README.md
- samples/
 - sample_1_stemi.md
 - sample_2_septic_shock.md
 - sample_3_anaphylaxis.md
- documents/
 - README.md
 - annotation-guidelines.md
 - challenges-and-decisions.md
 - future-work.md
- analysis/
 - entity-relation-count.md
 - annotation-statistics.xlsx
- schema/
 - label-studio-config.xml
 - annotation-schema.json
 - project-export.json


---

## Sample Annotations

- **Cardiovascular Note:**  
  [Acute STEMI — Anterior Wall](samples/sample_1_stemi.md)

- **Emergency Medicine Note:**  
  [Septic Shock](samples/sample_2_septic_shock.md)

- **Emergency Medicine Note:**  
  [Anaphylaxis](samples/sample_3_anaphylaxis.md)

---

## Key Annotation Principles

- **Text-based only:**  
  Annotate only what is explicitly stated in the text.

- **Conservative relations:**  
  Relations are annotated **only when explicitly stated**.

- **Minimal meaningful spans:**  
  Capture complete clinical phrases while excluding linking words.

- **Strict negation handling:**  
  The entity is annotated and marked as **Absent** when negated.

---

## Annotation Examples

### Entity Example

**Text:**  
> “Severe symptomatic aortic stenosis”

**Annotation:**  
- Entity: *Severe symptomatic aortic stenosis*  
- Type: DIAGNOSIS  
- Severity: Severe

---

### Relation Example

**Text:**  
> “Echocardiogram showed severe aortic stenosis”

**Entities:**  
- *Echocardiogram* — DIAGNOSTIC_TEST  
- *Severe aortic stenosis* — DIAGNOSIS  

**Relation:**  
Echocardiogram ──DIAGNOSIS──> Severe aortic stenosis



---

### Negation Example

**Text:**  
> “No focal consolidation”

**Annotation:**  
- Entity: *Focal consolidation*  
- Type: TEST_RESULT  
- Negation: Absent

---

## Usage

### Clinical NLP Research
- Train and evaluate NER and relation extraction models
- Benchmark against i2b2 and n2c2 datasets
- Analyze entity and relation distributions

### Annotation Tool Development
- Use `label-studio-config.xml` as a template
- Apply annotation guidelines to new datasets
- Extend schema for domain-specific use cases

### Clinical Application Development
- Extract structured data from free-text notes
- Support clinical decision support systems
- Enable quality measurement and analytics pipelines

---

## Annotation Tool

Annotations were performed using **Label Studio** with a custom XML configuration.

**Features**
- 18 entity labels  
- 4 relation types with directional arrows  
- 4 modifier dropdowns  
- Optimized UI for reduced annotation friction  

**Challenges Addressed**
- Differentiating Clinical Course vs Disease Status  
- Enforcing strict relation annotation rules  
- Handling negation logic accurately  
- Excluding discharge warning signs  

See **documents/challenges-and-decisions.md** for details.

---

## Limitations

- Small corpus (6 notes) — suitable for pilot studies
- Single annotator — no inter-annotator agreement
- Conservative relations — implicit relations intentionally excluded
- Limited specialties
- English-only dataset

---

## Future Work

- Expand corpus to 20–30 notes across 10+ specialties
- Introduce multi-annotator validation
- Train baseline NER and relation extraction models
- Add temporal relations and coreference resolution
- Develop clinical decision support applications

See **documents/future-work.md** for details.

---

## Citation

If you use this corpus, please cite:

> **Aigbomodion, A. (2025).**  
> *Clinical Text Annotation Corpus for NER and Relation Extraction.*  

---

## Contact

**Anita Aigbomodion, RN, BSN**  
Registered Nurse | Healthcare Data Analyst  
HIPAA-certified | 1+ year clinical experience  

- **Email: *anita.o.aigbo@gmail.com*   
- **LinkedIn: *www.linkedin.com/in/anita-aigbomodion*  
---

## License

MIT License

---

## Acknowledgments

- Label Studio — annotation platform

---

**Last Updated:** December 2025  
**Version:** 1.0

