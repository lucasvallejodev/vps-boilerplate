# VPS Reverse Proxy with Traefik, Nginx, and Open Web UI

This project provides a boilerplate setup to roll out a VPS reverse proxy using Traefik, with examples for Nginx and Open Web UI, all managed using Docker.

## Project Structure

```
nginx/
    docker-compose.yaml
open-webui/
    docker-compose.yaml
    open-webui-local/ # Open Web UI data
traefik/
    .env.example
    docker-compose.yaml
    README.md
    config/
        traefik.yaml
    data/ # Traefik persisted data
```

## Prerequisites

- Docker
- Docker Compose
- A VPS with a public IP
- A domain name

## Setup

### 1. Clone the Repository

```sh
git clone https://github.com/yourusername/vps-reverse-proxy.git
cd vps-reverse-proxy
```

### 2. Configure Traefik

1. Navigate to the `traefik` directory:

    ```sh
    cd traefik
    ```

2. Rename the `.env.example` file to `.env` and fill in your Cloudflare API token:

    ```sh
    cp .env.example .env
    ```

    ```env
    CF_DNS_API_TOKEN='YOUR_CLOUDFLARE_API_TOKEN'
    ```

3. Review and adjust `traefik.yaml` configuration in the `config` directory as needed.

### 3. Start Traefik

```sh
docker-compose up -d
```

### 4. Configure Nginx

1. Navigate to the `nginx` directory:

    ```sh
    cd ../nginx
    ```

2. Review and adjust the `docker-compose.yaml` file as needed.

### 5. Start Nginx

```sh
docker-compose up -d
```

### 6. Configure Open Web UI

1. Navigate to the `open-webui` directory:

    ```sh
    cd ../open-webui
    ```

2. Review and adjust the `docker-compose.yaml` file as needed.

### 7. Start Open Web UI

```sh
docker-compose up -d
```

## Accessing Services

- Traefik Dashboard: `https://monitor.yourdomain.com`
- Nginx: `https://notes.yourdomain.com`
- Open Web UI: `https://ai.yourdomain.com`

## Encryption

Environment variables for encryption are stored in the `.env` file:

```
CF_DNS_API_TOKEN='YOUR_CLOUDFLARE_API_TOKEN'
```

## License

This project is licensed under the MIT License.