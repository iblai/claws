Available integrations for K-12 tutoring:

- LMS read access (Canvas, Schoology, Google Classroom) -- retrieve assignment descriptions, due dates, rubrics, and attached resources
- NWEA MAP Growth API -- look up a student's RIT score and instructional area recommendations to calibrate session difficulty
- iReady diagnostic data -- check domain placement levels to align explanations to the student's current instructional zone
- Khan Academy progress API -- review mastered and in-progress skills to avoid repeating content the student already knows
- Code execution sandbox (Python/JavaScript) -- run math computations and science simulations during tutoring sessions
- Standards reference (CCSS, NGSS) -- link explanations to grade-level learning objectives on request

## Data Sources

Systems and platforms commonly accessed for K-12 tutoring workflows.

### Student Information Systems (SIS)

- **PowerSchool SIS** -- grade-level and course enrollment context
  - **Fields**: grade_level, enrolled_courses, current_grades, missing_assignments, standards_mastery
- **Infinite Campus** -- academic profile
  - **Fields**: grade, gradebook (course, score, category), primary_language

### Learning Management Systems (LMS)

- **Canvas (Instructure)**
  - **Fields**: assignment_title, description, due_date, points_possible, rubric, submission_type, course_modules
- **Schoology**
  - **Fields**: course_materials, assignment_grades, category_weights, completion_status
- **Google Classroom**
  - **Fields**: classwork_title, description, due_date, max_points, materials, submission_status, teacher_comments

### Adaptive Assessment & Diagnostics

- **NWEA MAP Growth**
  - **Fields**: RIT_score, percentile, lexile_level, instructional_area, goal_areas, growth_projection
- **iReady (Curriculum Associates)**
  - **Fields**: overall_placement, domain_scores, grade_level_equivalence, typical_growth, stretch_growth
- **Renaissance Star**
  - **Fields**: scaled_score, grade_equivalent, zone_of_proximal_development, skill mastery_level

### Instructional Platforms

- **Khan Academy**
  - **Fields**: course_mastery_percentage, skill_levels, exercise attempts, correct_count, mastery_status, time_spent

### Standards

- **Common Core State Standards (CCSS)**
  - **Fields**: standard_id, domain, cluster, grade, full_text, mathematical_practices
- **Next Generation Science Standards (NGSS)**
  - **Fields**: performance_expectation, disciplinary_core_idea, science_and_engineering_practice, crosscutting_concept
- **State-specific standards**
  - **Fields**: standard_code, subject, grade_band, description, strand
