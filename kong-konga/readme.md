# kong and konga

Use the latest version of kong and konga, and do not need to compile, directly pull the official image to run.

Four containers:

* *kong-database* : postgres
* *kong-migrations* : kong
* *kong* : kong
* *konga* : konga


## Usage

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

To use the konga UI, visit the following URL:
```
http://localhost:1337
```
