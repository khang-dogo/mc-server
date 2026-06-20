# Minecraft Server — Mini PC (1.21.1 Forge)

Docker-based Minecraft server using `itzg/minecraft-server`.

## Quick start

```bash
cd ~/workspace/minipc-workspace/minecraft
docker compose up -d
```

## Cấu trúc

```
minecraft/
├── docker-compose.yml   # Docker config
├── .env                 # Biến môi trường (sửa VERSION, MEMORY, TYPE...)
├── eula.txt             # EULA (đã accept)
├── data/                # World, logs, server.properties — edit trực tiếp ở đây
│   └── server.properties   # Config server (sửa thoải mái, không bị ghi đè)
├── mods/                # Bỏ file .jar mod vào đây → restart server
│   └── README.md
├── config/              # Extra config files (optional)
└── README.md
```

## Quản lý

- **Sửa config**: chỉnh `data/server.properties` rồi `docker compose restart`
- **Thêm mod**: bỏ `.jar` vào `mods/` → `docker compose restart` (tự động copy vào data)
- **Xem log**: `docker compose logs -f`
- **Dừng**: `docker compose down`
- **Backup world**: `tar czf backup-$(date +%Y%m%d).tar.gz data/world/`

## Sync GitHub

Thư mục này nằm trong `minipc-workspace` — commit & push từ GitHub, pull về mini PC.
