# Data Sources

Systems and platforms commonly accessed for K-12 administration and operations.

## Student Information Systems (SIS)

- **PowerSchool SIS** -- comprehensive K-12 student management
  - **Enrollment**: student_count, enrollment_by_grade, enrollment_by_school, entry/withdrawal_codes, demographics
  - **Attendance**: daily_attendance_rate, chronic_absenteeism_rate, period_attendance, absence_reasons
  - **Demographics**: ethnicity, gender, ELL_status, free/reduced_lunch, special_education, 504, homeless/foster
  - **Scheduling**: master_schedule, section_enrollment, teacher_assignments, room_utilization

- **Infinite Campus** -- district-wide SIS
  - **Reporting**: state_reporting_extracts, CRDC_data, enrollment_snapshots, ADA/ADM_counts
  - **Operations**: transportation_routing, food_service_eligibility, health_records, emergency_contacts

- **Skyward / Aeries / Tyler SIS** -- regional K-12 SIS platforms
  - **Similar data**: enrollment, attendance, grades, demographics, scheduling, state_reporting

## Finance & HR

- **Munis (Tyler Technologies)** -- K-12 financial management
  - **Budget**: fund_codes, account_codes, budgeted_amount, encumbered, expended, remaining_balance
  - **Payroll**: employee_id, position, salary, benefits_cost, FTE, pay_period, deductions

- **Frontline Central** -- K-12 HR and recruiting
  - **Positions**: job_title, location, FTE, salary_range, vacancy_status, posting_date
  - **Employees**: employee_id, position, hire_date, certification_status, evaluation_scores, absences

- **Frontline Absence Management (Aesop)** -- substitute teacher management
  - **Absences**: employee, absence_date, reason_code, substitute_assigned, fill_rate
  - **Reports**: absence_trends, fill_rates_by_school, substitute_utilization, cost_per_absence

## State & Federal Reporting

- **CRDC (Civil Rights Data Collection)** -- federal civil rights reporting
  - **Data**: enrollment_by_subgroup, discipline_by_subgroup, AP/IB_enrollment, restraint/seclusion, chronic_absence

- **State longitudinal data systems** -- state accountability reporting
  - **Metrics**: graduation_rate, dropout_rate, assessment_proficiency, attendance_rate, college_readiness

- **Title I / Title III / IDEA** -- federal program reporting
  - **Data**: eligible_students, funds_allocated, funds_expended, program_outcomes, supplement_not_supplant

## Facilities & Operations

- **SchoolDude (Brightly)** -- facilities and maintenance management
  - **Work orders**: request_type, location, priority, status, assigned_to, completion_date, cost
  - **Preventive maintenance**: equipment, schedule, last_service, next_due, vendor

- **Nutrislice / Titan (school nutrition)** -- food service management
  - **Meals**: meals_served, free/reduced/paid_counts, menu_items, allergen_info, USDA_compliance
  - **Eligibility**: student_eligibility_status, application_data, direct_certification_matches

- **Transfinder / Versatrans** -- transportation management
  - **Routes**: route_number, stops, students_assigned, estimated_time, bus_capacity
  - **Reports**: ridership, on-time_performance, route_efficiency, special_needs_transportation
