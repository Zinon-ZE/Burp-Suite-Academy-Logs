1. Goal
Access /admin by becoming role 2 user
2. Initial observation
/admin restricted by roleid=2
3. Vulnerable endpoint
POST /my-account/change-email
4. Exploit
Inject extra parameter:
{
  "email": "test@test.com",
  "roleid": 2
}
5. Result
Role upgraded → admin panel accessible → delete carlos
6. Root cause
Server does not validate allowed fields (mass assignment)
