<div align="center">

# jacred-fdb

**Torrent Tracker Aggregation Platform**

[![Latest Release](https://img.shields.io/github/v/release/jacred-fdb/jacred?label=stable&style=flat-square)](https://github.com/jacred-fdb/jacred/releases/latest)
[![Pre-release](https://img.shields.io/github/v/release/jacred-fdb/jacred?include_prereleases&label=pre-release&style=flat-square)](https://github.com/jacred-fdb/jacred/releases)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://github.com/jacred-fdb/jacred/blob/main/LICENSE)
[![Docker](https://img.shields.io/badge/docker-supported-2496ED?style=flat-square&logo=docker)](https://github.com/jacred-fdb/jacred)

</div>

---

## Mission

**jacred-fdb** develops and maintains open-source tooling for torrent tracker aggregation. The platform provides a unified API layer across multiple trackers, backed by a fast file-based database (fdb), full [Jackett](https://github.com/Jackett/Jackett) API compatibility, and deployment options via Docker or systemd.

---

## Core Project

### [jacred](https://github.com/jacred-fdb/jacred)

A self-hosted torrent aggregator and file database. JacRed indexes torrent metadata from multiple trackers, stores it in a local file DB, and supports both remote sync and independent parsing via cron.

**Features**

| Capability | Description |
|------------|-------------|
| **Jackett API** | Full compatibility with Jackett format |
| **File DB (fdb)** | Fast local storage with sync and backup |
| **Dual operation** | Sync from remote servers or self-parse via cron |
| **Web UI** | Built-in interface for search and management |
| **Proxy & Tor** | SOCKS5 support for .onion domains |
| **Tracks module** | Optional metadata collection (tsuri) |
| **Caching** | High-performance evercache for file access |
| **Docker** | Multi-arch images at `ghcr.io/jacred-fdb/jacred` |

**Supported trackers**

| Status | Trackers |
|--------|----------|
| Active (parse and/or sync) | Kinozal, NNMClub, Rutor, TorrentBy, Bitru, Rutracker, Megapeer, Selezen, Toloka, Mazepa, Baibako, Lostfilm, Animelayer |
| Retired (sync-only from legacy bases) | Anifilm, AniLibria, HDRezka |

---

## Quick Start

**Script installation** (Debian/Ubuntu, systemd + cron):

```bash
curl -s https://raw.githubusercontent.com/jacred-fdb/jacred/main/jacred.sh | bash
```

| Option | Description |
|--------|-------------|
| `--no-download-db` | Skip initial database download |
| `--pre-release` | Install latest pre-release |
| `--update` | Update existing installation |

**Docker:**

```bash
docker run -d --name jacred -p 9117:9117 \
  -v jacred-config:/app/config -v jacred-data:/app/Data \
  --restart unless-stopped ghcr.io/jacred-fdb/jacred:latest
```

Post-install: configure `init.yaml` or `init.conf` in `/opt/jacred/`, then `systemctl restart jacred`.

---

## Documentation

- **Config examples:** [Data/example.yaml](https://github.com/jacred-fdb/jacred/blob/main/Data/example.yaml), [Data/example.conf](https://github.com/jacred-fdb/jacred/blob/main/Data/example.conf)
- **Cloudflare Worker router:** [router/README.md](https://github.com/jacred-fdb/jacred/tree/main/router)
- **Requirements:** .NET 9.0 (from source); Linux with systemd/cron (script install)
