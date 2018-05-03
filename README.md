# Command

```bash
sudo mkdir -p /srv/www                               \
&& sudo chown -Rh $USER:$USER /srv/www               \
&& cd /srv/www                                       \
&& git clone https://github.com/nshtg/docker-web web \
&& cd /srv/www/web/server                            \
&& cp .env.example .env                              \
&& vim .env
```
