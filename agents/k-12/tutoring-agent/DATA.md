# Data Sources

Systems and platforms commonly accessed for K-12 tutoring workflows.

## Student Information Systems (SIS)

- **PowerSchool SIS** -- primary K-12 student information system
  - **Student records**: student_id, first_name, last_name, grade_level, school_name, homeroom_teacher
  - **Academic data**: current_grades (by course), assignment_scores, GPA, missing_assignments, attendance_rate
  - **Course enrollment**: course_name, section_id, teacher, period, room, term, credit_value
  - **Standards mastery**: standard_id, proficiency_level, assessment_date, growth_trend

- **Infinite Campus** -- comprehensive K-12 SIS
  - **Student profile**: student_number, name, grade, school, enrollment_status, primary_language
  - **Gradebook**: course, assignment_name, score, points_possible, category, weighted_grade
  - **Behavior**: incident_type, date, resolution, behavior_points

- **Skyward** -- K-12 student management
  - **Student data**: student_id, demographics, grade_level, school, counselor
  - **Grades**: course, marking_period, letter_grade, percentage, credits_earned
  - **Attendance**: date, period, status (present/absent/tardy), excuse_code

## Learning Management Systems (LMS)

- **Canvas (Instructure)** -- widely adopted K-12 LMS
  - **Courses**: course_name, teacher, syllabus, modules, learning_outcomes
  - **Assignments**: title, description, due_date, points_possible, rubric, submission_type
  - **Grades**: assignment_score, total_grade, late_policy_status, submission_timestamp
  - **Content**: pages, files, external_links, embedded_media, discussion_prompts

- **Schoology** -- K-12 focused LMS
  - **Course materials**: folders, pages, assignments, assessments, discussions, media_albums
  - **Gradebook**: assignment_grades, category_weights, grading_period, completion_status
  - **Analytics**: content_access_logs, time_on_task, submission_patterns

- **Google Classroom** -- Google-integrated LMS
  - **Classwork**: assignment_title, description, due_date, max_points, topic, materials
  - **Submissions**: student_submission, draft_status, turned_in_timestamp, grade, comments
  - **Stream**: announcements, class_comments, scheduled_posts

## Assessment & Adaptive Learning

- **NWEA MAP Growth** -- adaptive assessment platform
  - **Scores**: RIT_score, percentile, growth_projection, goal_areas, lexile_level
  - **Learning continuum**: instructional_area, skill_strand, readiness_level
  - **Growth data**: fall_score, winter_score, spring_score, met_projected_growth (bool)

- **iReady (Curriculum Associates)** -- diagnostic and instructional platform
  - **Diagnostic results**: overall_placement, domain_scores (by subject area), grade_level_equivalence
  - **Growth metrics**: scale_score, typical_growth, stretch_growth, placement_level
  - **Lesson data**: lesson_name, pass_rate, time_on_task, standards_addressed

- **Renaissance Star** -- assessment suite (Star Reading, Star Math, Star Early Literacy)
  - **Scores**: scaled_score, percentile_rank, grade_equivalent, zone_of_proximal_development
  - **Growth**: student_growth_percentile, benchmark_status (at/above/below/well_below)
  - **Skills**: domain, skill_name, mastery_level, instructional_priority

- **Khan Academy** -- free instructional platform
  - **Progress**: course_mastery_percentage, skill_levels, energy_points, badges
  - **Exercise data**: skill_name, attempts, correct_count, mastery_status, time_spent

## Standards & Curriculum

- **Common Core State Standards (CCSS)** -- math and ELA standards
  - **Standards**: standard_id (e.g. CCSS.MATH.6.RP.A.1), domain, cluster, grade, full_text
- **Next Generation Science Standards (NGSS)** -- science standards
  - **Standards**: performance_expectation, disciplinary_core_idea, practice, crosscutting_concept
- **State-specific standards** -- varies by state
  - **Standards**: standard_code, subject, grade_band, description, strand
