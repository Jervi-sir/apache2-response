this meant for, if the domain name is pointing to the backend project, but the project is not running, 

by default Apache2 page will be shown, but I want it to be funny so 

to access this index.html go to 
`cd /var/www/html`

---

if its Nginx the you access the folder `/user/share/nginx/html/index.html`

and for every domain nginx rules add the following, under location / {} rules

```
    # Custom error page
    error_page 502 /index.html;
    location = /index.html {
        internal;  # Prevent direct access to this page
    }
```
