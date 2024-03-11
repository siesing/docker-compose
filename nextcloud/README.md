# Nextcloud

Ensure that the Docker network "traefik-proxy" has been created beforehand.

## Once the installation is completed

### Activate Cron Job

Trigger background job using
```shell
docker exec -u www-data <nextcloud-container-name> php cron.php
```

Setup up Cron Job
```shell
crontab -e
```

Add the following after the last line
```shell
*/5 * * * * docker exec -u www-data <nextcloud-container-name> php cron.php
```

  
### Run OCC commands from terminal on Nextcloud

In the terminal of the host machine type the following commands.

#### Set Default Locale

```shell
docker exec -u www-data <nextcloud-container-name> php occ config:system:set default_locale --type string --value="sv_SE"
```

#### Set Default Phone Region

```shell
docker exec -u www-data <nextcloud-container-name> php occ config:system:set default_phone_region --type string --value="SE"
```

Find your country specific value here. [View values here](https://en.wikipedia.org/wiki/SO_3166-1_alpha-2#Officially_assigned_code_elements)

### Prettify URLs

Remove the index.php-part in all Nextcloud URLs.
```shell
docker exec -u www-data <nextcloud-container-name> php occ maintenance:update:htaccess
```