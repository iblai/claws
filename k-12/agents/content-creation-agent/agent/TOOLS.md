Available integrations for K-12 content creation:

- Google Slides / Microsoft PowerPoint API -- generate slide decks with teacher-specified structure and content
- Google Docs / Word export -- produce formatted worksheets, graphic organizers, and study guides
- Google Drive / OneDrive -- save finished materials to the teacher's designated folder
- Canva for Education API (if enabled) -- generate visually styled classroom posters, anchor charts, and activity cards
- LMS content upload (Canvas, Schoology, Google Classroom) -- publish created materials directly to a course module or topic
- Standards reference (CCSS, NGSS, state databases) -- embed standard codes and language in finished materials
- Image library (public domain / CC0) -- source age-appropriate illustrations for worksheets and presentations

## Data Sources

Systems and platforms commonly accessed for K-12 content creation workflows.

### Content Storage and Delivery

- **Google Drive / Google Workspace for Education**
  - **Fields**: file_id, file_name, mime_type, parent_folder, owner, shared_with, last_modified, content_body
- **Microsoft OneDrive / SharePoint (M365 Education)**
  - **Fields**: document_id, name, folder_path, content, created_by, modified_date

### LMS Content Modules

- **Canvas**
  - **Fields**: module_name, page_title, page_body (HTML), file_attachments, external_urls, published (bool)
- **Schoology**
  - **Fields**: folder_name, page_content, file_links, media_attachments
- **Google Classroom**
  - **Fields**: topic_name, material_title, material_description, attachments (drive_file/link)

### Standards Reference

- **CCSS** -- standard_id, domain, cluster, grade, full_text, mathematical_practices, anchor_standards
- **NGSS** -- performance_expectation, disciplinary_core_idea, science_and_engineering_practice, crosscutting_concept
- **State standards** -- standard_code, subject, grade_band, description

### Curriculum Scope and Sequence

- **Adopted textbook series** (HMH, Savvas, McGraw-Hill, Amplify)
  - **Fields**: unit_name, chapter, lesson_number, lesson_title, vocabulary, key_concepts, standards_alignment
