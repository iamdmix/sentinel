# sentinel

A self-hosted homeserver stack running on Docker, exposed via Cloudflare Tunnel.

## Services

| Service | Port | Description |
|---------|------|-------------|
| [Jellyfin](http://localhost:8096) | 8096 | Media server |
| Portfolio | 8081 | Personal website (nginx) |
| [Portainer](http://localhost:9000) | 9000 | Docker management UI |
| [Uptime Kuma](http://localhost:3001) | 3001 | Uptime monitoring |
| [Prometheus](http://localhost:9090) | 9090 | Metrics collection |
| [Grafana](http://localhost:3002) | 3002 | Metrics dashboards |
| cAdvisor | 8082 | Container metrics |
| Node Exporter | — | Host metrics |

## Getting Started

1. Copy the example env and fill in your values:
   ```bash
   cp .env.example .env
   ```
2. Start all services:
   ```bash
   docker compose up -d
   ```
3. Stop all services:
   ```bash
   docker compose down
   ```

## Cloudflare Tunnel

The stack is exposed publicly via a Cloudflare Tunnel. Set `CLOUDFLARE_TUNNEL_ID` and `CLOUDFLARE_CREDENTIALS_FILE` in `.env` before starting.

## Stack

- Docker + Docker Compose
- Cloudflare Tunnel (`cloudflared`)
- Prometheus + Grafana for observability
- Nginx for static portfolio hosting
# sentinel
