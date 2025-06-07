# Homelab Services Documentation

## Network Overview
- **Linux Workstation**: VadersBridge (Main machine)
- **Synology NAS**: 192.168.50.92 (Media & Storage)

## Linux Mint Workstation (VadersBridge)

### Dashboard & Monitoring
| Service | Port | Purpose |
|---------|------|---------|
| Homepage | 3030 | Central dashboard with Imperial theme |
| Netdata | 19999 | Real-time system monitoring |
| Speedtest Tracker | 3032 | Internet speed tracking |

### Planned Services
- Uptime Kuma (3031) - Service availability monitoring

## Synology NAS (192.168.50.92)

### Media Stack
| Service | Port | Purpose |
|---------|------|---------|
| Plex | Standard | Media server |
| Radarr | 7878 | Movie management |
| Sonarr | 8989 | TV show management |
| Prowlarr | 9696 | Indexer management |
| Overseerr | 5055 | Media requests |
| qBittorrent | (via Gluetun) | Downloads |

### Support Services
| Service | Port | Purpose |
|---------|------|---------|
| Gluetun | 8090 | VPN container |
| FlareSolverr | 8191 | Cloudflare bypass |
| Watchtower | N/A | Auto-updates containers |
| vader-flix | 8091 | Custom web app |

## Port Reservations
- 3000-3099: Dashboard/Monitoring services
- 5000-5099: Request/Management services  
- 7000-7999: Media automation
- 8000-8999: Support services
- 9000-9999: Management tools

## Related Documentation

- [Widget Configuration](./widgets.md) - API keys and widget setup
- [Network Architecture](./network.md) - Service URLs and access details
