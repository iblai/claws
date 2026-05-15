Available integrations for K-12 professional development workflows:

- Frontline Professional Growth -- access teacher PD transcripts, credit hours earned, course completions, and individual growth plan records
- Edivate (formerly PD 360) -- retrieve available PD course catalog, usage data, and completion records
- Evaluation platform (Frontline Evaluation & Development, iObservation) -- read observation scores and feedback notes (read-only; no write access to evaluations)
- Certification reference service -- look up state teacher certification requirements, renewal windows, and approved PD credit types
- PD planner -- generate individualized professional learning plans based on evaluation goals, certification deadlines, and school improvement priorities
- Learning management (Canvas, Google Classroom) -- surface relevant instructional resources aligned to the teacher's identified growth area

## Data Sources

Systems and platforms commonly accessed for K-12 teacher professional development workflows.

### Professional Development Platforms

- **Frontline Professional Growth**
  - **Fields**: employee_id, course_name, provider, completion_date, credit_hours, credit_type (CEU/clock_hour/graduate), pd_category, goal_alignment
- **Edivate (PD 360)**
  - **Fields**: course_title, subject_area, audience, duration_minutes, completion_status, self_reflection, rating
- **My Learning Plan (Frontline)**
  - **Fields**: pd_plan_goals, action_steps, resources, evidence_of_completion, supervisor_approval

### Evaluation and Coaching Records (read-only)

- **Frontline Evaluation & Development**
  - **Fields**: observation_date, observer, rubric_domain, indicator, rating (unsatisfactory/basic/proficient/distinguished), evidence_notes, growth_goal
- **iObservation (Learning Sciences International)**
  - **Fields**: classroom_visit_date, element_scores, look-for_checklist, feedback_summary, follow_up_date
- **Danielson FFT Domains** -- Domain 1 (Planning), Domain 2 (Classroom Environment), Domain 3 (Instruction), Domain 4 (Professional Responsibilities)

### Certification and Licensure

- **State certification database** (varies by state)
  - **Fields**: certificate_type, subject_endorsements, issue_date, expiration_date, renewal_credits_required, approved_providers
- **NBPTS (National Board Certification)**
  - **Fields**: certificate_area, component_scores, renewal_cycle, portfolio_deadline

### School Improvement Planning

- **District SIP / CSIP records**
  - **Fields**: improvement_goal, strategy, professional_learning_action, responsible_party, progress_indicator, target_date
