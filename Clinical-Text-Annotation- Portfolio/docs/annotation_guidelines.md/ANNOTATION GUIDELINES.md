# Clinical Text Annotation Guidelines

Guidelines for manual annotation of clinical notes for **Named Entity Recognition (NER)** and **Relation Extraction**.

---

## 1. Entity Annotation Rules

### General Principles
- Annotate **minimal meaningful units** with essential context; exclude linking words.  
- Keep **standard disease names together**: e.g., "Acute bronchiolitis," "Heart failure with reduced ejection fraction."  
- Separate distinct concepts: test vs. result, medication vs. duration.

### Key Decisions
**Include in span:**
- "Crushing chest pain" → symptom includes quality descriptor  
- "Bilateral conjunctivitis" → laterality included  
- "Post-procedure echocardiogram" → temporal context included

**Exclude from span:**
- Linking words: "shows," "denies," "started on"  
- Diagnostic reasoning: "consistent with," "indicates"

---

## 2. Relation Annotation Rules

### Core Principle
- Annotate **only explicitly stated relations**.  
- **Do not infer** from medical knowledge.

### Required Language Examples

**DIAGNOSIS:** `"shows," "reveals," "consistent with," "confirms"`  
- ✅ "Chest X-ray shows pneumonia" → Annotate  
- ❌ "Urinalysis positive for nitrites" → Don't annotate

**TREATS:** `"for," "to treat," "given for"`  
- ✅ "Epinephrine for anaphylaxis" → Annotate  
- ❌ Discharge meds without indication → Don't annotate

**CAUSES:** `"due to," "caused by," "secondary to," "post-procedure developed"`  
- ✅ "Anaphylaxis secondary to peanut exposure" → Annotate  
- ✅ "Developed heart block post-TAVR" → Annotate  
- ❌ "Patient has hypertension and LVH" → Don't annotate

**INDICATION:** `"for," "requiring," "to evaluate," "indicated for"`  
- Use the **Lawyer Test**: if you cannot quote text justifying the relation, skip annotation.

---

## 3. Modifier Usage

**Severity** (applies to diagnoses, symptoms, signs, test results)  
- Values: Mild, Moderate, Severe, Critical  
- Note: Quality descriptors like "crushing" are **not** severity

**Clinical Course** (diagnoses, symptoms, signs)  
- Values: Improving, Worsening, Stable, Progressive, Resolved, Persistent  
- Key: Change over time  
- "Decreased/reducing" → Improving  
- "Resolved" → fully gone; "Improved" → better but still present

**Disease Status** (diagnoses only)  
- Values: Acute, Chronic, Active, Inactive, Resolved, Recurrent, Remote, Sudden onset, Gradual onset, Intermittent  
- Key: Disease **phase/nature**, not trajectory

**Negation** (absent entities)  
- Values: Present = entity exists, Absent = entity does not exist  
- Highlight the **entity**, not the negation word  
- Examples:  
  - "No pneumonia" → `[pneumonia]`, Absent  
  - "Denies chest pain" → `[chest pain]`, Absent

---

## 4. Key Distinctions

**Clinical Course vs Disease Status**  
- Clinical Course → trajectory over time (improving, worsening, stable)  
- Disease Status → disease phase (acute, chronic, active, resolved)

**Acute vs Acute Onset**  
- "Acute bronchiolitis" → Disease Status: Acute  
- "Acute onset chest pain" → temporal pattern included

**TEMPORAL Entity vs Modifier**  
- TEMPORAL entity → specific time expressions: "90 minutes ago," "3 days," "hospital day 3"  
- Temporal modifier removed to reduce confusion

---

## 5. Common Edge Cases

| Example | Annotation |
|---------|-----------|
| "Sensation of throat closing" | SYMPTOM |
| "100% occlusion of mid LAD with thrombus" | TEST_RESULT |
| "Mild-to-moderate respiratory distress" | Severity: Moderate (use higher value) |
| "No relief with nitroglycerin" | `[Nitroglycerin]` MEDICATION, Present; `[Relief]` Optional, Absent |
| "Bilateral conjunctivitis without discharge" | `[Bilateral conjunctivitis]` SIGN, Present; `[Discharge]` SIGN, Absent |

---

## 6. Discharge Instructions – What to Annotate

✅ **Annotate:**  
- Scheduled tests: "Repeat echo in 1 month" → `[Echocardiogram]` + `[1 month]`  
- Follow-up timing: "See cardiologist in 1 week" → `[1 week]`  
- Medication duration: "Continue aspirin for 6 weeks" → `[Aspirin]` + `[6 weeks]`  
- Activity restriction: "Avoid activity for 2 weeks" → `[2 weeks]`

❌ **Skip:**  
- Warning symptoms: "Return for fever, chest pain..."  
- General instructions: "Drink fluids," "Practice hygiene"  
- Patient education: "Learn EpiPen technique"  
- Hypothetical/future statements: "if" or "watch for" → Skip

---

## 7. Major Decisions Made

**Schema Changes:**  
- Removed: DISEASE, RISK_FACTOR, Temporal modifier  
- Added: PROCEDURE_RESULT, EXPOSURE, RATE

**Relation Strictness:**  
- Only explicit relations annotated  
- No medical inference  
- Exceptions: discharge diagnosis and temporal causation

**Negation Clarification:**  
- Present = entity exists  
- Absent = entity does not exist

---

## 8. Quality Checklist

Before finalizing annotations:  
- ✅ Entity boundaries clean  
- ✅ Negation correctly applied  
- ✅ Modifiers explicitly stated  
- ✅ Relations only annotated with explicit language  
- ✅ Consistent with documented decisions

---
