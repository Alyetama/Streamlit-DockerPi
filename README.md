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

```bash
$ systemctl start caddy
$ caddy run --environ --config ./Caddyfile  # Replace <domain_name> in Caddyfile with your domain's name*
# *you will need to point an A record on your domain provider's zone editor to the server's ip
```


## Run the container

```bash
DOCKER_BUILDKIT=1 docker-compose up --detach  # uncomment the image line and uncomment the build line if you don't have access to the private registry
```
