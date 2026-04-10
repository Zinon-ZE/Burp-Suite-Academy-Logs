# Lab: Unprotected Admin Panel

## 1. Lab Description

 This lab has an unprotected admin panel.

Solve the lab by deleting the user 'carlos'. 
---

## 2. Reconnaissance

Initial attempt was made to access the default admin endpoint:

```
/admin /administrator
```

This endpoint was not accessible and returned a not found response, indicating the admin panel was not exposed directly.

Next, I checked the robots.txt file for hidden or disallowed paths:

```
/robots.txt
```

---

## 3. Discovery

The robots.txt file contained the following entry:

```
User-agent: *
Disallow: /administrator-panel
```

This revealed a hidden administrative interface that is excluded from search engine indexing.

---

## 4. Exploitation

I navigated directly to the discovered endpoint:

```
/administrator-panel
```

The admin panel loaded successfully.

Inside the panel, I accessed the user management functionality and deleted the target user:

```
carlos
```

---

## 5. Result

The lab was successfully completed after deleting the user `carlos`.

---

## 6. Key Learning

* Sensitive endpoints may be exposed via `robots.txt`
* Security through obscurity is not a valid protection mechanism
* Hidden directories can often be discovered through basic enumeration
