Available integrations for K-12 assessment workflows:

- LMS assessment builder (Canvas Quizzes, Schoology Assessments, Google Forms) -- create and publish assessments with automatic grade passback
- Formative / Edulastic -- generate standards-tagged question banks and import/export QTI-formatted items
- Auto-grader (multiple choice, short answer, fill-in-the-blank) -- score submissions and produce class-level performance reports
- Rubric builder -- generate analytic or holistic rubrics aligned to specific standards
- SIS gradebook write (teacher-authorized) -- push finalized scores to PowerSchool, Infinite Campus, or Skyward gradebooks after teacher approval
- Standards reference (CCSS, NGSS, state databases) -- tag every question to a standard code at generation time

## Data Sources

Systems and platforms commonly accessed for K-12 assessment workflows.

### Assessment Platforms

- **Canvas Quizzes (New Quizzes)**
  - **Fields**: quiz_id, question_type, question_text, answer_options, correct_answer, standard_tag, points, time_limit
- **Schoology Assessments**
  - **Fields**: assessment_id, item_bank_questions, rubric, grading_period, category_weight, submission_count
- **Edulastic**
  - **Fields**: test_name, standard_alignment, DOK_level, question_items, auto_graded (bool), performance_band
- **Formative**
  - **Fields**: activity_name, question_items, live_results, class_mastery_percentage, per-student_scores

### Gradebooks (read/write with teacher authorization)

- **PowerSchool Gradebook**
  - **Fields**: course_section, assignment_name, score, points_possible, category, grade_period, comment
- **Infinite Campus Gradebook**
  - **Fields**: course, assignment, score, weighted_grade, missing_flag, late_flag
- **Skyward Gradebook**
  - **Fields**: marking_period, assignment, percentage_score, letter_grade, credits_earned

### Standards

- **CCSS** -- standard_id, domain, cluster, grade, full_text
- **NGSS** -- performance_expectation, disciplinary_core_idea, grade_band
- **Depth of Knowledge (DOK)** -- dok_level (1-4), descriptor

### Item Banks

- **State-provided item banks**
  - **Fields**: item_id, standard_code, dok_level, question_type, answer_key, passage (if applicable)
- **Publisher item banks (HMH, Savvas, McGraw-Hill)**
  - **Fields**: chapter, lesson, standard, question_type, answer_key, lexile_level
