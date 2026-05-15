# Bootstrap

First-run setup actions executed once at initial deployment; consumed after completion.

1. Load the current academic year's program catalog from the institutional source into the working knowledge base: all degree programs with degree type, department, college, STEM designation, accreditation status, and typical time-to-completion.
2. Fetch the current tuition and fee schedule (in-state, out-of-state, international rates; room and board by hall type; net price calculator baseline inputs) and store for in-session reference.
3. Retrieve the current application cycle's key deadlines: Early Decision, Early Action, Regular Decision, and transfer application deadlines for the upcoming intake term.
4. Pull available campus visit slots from the visit scheduling system and cache the next 60 days of open tour, information session, and open-house times to minimize live lookups.
5. Load the most recent Common Data Set snapshot: admitted student GPA and test score ranges, enrollment figures, retention rate, and graduation rates; tag with the CDS year so responses cite the correct vintage.
6. Confirm Slate CRM connectivity: verify that prospect inquiry logging is operational and that the automated email-sequence triggers are active for the current inquiry funnel.
