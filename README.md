# Minecraft Server — Cobbleverse

> **Pokemon Adventure [Cobblemon]** trên Mini PC | Fabric 1.21.1

## 🎮 Thông tin server

| Khoản | Giá trị |
|---|---|
| IP | `100.111.56.80:25565` (qua Tailscale) |
| Version | Minecraft **1.21.1** |
| Loader | **Fabric** |
| Modpack | **Cobbleverse 1.7.31** — 109 mods |
| Online-mode | `false` (cracked) |
| RAM | tối đa 5G |
| Image | `itzg/minecraft-server:java21` |

## 🗂 Cấu trúc repo

```
├── docker-compose.yml    # Service definition
├── .env                  # Environment variables (edit here)
├── eula.txt              # EULA đã accept
├── mods/                 # Drop .jar mod files here (optional)
├── config/               # Extra config overrides (optional)
├── data/                 # ⚡ Runtime data (world, logs, generated config) — local only
└── README.md
```

## 🚀 Cách chạy

```bash
docker compose up -d
docker compose logs -f    # Theo dõi log
docker compose down       # Tắt
```

### Config chính

Sửa file `.env` trước khi chạy:

- `TYPE=FABRIC` — loader
- `VERSION=1.21.1` — game version
- `MAX_MEMORY=5G` — RAM tối đa
- `ONLINE_MODE=false` — cho phép cracked
- `MOTD=...` — thông báo server list

## 🔐 Firewall (UFW)

Cổng đã mở:
- `22/tcp` — SSH
- `25565/tcp` — Minecraft
- `tailscale0` — toàn bộ (Tailscale internal)

## 📦 Modpack

**Cobbleverse 1.7.31** (Modrinth) — tự động download khi start lần đầu.
Cấu hình qua biến môi trường:
- `MODRINTH_PROJECT=cobbleverse`
- `MODRINTH_VERSION_ID=DN77rBht`
- `MODPACK_PLATFORM=modrinth`

## 🛠 Backups

World data tự động backup vào `backups/` trước mỗi lần cài modpack mới.
