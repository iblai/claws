# Data Sources

Systems and platforms commonly accessed for K-12 family communication.

## Family Communication Platforms

- **ParentSquare** -- unified school-home communication
  - **Messages**: message_type (alert/newsletter/form/sign_up), recipients, send_date, read_receipts, translations
  - **Directory**: parent_name, email, phone, preferred_language, communication_preferences, linked_students
  - **Forms**: form_name, responses, due_date, completion_rate
  - **Calendar**: events, RSVPs, volunteer_sign_ups

- **Remind** -- messaging platform for schools
  - **Messages**: message_text, recipient_group (class/school/individual), delivery_method (app/SMS/email), read_status
  - **Contacts**: parent_phone, opt_in_status, language_preference

- **ClassDojo** -- classroom communication and behavior
  - **Messages**: teacher-parent messages, class_story_posts, school_story_posts, photo/video shares
  - **Behavior**: points (positive/needs_work), skill_name, student_portfolio_items
  - **Engagement**: parent_login_frequency, message_response_rate, story_views

- **Seesaw** -- student-driven digital portfolio and communication
  - **Portfolios**: student_work_samples, photos, videos, drawings, voice_recordings
  - **Communication**: family_messages, activity_comments, announcement_posts
  - **Engagement**: family_view_count, like_count, comment_count

- **Bloomz** -- school communication and volunteer management
  - **Features**: messages, calendar, volunteer_coordination, photo_sharing, behavior_tracking
  - **Directory**: parent_contacts, communication_preferences, volunteer_availability

## Student Information Systems (for parent portal data)

- **PowerSchool Parent Portal** -- parent-facing SIS access
  - **Visible data**: grades, attendance, assignments, teacher_comments, schedule, balance
  - **Notifications**: grade_alerts, attendance_alerts, missing_assignment_alerts

- **Infinite Campus Parent Portal** -- parent access to student information
  - **Visible data**: report_cards, progress_reports, schedule, fees, transportation, health_records

## Translation & Accessibility

- **Google Translate API / Microsoft Translator** -- automated translation
  - **Languages**: source_language, target_language, translated_text, confidence_score

- **TransACT** -- legally compliant translated parent notices
  - **Documents**: IDEA notices, Title III communications, enrollment forms
  - **Languages**: 20+ languages with legally verified translations

## School Calendars & Events

- **Google Calendar / Outlook** -- school event scheduling
  - **Events**: event_name, date, time, location, description, audience, recurrence
