# clash-node

使用 Docker Compose 部署 Mihomo Shadowsocks 节点，并通过 Nginx 提供 Clash/Mihomo 订阅。

## 使用方法

```bash
cp config.example.yaml config.yaml
cp sub.example.yaml sub.yaml
```

将 `config.yaml` 和 `sub.yaml` 中的 `CHANGE_ME_PASSWORD` 替换为同一个强密码，然后启动：

```bash
docker-compose up -d
```

默认端口：

- `8388/TCP` 和 `8388/UDP`：Shadowsocks 代理
- `8088/TCP`：订阅地址 `http://服务器地址:8088/sub.yaml`

订阅文件包含代理密码，不建议将 `8088` 直接暴露到公网。公网使用时只需映射并放行 `8388/TCP` 和 `8388/UDP`。

## 管理命令

```bash
docker-compose ps
docker-compose logs -f
docker-compose restart
docker-compose down
```
