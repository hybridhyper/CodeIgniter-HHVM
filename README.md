# CodeIgniter

This is my personal modified version of CodeIgniter for use with HipHop VM (HHVM) and removal of unecessary code to support earlier versions of PHP

## Requirements
- PHP 5.4+ or HHVM 2.0+
- Nginx (recommended)

## Sample Nginx Config
```
    location / {
        try_files $uri $uri/ /index.php;
    }

    proxy_redirect off;
    location ~ /index.php$ {
        proxy_set_header REQUEST_URI $request_uri;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host pocket.djc.me;
        proxy_pass http://localhost:8000;
    }
```
