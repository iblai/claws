Available integrations for K-12 student safety and content moderation:

- Content moderation classifier -- evaluate text submissions against K-12 safety taxonomy (violence, self-harm, adult content, cyberbullying, hate speech)
- School safety escalation webhook -- POST structured alert payloads to the district's safety notification system when an immediate-escalation determination is made
- Crisis resource lookup -- retrieve current crisis hotline numbers (988 Suicide & Crisis Lifeline, Crisis Text Line, local school counselor contact) to share with students in distress
- Audit log writer -- append moderation decisions with timestamp, category, confidence score, and disposition to the safety audit log in /sandbox/.openclaw/workspace/
- CIPA content filter integration -- query URL and domain classification service for safe browsing guidance
- Student support team notification -- trigger in-platform notification to the designated school counselor or administrator on escalation events

## Data Sources

Systems and platforms accessed for K-12 content moderation and student safety workflows.

### Content Moderation

- **Internal content classifier**
  - **Categories**: self_harm, violence, sexual_content, hate_speech, cyberbullying, drug_references, adult_language
  - **Fields**: content_snippet (truncated), category, confidence_score, disposition (safe/review/escalate), timestamp

- **SafeSearch / CIPA filter integration**
  - **Fields**: url, domain_category, safe_search_rating, block_reason

### Student Safety Platforms

- **Bark for Schools**
  - **Fields**: alert_type, platform_source, severity_level, student_id (tokenized), content_preview, recommended_action
- **Gaggle Safety Management**
  - **Fields**: trigger_type, content_category, review_status, escalated_to, timestamp

### Crisis Resources

- **988 Suicide & Crisis Lifeline** -- national phone/chat/text crisis line
- **Crisis Text Line** -- text HOME to 741741
- **School counselor directory** -- counselor_name, school, phone, availability_hours (from SIS staff directory)

### Safety Audit Log (internal workspace)

- **Path**: `/sandbox/.openclaw/workspace/safety-audit.log`
  - **Fields**: event_id, timestamp, session_id (anonymized), category, confidence, disposition, reviewer_notified (bool)
