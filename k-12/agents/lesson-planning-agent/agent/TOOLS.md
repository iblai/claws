Available integrations for K-12 lesson planning:

- LMS write access (Canvas, Schoology, Google Classroom) -- draft and publish lesson modules, assignment shells, and pacing calendars directly to the teacher's course
- Standards API (CCSS, NGSS, state standards) -- look up standard text and metadata by code to embed accurate citations in plans
- Curriculum mapping platform (Atlas, Chalk) -- read existing unit maps to ensure new plans align with the district curriculum sequence
- Pacing calendar integration -- check the school calendar for instructional days, holidays, and assessment windows before scheduling units
- Google Drive / OneDrive -- save lesson plan documents to the teacher's designated folder
- Class roster data (SIS read-only) -- retrieve grade level and demographic summary to inform differentiation suggestions

## Data Sources

Systems and platforms commonly accessed for K-12 lesson planning workflows.

### Learning Management Systems (LMS)

- **Canvas (Instructure)**
  - **Fields**: course_id, course_name, modules, pages, assignments, learning_outcomes, pacing_calendar
- **Schoology**
  - **Fields**: course_materials, folder_structure, grading_periods, grading_categories
- **Google Classroom**
  - **Fields**: course_topics, classwork_items, scheduled_posts, teacher_materials

### Curriculum Mapping Platforms

- **Atlas (Faria Education Group)**
  - **Fields**: unit_name, grade, subject, standards_addressed, essential_questions, enduring_understandings, alignment_coverage
- **Chalk**
  - **Fields**: unit_plans, lesson_plans, standards_alignment, pacing_calendar, coverage_percentage_by_domain
- **Eduplanet21**
  - **Fields**: stage1_desired_results, stage2_evidence, stage3_learning_plan, transfer_goals, essential_questions

### Standards Databases

- **CCSS** -- Common Core Math and ELA
  - **Fields**: standard_id (e.g. CCSS.MATH.6.RP.A.1), domain, cluster, grade, full_text
- **NGSS** -- Next Generation Science Standards
  - **Fields**: performance_expectation, disciplinary_core_idea, practice, crosscutting_concept, grade_band
- **State standards databases**
  - **Fields**: standard_code, subject, grade_band, description, strand, adoption_year

### Student Roster Context (read-only, aggregated)

- **PowerSchool / Infinite Campus**
  - **Fields**: grade_level, class_size, ELL_percentage, IEP_count (anonymized), free_reduced_lunch_percentage
