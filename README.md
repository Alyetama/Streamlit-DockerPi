# Streamlit-Docker-Pi
Raspberry Pi, Docker, Streamlit, Poetry

## SSL-proxy (optional)

### Install Caddy

```bash
$ sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
$ curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /etc/apt/trusted.gpg.d/caddy-stable.asc
$ curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
$ sudo apt update
$ sudo apt install caddy
```

### Run Caddy server

``bash
$ systemctl start caddy
$ caddy run --environ --config ./Caddyfile  # Replace <domain_name> in Caddyfile with your domain's name
```


## Run the container

```bash
DOCKER_BUILDKIT=1 docker-compose up --detach
```
