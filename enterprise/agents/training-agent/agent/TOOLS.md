Available integrations for employee learning, compliance training, and development planning:

- Cornerstone OnDemand, Docebo, or Workday Learning for enrollment, completion tracking, and compliance deadline monitoring
- LinkedIn Learning or Coursera for Enterprise for external course catalog browsing and recommended content
- Skills framework API for mapping job roles to required competencies and identifying skill gaps
- HRIS read-only access for employee role, tenure, and location to personalize learning path recommendations
- Notification system (Slack, email) for sending training reminders, completion confirmations, and deadline alerts

## Data Sources

Systems and platforms accessed for employee learning management, compliance training tracking, and skills development.

### Learning Management Systems

- **Cornerstone OnDemand** -- enterprise LMS and talent management
  - **Learning assignment**: assignment_id, employee_id, course_id, course_title, learning_type, due_date, status, completion_date, score, required_flag, assigned_by
  - **Course**: course_id, title, category, duration_minutes, delivery_type, provider, version, compliance_required, last_updated, languages
  - **Transcript**: record_id, employee_id, course_id, completion_date, score, certificate_expiry, credits_earned
- **Docebo** -- cloud learning platform
  - **Enrollment**: enrollment_id, user_id, course_id, status, enrolled_date, completion_date, score, certificate_issued, time_spent_minutes
  - **Course**: course_id, name, category, type, duration, language, rating, enrolled_count, completion_rate

### External Content Providers

- **LinkedIn Learning** -- professional development library
  - **Course**: course_id, title, author, duration, skill_tags, level, language, release_date, rating, viewer_count
  - **Learning path**: path_id, title, courses, duration, skills_covered, completion_count
- **Coursera for Teams** -- academic and professional courses
  - **Course**: course_id, name, university, specialization, skills_taught, level, duration_weeks, rating, enrolled_count
  - **Certificate**: certificate_id, learner_id, course_id, issue_date, expiry_date, credential_url, verification_code

### Skills & Competency Frameworks

- **Workday Skills Cloud** -- skills ontology and mapping
  - **Skill**: skill_id, name, category, level, related_skills, job_profiles_requiring, proficiency_scale
  - **Employee skill**: employee_id, skill_id, proficiency_level, source, assessed_date, verified_by
- **Degreed** -- skills platform and LXP
  - **Skill score**: employee_id, skill, score, percentile, articles_read, courses_completed, assessments_passed, last_activity
  - **Learning pathway**: pathway_id, title, skills, resources, duration, assigned_to_roles

### Compliance Training

- **Navex Global (EthicsPoint)** -- compliance and ethics training
  - **Training assignment**: assignment_id, employee_id, course_name, regulation, jurisdiction, due_date, completion_date, passed, attempts
  - **Compliance course**: course_id, title, regulation, audience, frequency, jurisdiction, languages, version, duration
- **KnowBe4** -- security awareness training
  - **Campaign**: campaign_id, name, phish_link_rate, open_rate, reply_rate, training_completion_rate, risk_score, start_date, end_date
  - **User training**: user_id, module, completion_date, score, time_spent, phishing_tests_sent, phishing_tests_failed
