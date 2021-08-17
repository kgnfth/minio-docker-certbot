## minio-docker-letsencrypt-deploy
Standalone MinIO deployed via Docker Compose with autorenew ssl certificate using letsencrypt.

## Prerequisites

- [docker](https://docs.docker.com/get-docker/)
- [docker-compose](https://docs.docker.com/compose/install/)

## Quick Start

1. Create .env

```
cp .env.example .env
```

2. change the environment variables

```
- MINIO_ROOT_USER: MinIO ACCESS_KEY
- MINIO_ROOT_PASSWORD: MinIO SECRET_KEY
- MINIO_REGION_NAME: name of the location of the server
- FQDN: a space separated list of domains for which you want to generate certificates.
- CERTBOT_EMAIL: where you will receive updates from letsencrypt.
```

3. Start MinIO server

```
docker-compose up -d
```

4. MinIO server' containers health status

```
watch -n 3 "docker ps -a"
```

5. Single instance of MinIO is now accessible on the host at port 443, proceed to access the Web browser at https://your.example.com/.
Here Standalone MinIO server instance is reverse proxied through Nginx load balancing.

## License

This project is licensed under the GNU Affero General Public License v3.0 - see the [LICENSE](LICENSE) file for details.
