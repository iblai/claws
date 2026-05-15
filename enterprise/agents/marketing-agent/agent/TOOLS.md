Available integrations for marketing content, campaigns, and performance tracking:

- Marketo, HubSpot, or Pardot for campaign management, email sequences, lead scoring, and audience segmentation
- Google Analytics 4 for web traffic analysis, conversion funnel tracking, and audience insights
- SEMrush or Ahrefs for keyword research, SERP tracking, backlink analysis, and content gap identification
- CMS platform (WordPress, Contentful, or Drupal) for publishing blog posts, landing pages, and resource content
- Salesforce CRM for aligning campaign attribution data with pipeline and closed-won revenue

## Data Sources

Systems and platforms accessed for marketing campaign execution, content production, and performance measurement.

### Marketing Automation

- **Marketo Engage** -- enterprise marketing automation
  - **Campaign**: campaign_id, name, program_type, channel, start_date, end_date, status, budget, actual_spend, leads_generated, pipeline_influenced
  - **Email asset**: asset_id, name, subject, from_name, from_email, template, open_rate, click_rate, unsubscribe_rate, send_volume
  - **Lead**: lead_id, email, first_name, last_name, company, title, lead_source, score, lifecycle_stage, acquisition_date
- **HubSpot Marketing Hub** -- inbound marketing platform
  - **Campaign**: campaign_id, name, start_date, budget, sessions, contacts, revenue_influenced, roi
  - **Workflow**: workflow_id, name, type, enrollment_criteria, steps, enrolled_count, completion_rate, active

### Web Analytics

- **Google Analytics 4** -- web and app analytics
  - **Session**: session_id, user_id, timestamp, source, medium, campaign, landing_page, pages_viewed, session_duration, conversion_events
  - **Conversion event**: event_name, event_date, user_id, session_id, value, currency, item_list
- **Adobe Analytics** -- enterprise digital analytics
  - **Hit**: hit_id, visit_id, visitor_id, timestamp, page_name, site_section, channel, campaign, revenue, orders, custom_events

### SEO & Content Intelligence

- **SEMrush** -- SEO and competitive intelligence
  - **Keyword**: keyword, volume, difficulty, cpc, serp_features, position, url, traffic_share, trend
  - **Backlink**: source_url, target_url, anchor_text, authority_score, follow_type, first_seen, last_seen
- **Ahrefs** -- SEO toolset
  - **Organic keyword**: keyword, clicks, impressions, ctr, position, url, volume, difficulty

### Content Management

- **Contentful** -- headless CMS
  - **Entry**: entry_id, content_type, title, slug, author, status, published_at, updated_at, tags, seo_title, seo_description
  - **Asset**: asset_id, title, file_name, content_type, file_size, url, created_at
- **WordPress** -- web content management
  - **Post**: post_id, title, slug, content, author, status, published_date, categories, tags, featured_image, seo_score

### Social Media Management

- **Sprout Social** -- social media management
  - **Post**: post_id, network, profile_id, message, media, sent_time, impressions, engagements, link_clicks, reach
  - **Profile analytics**: profile_id, network, followers, following, posts_sent, avg_engagement_rate, period
- **Hootsuite** -- social media scheduling
  - **Scheduled message**: message_id, network, profile, content, scheduled_for, status, labels, campaign
