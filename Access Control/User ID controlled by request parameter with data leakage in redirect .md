IDOR via Data Leakage in Redirect
Goal

Get Carlos’s API key.

Exploit

Change request parameter:

/my-account?id=wiener → /my-account?id=carlos
Result

Server returned Carlos’s API key in redirect response body (302).

Cause

Sensitive data exposed in redirect response + missing authorization check.
