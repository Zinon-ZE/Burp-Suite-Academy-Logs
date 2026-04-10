IDOR with Password Disclosure
Goal

Get administrator password and delete Carlos.

Exploit

Change request parameter:

/my-account?id=wiener → /my-account?id=administrator
Result

Admin password exposed in response (prefilled form field).

Final Step

Login as administrator → delete user carlos.

Cause

Broken access control + sensitive data exposed in account page.
