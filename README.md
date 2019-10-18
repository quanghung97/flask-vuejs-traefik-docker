# Running a Flask application backend + frontend over HTTPS with traefik and Let's Encrypt

may be to need run certificate in folder `certs`

```
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout ssl.key -out ssl.crt
```

modified: traefik/traefik.toml and .env in folder `frontend`
change to your domain
```
domain = "service.test"
```
make sure that `/etc/hosts` add follow domain like `127.0.0.1 service.test`

To run docker production:

```
docker-compose up -d
```

traefik UI: http://service.test:8080

frontend: https://service.test
backend: https://service.test/api/

