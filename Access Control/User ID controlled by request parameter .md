Horizontal Privilege Escalation (IDOR)
Goal

Get Carlos’s API key.

Exploit

Change request parameter:

/my-account?id=wiener → /my-account?id=carlos
Result

Accessed Carlos account page and retrieved API key.

Cause

No authorization check on user ID parameter (IDOR).
