# Data Sources

Systems and platforms commonly accessed for K-12 assessment creation and grading.

## Assessment Platforms

- **Illuminate Education (DnA)** -- assessment and data management
  - **Item bank**: question_id, standard_alignment, DOK_level, question_type, answer_key, distractor_analysis
  - **Assessment data**: assessment_name, administration_date, class_scores, item_analysis, standard_mastery
  - **Reports**: proficiency_distribution, growth_comparison, subgroup_performance

- **Mastery Connect (Instructure)** -- formative assessment tracker
  - **Assessments**: assessment_name, standards_assessed, student_scores, mastery_status
  - **Trackers**: standard_id, class_mastery_percentage, individual_student_mastery, trend_data
  - **Item analysis**: question_performance, distractor_frequency, difficulty_index

- **Edulastic** -- standards-based assessment platform
  - **Items**: question_type, standard, DOK, technology_enhanced (drag/drop, graphing, etc.)
  - **Results**: student_responses, auto_scored, rubric_scores, standards_performance

- **Google Forms / Microsoft Forms** -- simple quiz tools
  - **Quiz data**: question, response_options, correct_answer, point_value, student_responses, auto_grade

## Standardized Testing Data

- **NWEA MAP** -- adaptive benchmark assessment
  - **Scores**: RIT_score, percentile, grade_level_norm, instructional_area_scores, lexile/quantile
  - **Growth**: fall_to_spring_growth, projected_growth, growth_percentile, conditional_growth_index

- **SBAC (Smarter Balanced)** -- Common Core summative assessment
  - **Results**: scale_score, achievement_level (1-4), claim_scores, performance_task_score

- **PARCC / state-specific** -- state summative assessments
  - **Results**: scale_score, performance_level, subclaim_scores, year_over_year_comparison

- **ACT Aspire / PreACT / PSAT** -- college readiness benchmarks
  - **Scores**: composite, subject_scores, benchmark_status, predicted_ACT/SAT_range

## Standards & DOK References

- **Webb's Depth of Knowledge** -- cognitive complexity framework
  - **Levels**: DOK1 (recall), DOK2 (skill/concept), DOK3 (strategic thinking), DOK4 (extended thinking)

- **Bloom's Taxonomy** -- learning objective classification
  - **Levels**: remember, understand, apply, analyze, evaluate, create

- **Common Core / NGSS / state standards** -- alignment targets
  - **Standards**: code, description, grade, domain, cluster, related_standards
