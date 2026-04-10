IDOR via Transcript File Access
Goal

Find Carlos password and login.

Exploit

Server stores chat logs as static files:

/download-transcript/1.txt → /2.txt → /3.txt

Changed response path:

/download-transcript/2.txt → /download-transcript/1.txt
Result

Accessed other users’ chat transcript and extracted Carlos password.

Cause

Insecure Direct Object Reference (predictable file paths)
