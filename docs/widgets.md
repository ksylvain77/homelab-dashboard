# Homepage Widget Configuration

This document contains the API keys and configuration for all Homepage widgets. 

**⚠️ SECURITY NOTE**: This file contains sensitive API keys. Ensure your repository is private.

## Widget Configurations

### Media Services

#### Radarr
- **API Key**: `1796ecf4c4f244bfa6b7db47c6e271b0`
- **Widget Type**: `radarr`
- **Features**: Movie count, queue status, missing movies

#### Sonarr  
- **API Key**: `8709f14bd30d4924bc76349878a1a06f`
- **Widget Type**: `sonarr`
- **Features**: TV show count, upcoming episodes, queue

#### Plex
- **Auth Token**: `QWQEjkGeKFsy3eQUYB1-`
- **Widget Type**: `plex`
- **Features**: Active streams, library counts, total items

#### Overseerr
- **API Key**: `MTc0NzY0ODMxOTM3NDc4NTdlYTEyLWNhN2YtNGRhYS05M2VkLTU5YzIyZWFmZDNkMQ==`
- **Widget Type**: `overseerr`
- **Features**: Pending requests, available items

### Download Services

#### Prowlarr
- **API Key**: `06329eca76a94f1a8b43322aeff38031`
- **Widget Type**: `prowlarr`
- **Features**: Indexer stats, health status

#### qBittorrent
- **Username**: `kevin`
- **Password**: `kevinkevin`
- **Widget Type**: `qbittorrent`
- **Features**: Download/upload speeds, active torrents
- **Access**: Via Gluetun VPN on port 8090

### Monitoring Services

#### Speedtest Tracker
- **Widget Type**: `customapi`
- **API Endpoint**: `/api/speedtest/latest`
- **Internal URL**: `http://speedtest-tracker:80`
- **Features**: Download/upload speeds, ping
- **Note**: Uses custom API mappings for data fields

## Services Without Widgets

These services are displayed on Homepage but don't have widget support:

- **Pi-hole**: DNS & Ad Blocking (port 80/admin)
- **Synology NAS**: DS243+ Storage Server (port 5000)
- **Uptime Kuma**: Service Monitoring (port 3031) - *Not yet deployed*
- **Netdata**: Real-time Performance Monitoring (port 19999)
- **VaderFlix**: Custom Media App (port 8091)
- **FlareSolverr**: Cloudflare Bypass (port 8191)
- **Gluetun**: VPN Container (port 8090)
- **Watchtower**: Auto-update Containers

## Adding New Widgets

1. Get the API key from the service (usually Settings → General)
2. Add widget configuration to `config/homepage/services.yaml`
3. Update this documentation with the key for future reference

## Widget Template

```yaml
- Service Name:
    icon: service-icon.png
    href: http://service-url
    description: Service description
    widget:
      type: widget-type
      url: http://service-url
      key: YOUR_API_KEY
```

## Network Architecture

- Homepage accesses local services via Docker network names (e.g., speedtest-tracker)
- NAS services are accessed via IP: 192.168.50.92
- VPN routing: qBittorrent traffic routes through Gluetun container 