# Traefik

This is my boilerplate for a Traefik setup. This setup doesn't rely on certificates from Let's Encrypt, but on user-defined ones from a provider. I personally use [Cloudflare](https://cloudflare.com) for this, but any provider will work.

The setup relies mostly on a dynamic configuration file for configuration instead of cluttering the individual docker-compose files with label configurations.

The dynamic configuration file contains examples of `routers`, `services`, `middlewares` and `tls`. Feel free to use what you need and configure it the way that fits your needs.


## Prerequisites

Ensure that the Docker network `traefik-proxy` has been created beforehand.

Make sure to create the following directory on the host system in advance for the configuration files, both static and dynamic.
```shell
/etc/traefik/
```

Make sure to create the following directory on the host system in advance for the certificate files.
```shell
/etc/certificates/
```