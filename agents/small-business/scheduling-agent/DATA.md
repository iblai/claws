# Data Sources

Systems and platforms commonly accessed for small business scheduling.

## Scheduling & Booking Platforms

- **Calendly** -- appointment scheduling
  - **Events**: event_type, date, time, duration, invitee_name, invitee_email, status (scheduled/canceled/rescheduled)
  - **Availability**: schedule_rules, buffer_time, minimum_notice, date_overrides, timezone
  - **Analytics**: bookings_by_type, cancellation_rate, popular_times, average_lead_time

- **Acuity Scheduling (Squarespace)** -- online booking for service businesses
  - **Appointments**: client_name, service_type, provider, date, time, duration, price, intake_form_responses
  - **Packages**: package_name, sessions_total, sessions_remaining, expiration_date
  - **Availability**: calendars_by_staff, blocked_times, recurring_availability, timezone

- **Square Appointments** -- booking with POS integration
  - **Bookings**: customer, service, staff, date, time, duration, price, status, no_show_flag
  - **Services**: service_name, duration, price, staff_assignments, category
  - **Customer history**: visit_count, last_visit, total_spent, preferred_staff, notes

- **Vagaro** -- salon, spa, and fitness scheduling
  - **Appointments**: client, service, provider, date, time, room/station, price, tip, product_add_ons
  - **Classes**: class_name, instructor, date, time, capacity, enrolled, waitlist

- **Jobber** -- field service scheduling
  - **Jobs**: client, service_type, date, time_window, assigned_team, status, materials_needed
  - **Routes**: job_sequence, travel_time, location, optimized_route, estimated_arrival

## Calendar Systems

- **Google Calendar** -- general calendar management
  - **Events**: title, date, time, duration, location, attendees, recurrence, reminders, description
  - **Availability**: free/busy status, working_hours, out_of_office, calendar_sharing_permissions

- **Microsoft Outlook Calendar** -- business calendar
  - **Events**: subject, start/end, location, attendees, recurrence, categories, reminder
  - **Scheduling assistant**: attendee_availability, suggested_times, room_availability

## Reminder & Communication

- **Twilio / SimpleTexting** -- SMS reminders
  - **Messages**: recipient_phone, message_text, send_time, delivery_status, opt_out_status
  - **Templates**: reminder_template, confirmation_template, follow_up_template

- **Mailchimp / Constant Contact** -- email reminders
  - **Automations**: trigger_event, send_timing, email_content, open_rate, click_rate
