### **Clinical Text Annotation Project**

### 

Annotated corpus for Named Entity Recognition and Relation Extraction in clinical notes



###### **Project Overview**

This project presents a manually annotated corpus of 6 clinical notes covering cardiovascular, pediatric, and emergency medicine cases. The corpus supports development of clinical NLP systems for entity recognition, relation extraction, and clinical reasoning tasks.



###### **Quick Stats**

Notes: 6 (diverse specialties and note types)

Entity Types: 18

Relation Types: 4

Modifiers: 4

Annotation Approach: Conservative (explicit text only, no medical inference)



###### **Schema**

Entity Types (18)

PATIENT\_DEMOGRAPHICS, DIAGNOSIS, SYMPTOM, SIGN, VITAL\_SIGN, DIAGNOSTIC\_TEST, TEST\_RESULT, LAB\_VALUE, MEDICATION, DOSAGE, ROUTE,RATE, FREQUENCY, PROCEDURE, ANATOMY, EXPOSURE, TEMPORAL, PROCEDURE\_RESULT



###### **Relation Types (4)**

DIAGNOSIS: Finding/test → Disease

TREATS: Treatment → Disease

CAUSES: Factor → Disease

INDICATION: Procedure/Med → Reason



###### **Modifiers (4)**

Severity: Mild, Moderate, Severe, Critical

Clinical Course: Improving, Worsening, Stable, Progressive, Resolved, Persistent

Disease Status: Acute, Chronic, Active, Inactive, Resolved, Recurrent, Remote

Negation: Present (entity exists), Absent (entity doesn't exist)



###### **Files**

clinical-text-annotation-portfolio/

│

annotated\_notes/

├── Readme

├── Project1

schema/

├── schema.json

├── label\_studio\_config.xml

docs/

├── README.md

├── annotation\_guidelines.pdf

├── challenges\_and\_decisions.pdf

├── future\_work.md

analysis/

├── statistics.xlsx

├── entity\_relation\_counts.md

samples/

├── sample\_1\_stemi.md

├── sample\_2\_septic\_shock.md

└── sample\_3\_anaphylaxis.md





###### **Key Annotation Principles**

Text-based only: Annotate what's explicitly stated, not medical knowledge

Conservative relations: Only annotate with explicit relational language

Complete phrases: Include minimal meaningful units, exclude linking words

Strict negation: Highlight entity being negated, mark as Absent



###### **Example Annotations**

Entity Example

Text: "Severe symptomatic aortic stenosis"

Entity: \[Severe symptomatic aortic stenosis]

Type: DIAGNOSIS

Severity: Severe



###### **Relation Example**

Text: "Echocardiogram showed severe aortic stenosis"

Entities: \[Echocardiogram] (DIAGNOSTIC\_TEST), \[Severe aortic stenosis] (DIAGNOSIS)

Relation: Echocardiogram ──DIAGNOSIS──> Severe aortic stenosis



###### **Negation Example**

Text: "No focal consolidation"

Entity: \[Focal consolidation]

Type: TEST\_RESULT

Negation: Absent



###### **Usage**

For NER/Relation Extraction Research

Use as training/test corpus for clinical NLP models

Compare with i2b2, n2c2 benchmarks

Evaluate on entity recognition and relation extraction

For Annotation Tool Development

Use label\_studio\_config.xml as template

Apply guidelines to new clinical notes

Extend schema for specific domains

For Clinical Application Development

Extract structured data from notes

Build clinical decision support features

Support quality measurement initiatives



###### **Annotation Tool**

Label Studio with custom XML configuration (included)

Features:

18 entity type labels

4 relation types with arrow creation

4 context-dependent modifier dropdowns

Smart defaults to minimize clicks

Challenges Addressed

Distinguishing Clinical Course vs. Disease Status

Relation annotation strictness (explicit only)

Negation logic (Present = exists, Absent = doesn't exist)

Discharge instructions handling (skip warning signs)

See challenges\_and\_decisions.pdf for details.



###### **Limitations**

Small corpus: 6 notes (suitable for pilot, needs expansion)

Single annotator: No inter-annotator agreement calculated

Conservative relations: Some valid implicit relations not annotated (by design)

Limited specialties: Cardiovascular, pediatric, emergency only

English only: No multilingual support





###### **Future Work**

Expand to 20-30 notes across 10+ specialties

Multi-annotator validation

Train baseline NER and relation extraction models

Add temporal relations and co-reference resolution

Develop clinical decision support applications

See future\_work.pdf for details.



###### **Citation**

If you use this corpus, please cite:

Anita Aigbomodion (2025). Clinical Text Annotation Corpus for NER and Relation Extraction.

\[Institution/Project Name]. https://\[your-link]



###### **Contact**

Anita Aigbomodion, RN, BSN

Registered nurse with expertise in healthcare data analytics

HIPAA-certified with 1 year of clinical experience



Email: anitaj280@gmail.com

LinkedIn:

Portfolio:



###### **License**

MIT



###### **Acknowledgments**

Label Studio for annotation platform



Last Updated: December 2025

Version: 1.0

