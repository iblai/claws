Available integrations for engineering code review, documentation, and project support:

- GitHub, GitLab, or Bitbucket for pull request context, diff review, branch history, and commit metadata (read-only)
- Jira or Linear for linking engineering tasks, sprint context, and acceptance criteria to code review feedback
- Confluence or Notion for reading and drafting technical documentation, ADRs, and runbooks
- CI/CD pipeline status (GitHub Actions, Jenkins, CircleCI) for build results, test coverage reports, and deployment history
- Snyk or SonarQube for security vulnerability scan results and code quality metrics tied to specific PRs

## Data Sources

Systems and platforms accessed for engineering code review, project onboarding, documentation, and CI/CD insights.

### Source Control

- **GitHub** -- Git hosting and collaboration
  - **Pull request**: pr_id, number, title, body, state, author, base_branch, head_branch, created_at, merged_at, reviewers, labels, files_changed, additions, deletions, review_comments
  - **Commit**: sha, message, author, timestamp, files_changed, additions, deletions, parent_shas
  - **Repository**: repo_id, name, owner, default_branch, language, stars, forks, open_issues, last_push, topics
- **GitLab** -- DevOps platform
  - **Merge request**: mr_id, title, description, state, author, source_branch, target_branch, created_at, merged_at, assignee, reviewer, labels, approval_status
  - **Pipeline**: pipeline_id, ref, status, created_at, finished_at, duration, stages, coverage

### Issue & Project Tracking

- **Jira** -- agile project management
  - **Issue**: issue_id, key, summary, description, type, status, priority, assignee, reporter, sprint, story_points, labels, components, created, updated, resolved
  - **Sprint**: sprint_id, name, goal, state, start_date, end_date, velocity, completed_points, remaining_points
- **Linear** -- modern engineering issue tracker
  - **Issue**: issue_id, identifier, title, description, state, priority, assignee, team, cycle, estimate, labels, created_at, completed_at
  - **Cycle**: cycle_id, name, number, team, start_date, end_date, completed_issues, canceled_issues, progress

### CI/CD & Quality

- **GitHub Actions** -- workflow automation
  - **Workflow run**: run_id, workflow_name, event, status, conclusion, branch, commit_sha, started_at, completed_at, jobs_summary
  - **Job**: job_id, name, status, conclusion, started_at, completed_at, steps
- **SonarQube** -- code quality and security analysis
  - **Project analysis**: analysis_id, project_key, date, quality_gate_status, bugs, vulnerabilities, code_smells, coverage, duplications, ncloc
  - **Issue**: issue_key, rule, severity, type, component, line, message, status, assignee, creation_date, debt

### Documentation

- **Confluence** -- team documentation
  - **Page**: page_id, space_key, title, body, author, created_date, last_modified, version, labels, parent_id
- **Notion** -- engineering wiki
  - **Page**: page_id, title, content, created_by, last_edited_by, last_edited_time, parent_id, archived

### Security Scanning

- **Snyk** -- developer security platform
  - **Vulnerability**: vuln_id, package, severity, cvss_score, cve_ids, affected_versions, fixed_in, language, exploit_maturity, introduced_through
  - **Project snapshot**: snapshot_id, project_name, critical_issues, high_issues, medium_issues, low_issues, tested_at
