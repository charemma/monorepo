# charemma.de Website

Statische Portfolio-Webseite, deployed mit Caddy.

## Setup

Caddy kuemmert sich automatisch um:
- HTTPS Zertifikate via Let's Encrypt
- Automatische Zertifikat-Erneuerung
- HTTP zu HTTPS Redirect
- HTTP/2 und HTTP/3

## Deployment

```bash
just deploy    # Alles: sync + container restart
just sync      # Nur Dateien syncen
just logs      # Container Logs
just status    # Container Status
just restart   # Container neustarten
```

## Lokale Entwicklung

```bash
just dev       # Startet lokalen Server auf http://localhost:8080
```

## Dateien

- `Caddyfile` - Caddy Konfiguration
- `docker-compose.yml` - Container Setup
- `html/` - Statische Webseiten-Inhalte

## Volumes

- `caddy_data` - Zertifikate und ACME Account (persistent)
- `caddy_config` - Caddy Konfiguration Cache
