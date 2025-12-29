###  **CHALLENGES AND DECISIONS (CONCISE)**



##### **Annotation Challenges and Key Decisions**

##### 

###### **1.MAJOR CONCEPTUAL CHALLENGES**



Challenge: Clinical Course vs. Disease Status Confusion

Issue: Both can use similar words (resolved, acute)

Resolution:

Clinical Course = trajectory over time (improving, worsening, resolved)

Disease Status = disease phase/nature (acute, chronic, active, resolved)

"Resolved" can be both depending on context



Challenge: Temporal Entity vs. Modifier Confusion

Issue: Created "Temporal" as both entity AND modifier

Resolution:

TEMPORAL entity = time expressions to highlight ("90 minutes ago," "3 days")

Removed temporal modifier completely

Moved temporal descriptors (acute, chronic) to Disease Status modifier



Challenge: Negation Logic (Present vs. Absent)

Issue: Initially backwards (Negation Present = entity absent)

Resolution:

Present = entity EXISTS

Absent = entity DOESN'T exist

Highlight entity being negated, not negation word





###### **2. SCHEMA DESIGN DECISIONS**

Decision: Remove DISEASE Entity Type

Issue: DISEASE vs. DIAGNOSIS redundancy

Resolution: Use only DIAGNOSIS for all diseases/conditions (current and historical)

Rationale: Eliminates ambiguity, context indicates timing



Decision: Rate vs Frequency use

Issue: Substituting frequency for rate would misrepresent continuous therapies, since they are not repeated at intervals but delivered without interruption.

Resolution: Clearly separate rate and frequency in the annotation schema

Rationale: Maintaining this distinction preserves clinical accuracy



Decision: Add PROCEDURE\_RESULT Entity Type

Issue: Post-procedure outcomes didn't fit existing types

Examples: "Well-seated valve," "TIMI 3 flow restored"

Resolution: Added PROCEDURE\_RESULT for procedural outcomes



Decision: EXPOSURE vs. DIAGNOSIS for Risk Factors

Issue: Past medical conditions could be either

Resolution:

DIAGNOSIS: Past medical conditions ("history of hypertension")

EXPOSURE: Behavioral/environmental factors ("smoking," "sick sibling," "daycare")



###### **3. RELATION ANNOTATION DILEMMAS**

Dilemma: Medical Knowledge vs. Explicit Text

Case: Urinalysis → UTI

Text: "Urinalysis positive for nitrites, leukocyte esterase"

Dilemma: Medically diagnostic of UTI, but text doesn't state it

Decision: DON'T annotate relation without explicit diagnostic statement

Rationale: Maintains objectivity, reproducibility



Case: Discharge Medications → Conditions

Text: Patient has hypertension, discharge med is amlodipine

Dilemma: Medically we know amlodipine treats hypertension

Decision: DON'T annotate unless explicitly stated

Rationale: Medication indication not always obvious, requires drug knowledge

Exception: If text says "amlodipine for hypertension," then annotate



Case: E. coli → Urosepsis

Text: "Blood cultures grew E. coli" + Discharge dx: "E. coli urosepsis"

Decision: ANNOTATE - discharge diagnosis provides textual link

Rationale: Text explicitly names "E. coli urosepsis" connecting organism to infection

Dilemma: Temporal Causation



Case: "Post-TAVR complete heart block"

Dilemma: Doesn't say "caused by," just temporal association

Decision: ANNOTATE - temporal causation acceptable

Rationale: "Post-procedure developed" is standard medical language for complications





###### **4. MODIFIER ISSUES**

Issue: Pain Quality ≠ Severity

Problem: "Crushing pain" assumed severe

Resolution: Quality descriptors (crushing, sharp, dull) are NOT severity

Decision: Include in entity span, don't assign severity unless explicitly stated



Issue: Severity Ranges

Problem: "Mild-to-moderate" - which to choose?

Decision: Select higher value (Moderate)

Rationale: Conservative clinical approach, consistency



###### **5. KEY EDGE CASES**

"No relief with nitroglycerin"

Resolution:

Nitroglycerin: Negation Present (med was given)

Relief: Negation Absent (didn't occur)



"Wheezing decreased minimally"

Resolution: Clinical Course: Improving (any decrease = improvement)

"Likely RSV given sick contacts"

Resolution: Annotate entities, skip relation (no explicit causation stated)



###### **6. LESSONS LEARNED**

Start conservative - easier to add annotations later than remove bad ones

Modifier defaults save time - configure tool with smart defaults

Section context matters - trust note structure for context

Discharge instructions are different - need special rules (skip warning signs)

Document decisions immediately - creates precedents for future cases



**7. IMPACT**

Before strict guidelines:

Time per note: 2-3 hours

Consistency: ~60-70%

After implementing decisions:

Time per note: 1-1.5 hours

Consistency: ~90%+

