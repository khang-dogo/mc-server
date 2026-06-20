# Mods

Bỏ file `.jar` mod vào đây, rồi chạy:

```bash
docker compose restart
```

Server tự động copy mod vào `/data/mods/` khi start.

### Lưu ý
- Mod phải compatible với **Forge 1.21.1**
- Cả server và client đều cần cùng mods
- Dùng `REMOVE_OLD_MODS=true` trong `.env` nếu muốn xoá mod cũ tự động
