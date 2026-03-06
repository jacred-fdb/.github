<div align="center">

# 🔍 jacred-fdb

**Unified Torrent Tracker Aggregation Platform**

[![Latest Release](https://img.shields.io/github/v/release/jacred-fdb/jacred?label=stable&style=flat-square)](https://github.com/jacred-fdb/jacred/releases/latest)
[![Pre-release](https://img.shields.io/github/v/release/jacred-fdb/jacred?include_prereleases&label=pre-release&style=flat-square)](https://github.com/jacred-fdb/jacred/releases)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://github.com/jacred-fdb/jacred/blob/main/LICENSE)
[![Docker](https://img.shields.io/badge/docker-supported-2496ED?style=flat-square&logo=docker)](https://github.com/jacred-fdb/jacred)

</div>

---

## 🎯 Mission

**jacred-fdb** develops and maintains open-source tooling for torrent tracker aggregation — providing a single, unified API layer over multiple trackers with a fast file-based database (fdb), [Jackett](https://github.com/Jackett/Jackett)-compatible API, and straightforward self-hosting via Docker or systemd.

---

## 📦 Core Project

### [`jacred`](https://github.com/jacred-fdb/jacred)

A self-hosted torrent tracker aggregator & file database. Aggregates torrents from multiple trackers into a unified API, stores data in a file DB (fdb), and supports sync with remote servers or independent parsing via cron.

**Key capabilities:**

- 🔍 **Torrent aggregation** — multiple trackers in a single API
- 📦 **File DB (fdb)** — fast local storage with sync and backup support
- 🎯 **Jackett API** — full compatibility with Jackett format
- 🔄 **Sync or parse** — pull from remote servers or self-parse trackers via cron
- 🌐 **Web interface** — built-in UI for viewing and management
- 🔐 **Proxy & Tor** — access .onion domains via SOCKS5
- 📊 **Statistics** — tracker and torrent stats
- 🎵 **Tracks module** — optional metadata collection for tracks (tsuri)
- ⚡ **Caching** — high-performance file cache (evercache)
- 🐳 **Docker** — multi-arch images (`ghcr.io/jacred-fdb/jacred`)

**Active trackers:** Kinozal, NNMClub, Rutor, TorrentBy, Bitru, Rutracker, Megapeer, Selezen, Toloka, Mazepa, Baibako, Lostfilm, Animelayer.

**RIP (sync-only):** Anifilm, AniLibria, HDRezka.

---

## 🚀 Quick Start

**Install via script** (Debian/Ubuntu, systemd + cron):

```bash
# Stable
curl -s https://raw.githubusercontent.com/jacred-fdb/jacred/main/jacred.sh | bash

# Without downloading DB
curl -s https://raw.githubusercontent.com/jacred-fdb/jacred/main/jacred.sh | bash -s -- --no-download-db

# Pre-release
curl -s https://raw.githubusercontent.com/jacred-fdb/jacred/main/jacred.sh | bash -s -- --pre-release

# Update existing install
sudo /opt/jacred/jacred.sh --update
```

**Docker:**

```bash
docker run -d --name jacred -p 9117:9117 \
  -v jacred-config:/app/config -v jacred-data:/app/Data \
  --restart unless-stopped ghcr.io/jacred-fdb/jacred:latest
```

After install: configure `/opt/jacred/init.yaml` or `init.conf`, then `systemctl restart jacred`.

---

## 📚 Resources

- **Docs & config examples:** [`Data/example.yaml`](https://github.com/jacred-fdb/jacred/blob/main/Data/example.yaml), [`Data/example.conf`](https://github.com/jacred-fdb/jacred/blob/main/Data/example.conf)
- **Cloudflare Worker router:** [`router/README.md`](https://github.com/jacred-fdb/jacred/tree/main/router) — edge routing for backends
- **Requirements:** .NET 9.0 (from source), Linux with systemd/cron (script install)
