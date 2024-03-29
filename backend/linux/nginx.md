# NGINX Cheatsheet

## cheatsheet
https://github.com/SimulatedGREG/nginx-cheatsheet

## Laravel
```
server {
    listen 80;
    server_name example.com;
    root /example.com/public;

    add_header X-Frame-Options "SAMEORIGIN";
    add_header X-XSS-Protection "1; mode=block";
    add_header X-Content-Type-Options "nosniff";

    index index.html index.htm index.php;

    charset utf-8;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location = /favicon.ico { access_log off; log_not_found off; }
    location = /robots.txt  { access_log off; log_not_found off; }

    error_page 404 /index.php;

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.(?!well-known).* {
        deny all;
    }
}
```

### exedra
```
server {
    listen 80;
    server_name exedra.rosengate.com;
    return 301 https://exedra.rosengate.com$uri;
}

server {
    listen       80;
    server_name exedra.rosengate.com;
    root /var/www/html/exedra-web/public;

    location ~* \.(?:jpg|apk|jpeg|gif|png|ico|cur|gz|svg|svgz|mp4|ogg|ogv|webm|htc)$ {
      expires 1M;
      access_log off;
      add_header Cache-Control "public";
    }
    
    # CSS and Javascript
    location ~* \.(?:css|js)$ {
      expires 1y;
      access_log off;
      add_header Cache-Control "public";
    }

    location / {
        #rewrite ^([^.]*[^/])$ $1/ permanent;
    include fastcgi_params;
        #fastcgi_split_path_info ^(.+\.php)(/.+)$;
        fastcgi_pass unix:/var/run/php-fpm/php-fpm.sock;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME /var/www/html/exedra-web/public/index.php;
    }

    listen 443 ssl; # managed by Certbot
    ssl_certificate /etc/letsencrypt/live/exedra.rosengate.com/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/exedra.rosengate.com/privkey.pem; # managed by Certbot
    include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot
}
```