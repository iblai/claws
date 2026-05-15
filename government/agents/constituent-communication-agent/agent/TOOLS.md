Available integrations for government constituent communications:

- **GovDelivery / Granicus** — draft, schedule, and send email/SMS subscriber notifications; manage subscriber lists and topic subscriptions; retrieve delivery analytics (sends, opens, click-through rates, bounces, unsubscribes)
- **Agency CMS (Drupal / Sitefinity / Adobe Experience Manager)** — draft, update, and schedule web page content and service announcements; manage content approval workflows; track content version history
- **Social media management (Hootsuite for Government / Sprout Social)** — schedule posts across Twitter/X, Facebook, LinkedIn, and Nextdoor; manage reply queues; retrieve engagement metrics; enforce content review workflows
- **IPAWS / Wireless Emergency Alerts** — compose and submit emergency alert messages through FEMA IPAWS-OPEN for Wireless Emergency Alerts (WEA), Emergency Alert System (EAS), and National Public Warning System (NPWS) — requires authorized alert originator credentials and supervisor approval
- **Press release management** — draft and route press releases through the communications director approval workflow; publish to agency newsroom and distribute to media contacts
- **Accessibility checker (Microsoft Accessibility Checker / axe)** — scan draft content for Section 508 compliance issues (missing alt text, insufficient color contrast, improper heading structure, inaccessible table structure)
- **Translation services API** — request certified translations of public notices for required language-access audiences per EO 13166

## Data Sources

Systems and platforms for government public communications and outreach.

### Email & Subscriber Notifications

- **GovDelivery / Granicus** — bulletins (bulletin ID, subject, body, send date, sender, recipient count, topic), delivery stats (sent count, open rate, click-through rate, bounce rate, unsubscribe count, spam report count), subscriber lists (topic name, subscriber count, list growth rate, engagement score), topics (topic ID, name, category, subscribe page URL, subscriber count)

### Web Content Management

- **Agency CMS** — pages (page ID, title, URL slug, content, status: draft/pending review/published/archived, author, last modified, publish date, expiration date, content owner, template, SEO metadata), content versions (version number, changed by, change date, change summary), approval workflow (workflow state, assignee, approval date, reviewer comments)

### Social Media

- **Social media management platform** — posts (post ID, channel, content, media attachments, scheduled time, publish status, author, approval status), engagement metrics (impressions, reach, likes, shares, comments, click-through, follower change), reply queue (incoming messages, sentiment classification, assigned responder, response drafted, response sent)

### Emergency Alerting

- **IPAWS-OPEN** — alert records (alert ID, event type, severity, urgency, certainty, headline, description, instruction, area affected: SAME codes/polygons, expiration time, originator, COGID, status: draft/pending/sent/expired/cancelled), alert history (sent alerts, acknowledgments, public reach estimate)

### Content Archive & Records

- **Communications records log** — published items (item ID, title, channel, publication date, author, approval chain, content version, distribution list, retention schedule citation, legal hold flag)
