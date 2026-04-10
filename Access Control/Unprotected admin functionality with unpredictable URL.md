# Lab: Unprotected Admin Panel (Unpredictable Location)

## 1. Lab Description

 This lab has an unprotected admin panel. It's located at an unpredictable location, but the location is disclosed somewhere in the application.

Solve the lab by accessing the admin panel, and using it to delete the user 'carlos'. 

---

## 2. Reconnaissance

I first inspected the page source to identify any references to administrative functionality or hidden endpoints.

No direct references to an admin panel were found in the HTML source.

---

## 3. Discovery via Client-Side Code

I then opened the browser developer tools and examined the JavaScript files in the Debugger tab.

Inside the main JavaScript file, I found the following code:

```javascript
var isAdmin = false;
if (isAdmin) {
   var topLinksTag = document.getElementsByClassName("top-links")[0];
   var adminPanelTag = document.createElement('a');
   adminPanelTag.setAttribute('href', '/admin-k1urr1');
   adminPanelTag.innerText = 'Admin panel';
   topLinksTag.append(adminPanelTag);

   var pTag = document.createElement('p');
   pTag.innerText = '|';
   topLinksTag.appendChild(pTag);
}
```

This JavaScript reveals a hidden admin panel path:

```
/admin-k1urr1
```

---

## 4. Exploitation

I navigated directly to the discovered endpoint:

```
/admin-k1urr1
```

This granted access to the admin panel interface.

Inside the panel, I used the user management functionality to delete the target user:

```
carlos
```

---

## 5. Result

The lab was successfully completed after deleting the user `carlos`.

---
