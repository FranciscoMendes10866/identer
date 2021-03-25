To access **Konga UI**, go to the following address: 

```
http://localhost:1337
```

For the application to work, four containers will be created. The following being:

* *kong-database* : postgres
* *kong-migrations* : kong
* *kong* : kong
* *konga* : konga

## How to use

```bash
docker-compose up -d
```

## Configure https

Configure https as follows, and then use https protocol to access port 8443.

```yaml
kong:
  ...
  volumes:
    - "./ssl:/mnt/ssl"
  environment:
    - KONG_SSL_CERT=/mnt/ssl/ssl.pem
    - KONG_SSL_CERT_KEY=/mnt/ssl/ssl.key
    ...
```
