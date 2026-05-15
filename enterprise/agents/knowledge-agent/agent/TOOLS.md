Available integrations for enterprise knowledge search:

- Confluence for structured internal wikis, runbooks, project documentation, and team spaces
- SharePoint / OneDrive for corporate documents, policy PDFs, and presentation libraries
- Elasticsearch or OpenSearch for full-text semantic search across all indexed repositories
- Notion for team knowledge bases and collaborative documentation where enabled
- Google Drive for shared document libraries when the organization uses Google Workspace

## Data Sources

Systems and platforms accessed for enterprise knowledge search and institutional documentation retrieval.

### Wiki & Documentation Platforms

- **Confluence** -- Atlassian team wiki and documentation hub
  - **Page**: page_id, space_key, title, body, author, created_date, last_modified, version, labels, parent_page_id
  - **Space**: space_key, space_name, type, permissions, homepage_id, description
- **Notion** -- collaborative knowledge base
  - **Page**: page_id, title, content_blocks, created_by, last_edited_by, last_edited_time, parent_id, properties
  - **Database row**: row_id, database_id, properties, created_time, last_edited_time

### Document Management

- **SharePoint** -- Microsoft document management and intranet
  - **Document**: item_id, site_id, library, file_name, file_type, size, author, modified_date, version, permissions
  - **Site**: site_id, site_url, title, owner, storage_used, last_activity_date
- **Google Drive** -- Google Workspace document storage
  - **File**: file_id, name, mime_type, owner, shared_with, created_time, modified_time, size, web_view_link, labels

### Search Infrastructure

- **Elasticsearch** -- full-text and semantic search engine
  - **Index**: index_name, document_count, size_bytes, field_mappings, refresh_interval, analyzer
  - **Search result**: doc_id, score, source, highlight, explanation, index, shard
- **Coveo** -- enterprise AI-powered search
  - **Result**: result_id, title, uri, excerpt, source, rank, query_terms, click_through_rate, last_indexed_date

### Policy & Compliance Content

- **PolicyTech** -- policy management system
  - **Policy**: policy_id, title, version, status, owner, effective_date, review_date, category, applicability, acknowledgment_required
  - **Acknowledgment**: ack_id, policy_id, employee_id, acknowledged_date, method
- **Navex Global** -- ethics and compliance content library
  - **Document**: doc_id, title, category, jurisdiction, last_updated, related_regulations, owner, review_cycle
