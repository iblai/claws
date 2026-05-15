Available integrations for sales enablement and deal strategy:

- Salesforce CRM for opportunity data, account history, contact profiles, activity timeline, and pipeline stage
- HubSpot CRM as an alternative for deal management, email tracking, and sequence enrollment
- Gong for call recording transcripts, deal risk signals, and rep coaching insights
- Highspot or Seismic for approved sales content, battle cards, and case study libraries
- ZoomInfo or Apollo for prospect firmographic data, contact discovery, and intent signals

## Data Sources

Systems and platforms accessed for sales enablement, prospect intelligence, and deal execution support.

### CRM Platforms

- **Salesforce** -- enterprise CRM and revenue platform
  - **Opportunity**: opportunity_id, name, account_id, stage, amount, close_date, probability, forecast_category, owner_id, created_date, last_activity_date, lead_source
  - **Account**: account_id, name, industry, annual_revenue, employee_count, billing_address, website, owner_id, account_type, parent_account_id
  - **Contact**: contact_id, account_id, first_name, last_name, title, email, phone, linkedin_url, lead_source, last_contacted
  - **Activity**: activity_id, who_id, what_id, type, subject, date, description, outcome, owner_id
- **HubSpot CRM** -- inbound-focused CRM
  - **Deal**: deal_id, deal_name, pipeline, deal_stage, amount, close_date, associated_contacts, associated_company, owner, create_date, last_modified
  - **Company**: company_id, name, domain, industry, num_employees, annual_revenue, lifecycle_stage, owner, city, country

### Sales Intelligence

- **ZoomInfo** -- B2B contact and company intelligence
  - **Person**: person_id, first_name, last_name, job_title, department, seniority, email, phone, linkedin_url, company_id, city, state
  - **Company**: company_id, name, website, industry, sub_industry, revenue_range, employee_range, founded_year, technologies_used, sic_code
- **Apollo.io** -- sales intelligence and engagement
  - **Prospect**: prospect_id, name, title, email, verified_email, phone, company, industry, employees, technologies, intent_signals
  - **Sequence**: sequence_id, name, steps, enrolled_count, reply_rate, open_rate, bounce_rate

### Conversation Intelligence

- **Gong** -- revenue intelligence from call recordings
  - **Call**: call_id, participants, date, duration, topics, talk_ratio, next_steps, risks_mentioned, competitor_mentions, transcript_url
  - **Deal health**: deal_id, sentiment_trend, engagement_score, risk_factors, activity_recency, champion_engagement
- **Chorus (ZoomInfo)** -- conversation analytics
  - **Recording**: recording_id, deal_id, reps, duration, key_moments, objections_raised, feature_requests, competitor_mentions, coaching_flags

### Sales Content Management

- **Highspot** -- sales content platform
  - **Content item**: item_id, title, type, tags, stage_relevance, industry_relevance, view_count, share_count, win_rate_correlation, last_updated
  - **Pitch**: pitch_id, name, items_included, recipient, sent_date, view_duration, next_step_scheduled
- **Seismic** -- enterprise sales enablement
  - **Asset**: asset_id, name, content_type, persona_tags, stage_tags, version, approved_date, expiration_date, usage_analytics

### Market Intelligence

- **Bombora** -- B2B intent data
  - **Intent signal**: company_id, topic, surge_score, week, composite_score, topics_surging
- **LinkedIn Sales Navigator** -- professional network intelligence
  - **Lead**: lead_id, full_name, current_position, company, connections, job_changes_last_90_days, shared_connections, saved_lists
