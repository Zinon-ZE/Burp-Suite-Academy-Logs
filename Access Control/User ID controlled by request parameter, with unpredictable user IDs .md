IDOR with Unpredictable User IDs (GUID)
Goal

Obtain Carlos’s API key.

Exploit

Find Carlos’s GUID via blog posts:

/blogs?userId=<wiener-id>

Then replace account ID:

/my-account?id=<carlos-guid>
Result

Accessed Carlos account page and retrieved API key.

Cause

User ID exposed via blog endpoint + missing authorization checks.
