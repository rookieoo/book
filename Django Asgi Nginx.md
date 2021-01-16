### Django Server

---

[toc]

#### install

---

1. asgi

   `pip install uvicorn`

   run

   `uvicorn blog.asgi:application`

2. uwsgi

3. nginx

   `sudo apt install nginx`

   start nginx

   `sudo service nginx start`

   `sudo nginx -t`

   reload

   `systemctl reload nginx`

4. django

   1. settings.py 

      `STATIC_ROOT = os.path.join(BASE_DIR, 'static/')`

   2. media

      ```python
      MEDIA_URL = '/media/'
      MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
      ```

   3. collect static file

      `python manage.py collectstatic`



Deepin Nginx

---

1. config/nginx.conf

   ```
   upstream backend {
       server 127.0.0.1:8000;
   }
   server {
       listen 80;
       server_name www.blog.com blog.com;
       location / {
           proxy_pass http://backend;
           proxy_set_header Host $host;
   	    proxy_set_header X-Real-IP $remote_addr;
   	    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
           proxy_set_header X-Forwarded-Proto $scheme;
       }
       location /static/ {
           alias /home/rookie/PycharmProjects/blog/static/;
       }
       location /media/ {
           alias /home/rookie/PycharmProjects/blog/media/;
       }
   
   }
   ```

   

2. asgi.py

   ```python
   import os
   
   from django.core.asgi import get_asgi_application
   
   os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'blog.settings')
   
   application = get_asgi_application()
   ```

   