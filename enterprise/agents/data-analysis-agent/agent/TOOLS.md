Available integrations for data analysis, reporting, and business intelligence:

- Snowflake, BigQuery, or Redshift for executing read-only SQL queries against the data warehouse
- Tableau, Looker, or Power BI for reading existing dashboards, embedded metrics, and scheduled report outputs
- dbt for understanding data model definitions, lineage, and metric layer definitions
- Data catalog (DataHub, Alation) for discovering available datasets, column descriptions, and data ownership metadata
- Python/pandas in secure compute environment for ad-hoc statistical analysis and visualization generation

## Data Sources

Systems and platforms accessed for business reporting, trend analysis, ad-hoc queries, and metric governance.

### Data Warehouses & Lakes

- **Snowflake** -- cloud data warehouse
  - **Query result**: query_id, execution_time, rows_returned, bytes_scanned, warehouse_used, schema, table, columns_selected
  - **Table metadata**: database, schema, table_name, row_count, bytes, created, last_altered, columns, clustering_keys
- **Google BigQuery** -- serverless data warehouse
  - **Job**: job_id, project, dataset, table, query, state, creation_time, start_time, end_time, bytes_processed, slot_ms, referenced_tables
  - **Dataset**: dataset_id, project, location, creation_time, last_modified, tables_count, total_rows
- **Amazon Redshift** -- cloud data warehouse
  - **Query**: query_id, pid, user_name, database, queue, start_time, end_time, duration, queue_time, rows, bytes

### Business Intelligence

- **Tableau** -- visual analytics
  - **Workbook**: workbook_id, name, project, owner, created_at, updated_at, views, data_sources, dashboards, sheets
  - **View**: view_id, name, workbook_id, owner, created_at, total_views, last_viewed, embedded_data_source
- **Looker** -- BI and data platform
  - **Explore**: model, explore_name, label, fields, measures, dimensions, filters, joins
  - **Dashboard**: dashboard_id, title, folder, creator, created_at, last_viewed, tiles, scheduled_plans
- **Microsoft Power BI** -- enterprise BI
  - **Report**: report_id, name, dataset_id, workspace_id, created_datetime, modified_datetime, embed_url
  - **Dataset**: dataset_id, name, workspace_id, created_date, is_refreshable, configured_by, tables

### Data Modeling & Lineage

- **dbt** -- data transformation framework
  - **Model**: model_name, schema, database, materialization, tags, description, columns, depends_on, sources_used, last_run_status
  - **Metric**: metric_name, model, type, sql, timestamp, filters, dimensions, description
  - **Test**: test_name, model, column, test_type, status, failures, last_run

### Data Catalog & Governance

- **DataHub** -- metadata platform
  - **Dataset**: urn, platform, name, schema_fields, description, owners, tags, glossary_terms, domain, last_profiled
  - **Lineage edge**: source_urn, destination_urn, transformation_type, created_at, actor
- **Alation** -- data intelligence platform
  - **Article**: article_id, title, body, author, last_updated, tags, related_datasets
  - **Data quality**: table_id, check_name, status, failed_rows, checked_at, owner

### Operational Metrics Sources

- **Salesforce** -- CRM pipeline data
  - **Opportunity**: stage, amount, close_date, forecast_category, owner, account, created_date, win_rate_segment
- **Stripe** -- payments and revenue data
  - **Charge**: charge_id, amount, currency, status, created, customer_id, payment_method, refunded, dispute
  - **Invoice**: invoice_id, customer_id, amount_due, amount_paid, status, period_start, period_end, subscription_id
