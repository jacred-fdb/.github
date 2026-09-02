<!-- markdownlint-disable MD033 MD036 MD041 -->

<div align="center">

# jacred-fdb

**Open-source torrent tracker aggregation powered by JacRed**

[![Latest release](https://img.shields.io/github/v/release/jacred-fdb/jacred?label=stable&style=flat-square)](https://github.com/jacred-fdb/jacred/releases/latest)
[![Pre-release](https://img.shields.io/github/v/release/jacred-fdb/jacred?include_prereleases&label=pre-release&style=flat-square)](https://github.com/jacred-fdb/jacred/releases)
[![Build](https://img.shields.io/github/actions/workflow/status/jacred-fdb/jacred/build.yml?branch=main&style=flat-square&label=build)](https://github.com/jacred-fdb/jacred/actions/workflows/build.yml)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://github.com/jacred-fdb/jacred/blob/main/LICENSE)

[Documentation](https://docs.jacred.stream) · [Releases](https://github.com/jacred-fdb/jacred/releases) · [Report an issue](https://github.com/jacred-fdb/jacred/issues)

</div>

## JacRed

[JacRed](https://github.com/jacred-fdb/jacred) is a self-hosted torrent tracker aggregator with a fast file-based database. It combines 25 trackers behind one search service for Lampa, Sonarr, Radarr, Prowlarr, and other clients.

- Jackett, Torznab, Prowlarr, and native JSON APIs
- Local FileDB with remote synchronization and backups
- Independent tracker parsing through cron
- Built-in search, statistics, and configuration web interface
- Docker images for `amd64`, `arm64`, `arm`, and `386`
- Proxy, SOCKS5, Tor, and FlareSolverr support

## Quick start

Linux with systemd and cron:

```bash
curl -fsSL https://raw.githubusercontent.com/jacred-fdb/jacred/main/jacred.sh | bash
```

Docker:

```bash
docker run -d --name jacred -p 9117:9117 \
  -v jacred-config:/app/config -v jacred-data:/app/Data \
  --restart unless-stopped ghcr.io/jacred-fdb/jacred:latest
```

## Learn more

- [Installation](https://docs.jacred.stream/installation)
- [Configuration](https://docs.jacred.stream/configuration/overview)
- [Docker deployment](https://docs.jacred.stream/deployment/docker)
- [Tracker catalog](https://docs.jacred.stream/trackers/overview)
- [API reference](https://docs.jacred.stream/api-reference/overview)
- [Troubleshooting](https://docs.jacred.stream/operations/troubleshooting)

Building from source requires .NET 10. JacRed is available under the [MIT License](https://github.com/jacred-fdb/jacred/blob/main/LICENSE).

<!-- markdownlint-enable MD033 MD036 MD041 -->
