# Clinical Text Annotation Portfolio
### Named Entity Recognition (NER) & Relation Extraction

---

## About This Project

As a **Registered Nurse transitioning into Healthcare AI**, I completed a structured **clinical text annotation project** focused on **Named Entity Recognition (NER)** and **relation extraction** from unstructured clinical notes.

This portfolio demonstrates my ability to apply **clinical reasoning**, **medical language understanding**, and **annotation precision** to produce high-quality training data for **healthcare NLP and AI systems**.

All clinical notes were sourced from **publicly available, fully de-identified datasets** and annotated using standardized clinical NLP workflows.

**Target Roles:** Clinical Text Annotator 
**Focus Areas:** Clinical NER, modifiers, relation extraction  
**Availability:** Immediate | Remote

---

## 📋 Clinical Notes Annotated

| Specialty | Note Type | Entities Annotated | Relations Extracted |
|---------|-----------|-------------------|---------------------|
| Pediatrics | Bronchiolitis | 57 | 5 |
| Pediatrics | Kawasaki Disease | 88 | 9 |
| Cardiovascular | Acute STEMI | 93 | 6 |
| Cardiovascular | Aortic Stenosis | 83 | 10 |
| Emergency Medicine | Anaphylaxis | 119 | 15 |
| Emergency Medicine | Septic Shock | 110 | 10 |

**Total:** 6 clinical notes  
**Annotations:** 550 entities | 55 relations

---

## Entity Types Annotated

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


Entities were labeled using **standardized medical terminology** with contextual interpretation.

---

## 🔗 Relation Types Extracted

- DIAGNOSIS: "shows," "reveals," "consistent with," "confirms," "by criteria"
- TREATS: "for," "to treat," "given for," "administered for"
- CAUSES: "due to," "caused by," "secondary to," "post-procedure developed"
- INDICATION: "for," "requiring," "to evaluate," "indicated for"
  
The "Lawyer Test"
If you can't quote specific words justifying the relation, don't annotate it.
Relations were annotated only when **clinically meaningful and text-supported**.

---

## Clinical Modifiers Applied

Each relevant entity was enriched with structured clinical modifiers:

### Severity
Applies to: Diagnoses, symptoms, signs, test results
Values: Mild, Moderate, Severe, Critical

### Clinical Course
Applies to: Diagnoses, symptoms, signs
Values: Improving, Worsening, Stable, Progressive, Resolved, Persistent

### Disease Status
Applies to: Diagnoses ONLY
Values: Acute, Chronic, Active, Inactive, Resolved, Recurrent, Remote, Sudden onset, Gradual onset, Intermittent

### Negation
Applies to: Absent entities
Values: Present (entity EXISTS), Absent (entity DOES NOT exist)



---

## Tools & Methodology

- **Annotation Platform:** Label Studio  
- **Annotation Schema:** Custom ontology informed by **UMLS / SNOMED CT**  
- **Guideline Reference:** i2b2 Clinical NLP standards  
- **Quality Assurance:** Systematic self-review and consistency checks  

Annotations followed a **reproducible and documented workflow**.

---

## Annotation Statistics

- Total clinical notes:	6
- Total entities annotated:	550
- Total relations annotated:	55
- Entity types used:	18
- Relation types used:	3
- Average entities per note:	92
- Average relations per note:	9
---

## Clinical Expertise Applied

| Clinical Skill | Application in Annotation |
|---------------|--------------------------|
| Anatomy knowledge | Accurate localization |
| Pathophysiology | Disease pattern recognition |
| Medical terminology | Correct entity classification |
| Clinical reasoning | Context-aware disambiguation |
| Documentation experience | Understanding note structure |

---

## Sample Annotations

Representative annotated examples are included in the repository:

- Cardiovascular: [Acute STEMI](Portfolio/samples/sample_1_stemi.md)
- Emergency Medicine: [Septic Shock](Portfolio/samples/sample_2_septic_shock.md)
- Emergency Medicine: [Anaphylaxis](Portfolio/samples/sample_3_anaphylaxis.md)


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
   -  challenges-and-decisions.md
   -  future-work.md

 - analysis/
   - entity-relation-count.md
   - annotation-statistics.xlsx

 - schema/
   - label-studio-config.xml
   - annotation-schema.json
   - project-export.json

### Folder Descriptions

- **samples/** – Curated sample annotations with original clinical text excerpts, entities, and annotation rationale  
- **documents/** – Annotation guidelines, challenges encountered, and future improvement plans  
- **analysis/** – Quantitative annotation statistics and entity/relation counts  
- **schema/** – Annotation schemas and Label Studio configuration files  


---

## Background

- **Bachelor of Science in Nursing (BSc)**
- **Registered Nurse (RN)** – Active License  
- **Clinical documentation experience**
- **HIPAA & data privacy awareness**

---

## Work Preferences

- **Location:** Remote (Nigeria 🇳🇬)
- **Availability:** Immediate
- **Time Zone:** GMT+1 (flexible for US/EU teams)

---

## Contact
- Email: anita.o.aigbo@gmail.com
- LinkedIn: www.linkedin.com/in/anita-aigbomodion

---

## License & Data Use
- This portfolio is for demonstration purposes only.

### All medical images used are:
- Publicly available datasets (e.g., NIH Chest X-ray collections)
- Fully de-identified in accordance with HIPAA standards
- Used strictly for educational and portfolio demonstration

---

##  Open to Opportunities

Seeking roles in:
- Clinical Text Annotation
- Medical Entity Recognition
- Healthcare AI Training Data

---

 *This portfolio reflects clinically informed, high-quality annotation suitable for healthcare NLP model development.*

*Last Updated: December 2025*
