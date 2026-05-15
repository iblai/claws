Available integrations for K-12 curriculum alignment workflows:

- Atlas (Faria) API -- read curriculum maps, unit structures, and existing standards tags; write updated alignment data after review
- Chalk API -- retrieve unit plans and pacing calendars; update standards alignment fields
- CASE Network (IMS Global) -- machine-readable standards lookup and crosswalk queries between frameworks
- EdReports search -- retrieve published alignment and usability ratings for commercially available instructional materials
- Standards databases (CCSS, NGSS, C3 Framework, state-specific) -- look up standard text, hierarchy, and related standards
- Spreadsheet export (Google Sheets, Excel) -- generate alignment matrices as downloadable reports for curriculum team review

## Data Sources

Systems and platforms commonly accessed for K-12 curriculum alignment workflows.

### Curriculum Mapping Platforms

- **Atlas (Faria Education Group)**
  - **Fields**: unit_name, grade, subject, standards_addressed, essential_questions, enduring_understandings, alignment_coverage (taught/assessed/gap), revision_history
- **Chalk**
  - **Fields**: unit_plans, lesson_plans, standards_alignment, pacing_calendar, coverage_percentage_by_domain
- **Eduplanet21**
  - **Fields**: stage1_desired_results, stage2_evidence, stage3_learning_plan, transfer_goals, standards_alignment

### Standards Databases

- **CASE Network (IMS Global)**
  - **Fields**: framework_id, standard_id, full_statement, grade_level, parent_standard, is_child_of, is_related_to, precedes, replaced_by
- **Academic Benchmarks / Instructure**
  - **Fields**: authority, subject, grade, standard_code, standard_text, crosswalk (source_standard → target_standard, alignment_strength)
- **CCSS** -- standard_id, domain, cluster, grade, full_text
- **NGSS** -- performance_expectation, disciplinary_core_idea, practice, crosscutting_concept
- **C3 Framework (Social Studies)** -- dimension, indicator, grade_band
- **National Core Arts Standards** -- process (creating/performing/responding/connecting), anchor_standard, grade_band
- **SHAPE America (PE/Health)** -- standard_number, indicator, grade_band

### Instructional Materials Reviews

- **EdReports**
  - **Fields**: publisher, title, grade, subject, overall_rating, gateway_1 (focus/coherence), gateway_2 (rigor), gateway_3 (usability), reviewed_date
- **Louisiana Believes Curriculum Reviews**
  - **Fields**: tier (1/2/3), subject, grade, overall_score, indicator_scores
