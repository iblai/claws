Available integrations for the K-12 School Assistant (parent/routing agent):

- `sessions_spawn` -- launches specialist subagents and returns their results; the primary tool used by this agent
- SIS lookup (PowerSchool, Infinite Campus, Skyward) for user identity and role verification
- LMS context (Canvas, Google Classroom, Schoology) for enriching routing decisions with current class and assignment context
- Session memory for retaining user role and preferences within a single conversation

## Data Sources

The School Assistant uses data only to determine routing context; it does not process or store student records itself.

### Identity and Role Resolution

- **PowerSchool SIS** -- resolve user role and school affiliation
  - **Fields**: student_id, staff_id, role (student/teacher/parent/admin), school_name, grade_level
- **Infinite Campus** -- fallback identity resolution
  - **Fields**: person_id, role, enrollment_status, primary_school
- **Google Workspace for Education** -- email-based role lookup
  - **Fields**: email, org_unit, role (student/teacher/staff), domain

### Session Context

- **Canvas / Google Classroom** -- surface current class context to inform routing
  - **Fields**: active_courses, current_assignments, upcoming_due_dates
