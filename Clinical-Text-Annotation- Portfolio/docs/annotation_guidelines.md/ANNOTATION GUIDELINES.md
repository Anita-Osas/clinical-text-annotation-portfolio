### **ANNOTATION GUIDELINES** 



#### **Clinical Text Annotation Guidelines - Key Notes**



###### **1.ENTITY ANNOTATION RULES**



General Principles



Annotate minimal meaningful unit, include essential context, exclude linking words.

Keep standard disease names together: "Acute bronchiolitis," "Heart failure with reduced ejection fraction"

Separate distinct concepts: Test vs. result, medication vs. duration

Key Decisions

Include in span:

"Crushing chest pain" (quality descriptor is part of symptom)

"Bilateral conjunctivitis" (laterality with finding)

"Post-procedure echocardiogram" (temporal context with test)

Exclude from span:

Linking words: "shows," "denies," "started on"

Diagnostic reasoning: "consistent with," "indicates"





###### **2.RELATION ANNOTATION RULES**



Core Principle



Only annotate relations explicitly stated in text. Do NOT infer from medical knowledge.



Required Language



DIAGNOSIS: "shows," "reveals," "consistent with," "confirms," "by criteria"

✅ "Chest X-ray shows pneumonia" → Annotate

❌ "Urinalysis positive for nitrites" (no diagnosis stated) → Don't annotate



TREATS: "for," "to treat," "given for," "administered for"

✅ "Epinephrine for anaphylaxis" → Annotate

❌ Discharge meds with no stated indication → Don't annotate



CAUSES: "due to," "caused by," "secondary to," "post-procedure developed"

✅ "Anaphylaxis secondary to peanut exposure" → Annotate

✅ "Developed heart block post-TAVR" → Annotate (temporal causation)

❌ Patient has hypertension and LVH (no causal language) → Don't annotate



INDICATION: "for," "requiring," "to evaluate," "indicated for"

The "Lawyer Test"

If you can't quote specific words justifying the relation, don't annotate it.





###### **3.MODIFIER USAGE**



Severity

Applies to: Diagnoses, symptoms, signs, test results

Values: Mild, Moderate, Severe, Critical

Note: "Crushing" = quality descriptor, NOT severity



Clinical Course

Applies to: Diagnoses, symptoms, signs

Values: Improving, Worsening, Stable, Progressive, Resolved, Persistent

Key: Describes CHANGE over time (requires comparison)

"Decreased/reducing" = Improving

Use "Resolved" when completely gone, "Improved" when better but still present.



Disease Status

Applies to: Diagnoses ONLY

Values: Acute, Chronic, Active, Inactive, Resolved, Recurrent, Remote, Sudden onset, Gradual onset, Intermittent

Key: Describes disease PHASE/NATURE, not trajectory



Negation

Applies to: Absent entities

Values: Present (entity EXISTS), Absent (entity DOES NOT exist)

Critical: Highlight the entity being negated, NOT the negation word

"No pneumonia" → Highlight \[pneumonia], Negation: Absent

"Denies chest pain" → Highlight \[chest pain], Negation: Absent





###### **4. KEY DISTINCTIONS**



Clinical Course vs. Disease Status

Clinical Course = trajectory (improving, worsening, stable)

Disease Status = phase (acute, chronic, active, resolved)

"Resolved" can be BOTH depending on context



Acute vs. Acute Onset

"Acute bronchiolitis" → Disease Status: Acute (keep in span)

"Acute onset chest pain" → Keep in span, describes temporal pattern



TEMPORAL Entity vs. Modifier

TEMPORAL entity = specific time expressions to highlight: "90 minutes ago," "3 days," "hospital day 3"

NO temporal modifier (removed from schema - was causing confusion)

Disease status includes: Acute, Chronic (these describe disease phase, not temporal expressions)





###### **4.COMMON EDGE CASES**

###### 

i. "Sensation of throat closing"

→ SYMPTOM (subjective patient experience)

ii. "100% occlusion of mid LAD with thrombus"

→ Keep together as one TEST\_RESULT

ii. "Mild-to-moderate respiratory distress"

→ Severity: Moderate (use higher value from range)

iv. "No relief with nitroglycerin"

→ \[Nitroglycerin]: MEDICATION, Negation: Present (med was given)

→ \[Relief]: Optional entity, Negation: Absent (didn't occur)

v. "Bilateral conjunctivitis without discharge"

→ \[Bilateral conjunctivitis]: SIGN, Negation: Present

→ \[Discharge]: SIGN, Negation: Absent





###### **5.DISCHARGE INSTRUCTIONS - WHAT TO ANNOTATE**



✅ DO Annotate:

Scheduled tests: "Repeat echo in 1 month" → \[Echocardiogram] + \[1 month]

Follow-up timing: "See cardiologist in 1 week" → \[1 week]

Medication duration: "Continue aspirin for 6 weeks" → \[Aspirin] + \[6 weeks]

Activity restriction duration: "Avoid activity for 2 weeks" → \[2 weeks] only

❌ DON'T Annotate:

Warning symptoms (return precautions): "Return for fever, chest pain..." → SKIP

General instructions: "Drink fluids," "Practice hygiene" → SKIP

Patient education: "Learn EpiPen technique," "Read labels" → SKIP

Hypothetical futures: Any "if" or "watch for" statements → SKIP

Rationale: These are instructions/education, not current clinical findings.





###### **6.MAJOR DECISIONS MADE**



Schema Changes

Removed: 

DISEASE (redundant with DIAGNOSIS),

RISK\_FACTOR (use DIAGNOSIS or EXPOSURE)

Temporal modifier (was causing confusion)



Added: 

PROCEDURE\_RESULT (post-procedure outcomes)

EXPOSURE (for non-disease risk factors)

RATE ( speed or pattern at which a medication is administered)



Relation Strictness

Conservative approach: Only annotate explicit relations

No medical inference: Don't annotate "Amlodipine treats hypertension" without explicit statement

Exception: Discharge diagnosis provides link (e.g., "E. coli urosepsis" connects organism to infection)

Exception: Temporal causation ("post-procedure developed") is acceptable



Negation Clarification

Present = entity exists

Absent = entity doesn't exist

Initially had this backwards!



###### **7. QUALITY CHECKLIST**

Before finalizing annotations:

✅ Entity boundaries clean (no extra words)?

✅ Negation correctly applied (Present/Absent logic)?

✅ Modifiers only used when explicitly stated?

✅ Relations only annotated with explicit language?

✅ Consistent with decisions documented here?





