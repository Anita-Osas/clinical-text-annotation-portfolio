# Future Work and Extensions

## 1. Corpus Expansion

**More Notes**  
- Target: 20-30 notes across 10+ specialties  
- Add oncology, psychiatry, surgery, neurology notes  
- Include different note types: ED notes, radiology reports, progress notes  

**More Annotations**  
- Multi-annotator validation → calculate inter-annotator agreement  
- Co-reference resolution → link repeated entity mentions  
- Temporal relations → connect events to timepoints  

---

## 2. Schema Enhancements

**Potential Additions**  
- **Entity types:** MEASUREMENT_UNIT, CLINICAL_DEPT, SOCIAL_DETERMINANT  
- **Relations:** PREVENTS, ADMINISTERED_VIA, OCCURRED_AT  
- **Modifiers:** Diagnostic Certainty (if needed)  

---

## 3. Model Development

**NER Models**  
- Train CRF, BiLSTM-CRF, BERT-based models (ClinicalBERT, BioBERT)  
- Evaluate per-entity F1 scores  
- Test few-shot learning  

**Relation Extraction**  
- Pipeline approach: NER → relation classification  
- Joint models: end-to-end  
- Evaluate relation F1 by type  

**Modifier Prediction**  
- Auto-predict severity, negation, disease status  
- Speed up annotation  

---

## 4. Evaluation

- Clinical expert review → validate medical accuracy  
- Inter-annotator agreement → quantify reliability  
- Compare with existing corpora → i2b2, n2c2, MIMIC-III  

---

## 5. Applications

**Clinical Decision Support**  
- Medication safety alerts  
- Diagnosis suggestions  
- Treatment recommendations  

**Quality Measurement**  
- Care gap identification  
- Guideline adherence checking  

**Research**  
- Phenotype extraction for cohort studies  
- Adverse event detection  
- Treatment effectiveness analysis  

**Medical Coding**  
- ICD-10 code suggestion  
- CPT code suggestion  

---

## 6. Tools

- Active learning interface → model suggests, annotator corrects  
- Consistency checker → flag inconsistencies across notes  
- Knowledge graph visualizer → show entities and relations  
- Timeline visualizer → display clinical events over time  
- Structured query interface → search annotated corpus  

---

## 7. Research Directions

- Uncertainty modeling → handle "likely," "possible," "suspected"  
- Temporal reasoning → extract event sequences, predict next events  
- Advanced negation → different negation types, speculation, hedging  
- Multi-modal integration → combine text with structured data  
- Explainability → interpretable relation extraction  

---

## 8. Immediate Next Steps

- Complete quality review of 6 annotated notes  
- Calculate annotation statistics (entity counts, relation counts per type)  
- Have clinical expert review sample annotations  
- Train baseline NER model on these 6 notes  
- Identify 10-15 additional notes for expansion
