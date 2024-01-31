# CDN with NGINX

This is a very simple web server for delivering files and two custom pages. The files should be stored beneath the files folder

## Domain

To customize the domain, have a look in the nginx-conf folder inside the default.conf, espacially the line with server_name:

```bash
server {
    listen       80;
    server_name  cdn.ansible.localhost;

    location / {
        root   /usr/share/nginx/html;
        index  index.html index.htm;
    }

    error_page   404 403 500            /404.html;
    location = /404.html {
        root   /usr/share/nginx/html;
    }
}
```

## Docker

To start the server use docker and docker-compose:

```bash
docker-compose up -d
```
