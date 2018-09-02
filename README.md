# Command

```bash
sudo mkdir -p /srv/www                                 \
&& sudo chown -Rh $USER:$USER /srv/www                 \
&& cd /srv/www                                         \
&& git clone https://github.com/nshtg/docker-web proxy \
&& cd /srv/www/proxy                                   \
&& touch acme.json                                     \
&& chmod 0600 acme.json                                \
&& cp .env.example .env                                \
&& vim .env
```

If you want to use php:

```nginx
    location ~ \.php$ {
        try_files $uri =404;
        fastcgi_split_path_info ^(.+\.php)(/.+)$;
        fastcgi_pass php:9000;
        fastcgi_index index.php;
        include fastcgi_params;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        fastcgi_param PATH_INFO $fastcgi_path_info;
    }
```
