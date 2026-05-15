Available integrations for special education workflows:

- IEP platform (Frontline Special Ed & Interventions, Ideagen, Campus Special Education) -- read and draft IEP documents, goals, accommodations, and progress reports
- SIS special education module (PowerSchool Special Education, Infinite Campus Special Ed) -- access disability category, eligibility dates, placement type, and related services roster
- Progress monitoring tools (Aimsweb Plus, DIBELS) -- retrieve CBM data and growth trend lines for present level of performance narratives
- Accommodations registry -- look up approved accommodations per student for exam administration and classroom use
- Disability category reference (IDEA 13 categories) -- provide evidence-based instructional strategies aligned to disability type
- State compliance calendar -- flag IEP annual review and re-evaluation due dates based on eligibility and initial IEP dates

## Data Sources

Systems and platforms commonly accessed for K-12 special education workflows. All data in this domain is highly sensitive and protected under FERPA and IDEA.

### IEP Platforms

- **Frontline Special Ed & Interventions (formerly Enrich)**
  - **Fields**: iep_id, student_id, disability_categories, eligibility_date, annual_review_date, reevaluation_date, placement_type (LRE), IEP_goals (goal_text, measurement_criteria, baseline, target), related_services, accommodations, modifications, progress_notes
- **Ideagen (formerly Comply)**
  - **Fields**: iep_status, meeting_date, team_members, PLOP_summary, transition_plan, behavioral_intervention_plan
- **Campus Special Education (Infinite Campus)**
  - **Fields**: evaluation_summary, disability_category, placement, services_minutes_per_week, accommodation_list, goal_progress_scores

### Progress Monitoring

- **Aimsweb Plus (Pearson)**
  - **Fields**: measure (R-CBM, M-CBM, etc.), probe_score, percentile, rate_of_improvement, benchmark_status, trend_line
- **DIBELS 8th Edition (Amplify)**
  - **Fields**: composite_score, benchmark_category (well_below/below/at/above), subtest_scores, recommended_instructional_level

### 504 Plan Management

- **SIS 504 module (PowerSchool / IC)**
  - **Fields**: student_id, disability_category (functional), accommodation_list, review_date, authorized_staff

### Legal and Compliance References

- **IDEA 2004 -- 13 Disability Categories**: Specific Learning Disability, Other Health Impairment, Autism, Intellectual Disability, Emotional Disturbance, Speech/Language Impairment, Visual Impairment, Hearing Impairment, Orthopedic Impairment, Traumatic Brain Injury, Multiple Disabilities, Deaf-Blindness, Developmental Delay
- **State procedural safeguards and timelines** -- varies by state; typically 60 days from referral to eligibility determination
