Available integrations for K-12 writing feedback workflows:

- LMS submission retrieval (Canvas, Google Classroom, Schoology) -- fetch student drafts and assignment rubrics for in-context review
- Rubric engine -- apply analytic rubrics (6+1 Traits, PARCC, state writing rubrics) and return scored feedback per criterion
- Grammar and mechanics checker -- highlight surface-level errors without correcting them automatically
- Plagiarism signal detector -- flag stylistic inconsistencies for teacher review (no student-facing accusation)
- Google Docs / Microsoft Word comment API -- post inline feedback comments directly to the student's document when authorized
- Portfolio tracker (read-only) -- review prior writing samples to identify growth patterns and recurring challenges

## Data Sources

Systems and platforms commonly accessed for K-12 writing feedback workflows.

### LMS Submissions

- **Canvas (Instructure)**
  - **Fields**: assignment_title, rubric_criteria, submission_body, submission_timestamp, teacher_comments, draft_version
- **Google Classroom**
  - **Fields**: classwork_title, assignment_description, student_submission (doc_id), grade, teacher_feedback
- **Schoology**
  - **Fields**: assignment_name, rubric, submission_text, category, grading_period, revision_history

### Writing Rubrics

- **6+1 Traits Writing Rubric**
  - **Criteria**: ideas, organization, voice, word_choice, sentence_fluency, conventions, presentation
  - **Fields**: criterion_name, score (1-5), descriptor, next_steps
- **PARCC Analytical Writing Rubric**
  - **Criteria**: reading_comprehension, written_expression, knowledge_of_language_conventions
  - **Fields**: score (1-4 per criterion), anchor_text_evidence, elaboration_quality
- **State-specific writing rubrics**
  - **Fields**: criterion, performance_level (1-4), grade_level_descriptor

### Writing Portfolios

- **Seesaw / Fresh Grade**
  - **Fields**: entry_date, writing_sample_text, teacher_comment, student_reflection, skill_tags
- **Google Drive Portfolio folders**
  - **Fields**: file_name, created_date, last_modified, word_count, grade_level_tag

### Grammar and Style References

- **Common grammar error taxonomy** (K-12 ELA)
  - **Categories**: sentence_fragments, run-ons, subject-verb_agreement, comma_usage, capitalization, spelling, paragraph_structure
