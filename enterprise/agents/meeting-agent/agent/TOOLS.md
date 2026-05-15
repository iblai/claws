Available integrations for meeting recaps, action tracking, and follow-up communications:

- Google Calendar or Microsoft Outlook for reading meeting metadata, attendee lists, and scheduled events
- Zoom, Google Meet, or Microsoft Teams for retrieving recording links and auto-generated transcripts
- Otter.ai, Fireflies.ai, or Gong for fetching high-quality meeting transcriptions and speaker diarization
- Slack or Microsoft Teams for posting meeting summaries and sending follow-up messages to attendees
- Jira, Asana, or Linear for creating action item tasks with owners and due dates extracted from meeting notes

## Data Sources

Systems and platforms accessed for meeting transcripts, calendar context, action item tracking, and follow-up distribution.

### Calendar & Conferencing

- **Google Calendar** -- meeting scheduling and calendar management
  - **Event**: event_id, summary, description, start_datetime, end_datetime, organizer, attendees, location, conference_link, status, recurrence
  - **Attendee**: email, display_name, response_status, optional
- **Microsoft Outlook / Exchange** -- enterprise calendaring
  - **Calendar event**: event_id, subject, body, start, end, organizer, attendees, location, online_meeting_url, is_recurring, recurrence_pattern
  - **Meeting room**: room_id, display_name, capacity, location, equipment, availability_status

### Video Conferencing & Recording

- **Zoom** -- video conferencing platform
  - **Meeting**: meeting_id, topic, start_time, duration, host, participants, recording_url, transcript_url, cloud_recording_expiry
  - **Participant**: participant_id, name, email, join_time, leave_time, duration, attentiveness_score
- **Microsoft Teams** -- enterprise meetings
  - **Meeting**: meeting_id, subject, organizer, start_time, end_time, participants, recording_url, transcript, chat_messages

### Transcription Services

- **Otter.ai** -- AI meeting transcription
  - **Transcript**: transcript_id, title, duration, date, speakers, word_count, summary, action_items, outline, highlights
  - **Speaker**: speaker_id, name, word_count, speaking_time_seconds, first_appearance
- **Fireflies.ai** -- meeting intelligence
  - **Meeting note**: note_id, title, date, duration, attendees, transcript, summary, action_items, questions_asked, topics_discussed, sentiment
  - **Action item**: item_id, meeting_id, text, owner, due_date, status

### Project & Task Management

- **Asana** -- work management platform
  - **Task**: task_id, name, description, assignee, due_date, project, section, tags, status, created_at, completed_at, parent_task
  - **Project**: project_id, name, owner, team, due_date, status, color, notes, created_at
- **Jira** -- project tracking
  - **Issue**: issue_id, key, summary, description, type, status, assignee, due_date, priority, labels, sprint, story_points

### Communication Platforms

- **Slack** -- team messaging
  - **Message**: message_id, channel, user, text, timestamp, thread_ts, reactions, files
  - **Channel**: channel_id, name, is_private, topic, purpose, members
