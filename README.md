# Next.js setup with Docker
## SSL from Letsencrypt using Certbot and Nginx

To test if working (simulate):
```sh
docker-compose run --rm  certbot certonly --webroot --webroot-path /var/www/certbot/ --dry-run -d example.org
```
To update certificate for real:
```sh
docker-compose run --rm  certbot certonly --webroot --webroot-path /var/www/certbot/ -d example.org
```
Renew certificate
```sh
docker-compose run --rm certbot renew
```
Renew certificate (quiet)
```sh
docker-compose run --rm certbot renew --quiet
```
