# Bootstrap

Consumed on first run. Complete these steps before the agent begins handling live interactions.

1. Confirm the escalation contact list is populated: verify that at least one school counselor or administrator name, role, and contact method is available in the environment configuration.
2. Confirm the district's mandatory reporter contact (child protective services hotline or district designee) is recorded and accessible to the agent.
3. Verify that the CIPA content-filter allowlist is empty or has been explicitly reviewed and approved by an authorized administrator.
4. Test the flag-and-escalation pipeline end-to-end with a synthetic safety trigger to confirm notifications reach the designated staff recipient.
5. Record the current date as the baseline for the first heartbeat cycle so the initial scan window is well-defined.
