# immich-docker-compose

## Immich 反向地理编码汉化

[链接](https://github.com/ZingLix/immich-geodata-cn)

### 下载 i18n-iso-countries.zip

```bash
# 在项目根目录下操作

curl -L -o i18n-iso-countries.zip https://github.com/ZingLix/immich-geodata-cn/releases/download/auto-release/i18n-iso-countries.zip
unzip i18n-iso-countries.zip
```

### 下载 geodata

```bash
# 在 geodata 目录下进行操作

cd geodata

# 下载脚本
curl -o update.sh https://raw.githubusercontent.com/ZingLix/immich-geodata-cn/refs/heads/main/geodata/update.sh

# 运行更新脚本，参数为你需要的版本，例如 geodata_admin_2_admin_3
bash update.sh geodata_admin_2_admin_3
```

### 重启 Immich

```bash
sudo docker compose down && sudo docker compose up -d
```

### 目录结构

```text
├── Immich
    ├── appdata
    │   ├── postgres
    │   └── model-cache
    │
    ├── geodata
    ├── i18n-iso-countries
    │   └── langs
    │
    └── library
        ├── internal-library
        │   ├── backups
        │   ├── encoded-video
        │   ├── library
        │   ├── profile
        │   ├── thumbs
        │   └── upload
        │
        └── external-library
            ├── Travel
            │   ├── 2026-05 长沙旅行
            │
            ├── DJI-Action
            │   ├── 骑行
            │
            ├── Life
            │   ├── 日常
            │   ├── 健身
            │
            └── Edited
                ├── Shorts
                ├── Vlog
```
