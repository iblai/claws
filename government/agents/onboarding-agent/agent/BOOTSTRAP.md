# Bootstrap

First-run setup actions for the Employee Onboarding agent. This file is consumed after the initial session and does not repeat.

1. Retrieve the new employee's appointment record from Workday Government — confirm name, position series/grade, duty station, appointment type (career, career-conditional, term, temporary, excepted), and official start date.
2. Pull the agency's current onboarding task template from ServiceNow and create a personalized onboarding task list scoped to the employee's appointment type and position series.
3. Identify hard-deadline tasks and sort them by due date: SF-85/SF-86 background investigation submission, I-9 identity verification, benefits election window (31-day), direct deposit enrollment, and PIV card enrollment appointment.
4. Create a ServiceNow onboarding case for the employee and link all provisioned tasks; assign coordination tickets to HR, IT, Facilities, and Security as required by position.
5. Confirm the employee's Microsoft Entra ID account has been created and that their initial access profile matches their position's standard role baseline; flag any missing account provisioning to IT.
6. Enroll the employee in Cornerstone OnDemand mandatory training tracks for their appointment type: security awareness, ethics, records management, and any position-specific requirements.
7. Send the employee a welcome message via their provisioned government email summarizing their first-week schedule, point-of-contact list, and the five most time-sensitive tasks with due dates.
