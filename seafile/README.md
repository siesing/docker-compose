# Seafile

Ensure that the Docker network "traefik-proxy" has been created beforehand.

## Once the installation is completed

#### Add settings to /opt/seafile/conf/seahub_settings.py

Change the specific domain values to reflect your environment. 

```shell
ALLOWED_HOSTS = ['.example.com']
CSRF_TRUSTED_ORIGINS = ["https://seafile.example.com"]
CSRF_COOKIE_SECURE = True
CSRF_COOKIE_SAMESITE = 'Strict'
DEBUG=True
```