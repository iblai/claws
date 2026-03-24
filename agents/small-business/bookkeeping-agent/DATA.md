# Data Sources

Systems and platforms commonly accessed for small business bookkeeping.

## Accounting Software

- **QuickBooks Online** -- most popular small business accounting
  - **Chart of accounts**: account_name, type (asset/liability/equity/income/expense), balance, sub_accounts
  - **Transactions**: date, type (invoice/expense/payment/transfer), amount, account, category, vendor/customer, memo
  - **Invoices**: invoice_number, customer, line_items, amount, date_sent, due_date, status (open/paid/overdue), payment_date
  - **Expenses**: date, vendor, amount, category, payment_method, receipt_image, billable_status
  - **Reports**: profit_and_loss, balance_sheet, cash_flow, AR_aging, AP_aging, tax_summary
  - **Bank feeds**: bank_name, transaction_date, amount, description, matched_status, rule_applied

- **Xero** -- cloud accounting
  - **Transactions**: date, type, amount, account_code, tax_rate, tracking_categories, reconciled_status
  - **Invoices**: contact, invoice_number, line_items, subtotal, tax, total, status, payments_applied
  - **Bank reconciliation**: statement_balance, matched_transactions, unmatched_items, bank_rules
  - **Reports**: profit_and_loss, balance_sheet, budget_vs_actual, GST/VAT_return, 1099_summary

- **FreshBooks** -- invoicing-focused accounting
  - **Invoices**: client, line_items, amount, status, payment_date, late_fees, recurring_profile
  - **Expenses**: category, vendor, amount, tax, receipt, billable_to_client, reimbursable
  - **Time tracking**: project, task, hours, rate, billable_status, invoice_association

- **Wave** -- free accounting for small businesses
  - **Transactions**: account, date, description, amount, category, receipt, notes
  - **Invoices**: customer, items, amount, status, payment_method, payment_date
  - **Reports**: income_by_customer, expense_by_vendor, sales_tax, account_balances

## Payment Processing

- **Square** -- POS and payment processing
  - **Transactions**: payment_id, amount, tip, tax, discount, payment_method (card/cash/digital), timestamp, location
  - **Items**: item_name, category, quantity, price, variant, modifier
  - **Deposits**: deposit_date, gross_amount, fees, net_amount, transactions_included

- **Stripe** -- online payment processing
  - **Charges**: amount, currency, customer, description, status, fee, net, created_date
  - **Subscriptions**: customer, plan, amount, interval, status, current_period, trial_end
  - **Payouts**: amount, arrival_date, status, transactions_included

- **PayPal** -- payment platform
  - **Transactions**: type, amount, fee, net, currency, counterparty, date, status, invoice_id

## Payroll

- **Gusto** -- small business payroll and HR
  - **Payroll**: employee, gross_pay, deductions, taxes (federal/state/local), net_pay, pay_date, pay_period
  - **Tax filings**: form_type (941/940/W-2/1099), filing_date, amounts, status
  - **Benefits**: employee, plan_type, employer_contribution, employee_contribution

- **ADP Run** -- small business payroll
  - **Payroll data**: earnings, deductions, employer_taxes, check_date, department
  - **Reports**: payroll_register, tax_liability, labor_distribution, year_end

## Banking

- **Bank feeds (Chase, Bank of America, Wells Fargo, etc.)** -- transaction data
  - **Transactions**: date, description, amount, type (debit/credit), running_balance, category_suggestion
  - **Statements**: statement_period, beginning_balance, ending_balance, total_debits, total_credits
