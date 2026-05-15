Available integrations for K-12 family communication workflows:

- ParentSquare -- draft and schedule mass messages, individual messages, and event announcements; read delivery and open rate analytics
- Remind -- compose class and school-wide SMS/app messages; access read receipts
- ClassDojo -- write classroom story posts and direct messages to authorized guardians
- Translation service (DeepL, Google Translate API) -- translate drafted communications into parent home languages; flag for human review before sending
- School calendar integration -- pull upcoming events, early dismissal dates, and school holidays to reference in newsletters
- SIS contact lookup (read-only) -- retrieve authorized guardian contact records, preferred language, and communication channel preference
- Newsletter builder -- generate formatted HTML email newsletters ready for distribution via school email system

## Data Sources

Systems and platforms commonly accessed for K-12 family communication workflows.

### Communication Platforms

- **ParentSquare**
  - **Fields**: message_type (alert/post/direct), recipient_group, subject, body, attachments, schedule_datetime, delivery_stats (sent/delivered/opened)
- **Remind**
  - **Fields**: class_name, message_body, send_datetime, read_receipt, translation_status
- **ClassDojo**
  - **Fields**: story_post_type, photo_caption, message_body, recipient (class/individual), guardian_id

### SIS Family Contact Records (read-only)

- **PowerSchool**
  - **Fields**: guardian_id, student_id, relationship, contact_name, primary_phone, email, home_language, communication_opt_ins, lives_with (bool), custody_restrictions
- **Infinite Campus**
  - **Fields**: person_id, relationship_type, household, preferred_contact_method, language_preference, portal_access (bool)

### School Calendar

- **School calendar system (Tandem / SchoolMint / Google Calendar)**
  - **Fields**: event_name, event_type, date, time, location, audience (all/grade/class), description, rsvp_required (bool)

### Translation Reference

- **Top languages by district population**: Spanish, Vietnamese, Mandarin, Arabic, Somali, Portuguese, Haitian Creole, Tagalog, Hmong, Russian
  - **Fields**: language_code, student_count, guardian_preferred (bool), requires_certified_translator (bool)
