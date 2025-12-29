### **Future Work and Extensions**





###### **1. CORPUS EXPANSION**

More Notes

Target: 20-30 notes across 10+ specialties

Add: Oncology, psychiatry, surgery, neurology notes

Add: Different note types (ED notes, radiology reports, progress notes)

More Annotations

Multi-annotator validation: Calculate inter-annotator agreement

Co-reference resolution: Link repeated entity mentions

Temporal relations: Connect events to timepoints



###### 

###### **2. SCHEMA ENHANCEMENTS**

Potential Additions

Entity types: MEASUREMENT\_UNIT, CLINICAL\_DEPT, SOCIAL\_DETERMINANT

Relations: PREVENTS, ADMINISTERED\_VIA, OCCURRED\_AT

Modifiers: Diagnostic Certainty (if needed)



###### 

###### **3. MODEL DEVELOPMENT**

NER Models

Train CRF, BiLSTM-CRF, BERT-based models (ClinicalBERT, BioBERT)

Evaluate per-entity F1 scores

Test few-shot learning

Relation Extraction

Pipeline approach (NER then relation classification)

Joint models (end-to-end)

Evaluate relation F1 by type

Modifier Prediction

Auto-predict severity, negation, disease status

Use to speed up annotation



###### 

###### **4. EVALUATION**

Clinical expert review: Validate medical accuracy

Inter-annotator agreement: Quantify reliability

Compare with existing corpora: i2b2, n2c2, MIMIC-III



###### 

###### **5. APPLICATIONS**

Clinical Decision Support

Medication safety alerts

Diagnosis suggestions

Treatment recommendations

Quality Measurement

Care gap identification

Guideline adherence checking

Research

Phenotype extraction for cohort studies

Adverse event detection

Treatment effectiveness analysis

Medical Coding

ICD-10 code suggestion

CPT code suggestion







###### **6. TOOLS**

Active learning interface: Model suggests, annotator corrects

Consistency checker: Flag inconsistencies across notes

Knowledge graph visualizer: Show entities and relations

Timeline visualizer: Display clinical events over time

Structured query interface: Search annotated corpus





###### **7. RESEARCH DIRECTIONS**

Uncertainty modeling: Handle "likely," "possible," "suspected"

Temporal reasoning: Extract event sequences, predict next events

Advanced negation: Different negation types, speculation, hedging

Multi-modal integration: Combine text with structured data

Explainability: Interpretable relation extraction





###### **8. IMMEDIATE NEXT STEPS**

Complete quality review of 6 annotated notes

Calculate annotation statistics (entity counts, relation counts per type)

Have clinical expert review sample annotations

Train baseline NER model on these 6 notes

Identify 10-15 additional notes for expansion





