# clash-node

使用 Docker Compose 部署 Mihomo Shadowsocks 节点，并通过 Nginx 提供 Clash/Mihomo 订阅。配置已完成，克隆后可以直接启动。

## 使用方法

```bash
docker-compose up -d
```

默认端口：

- `8388/TCP` 和 `8388/UDP`：Shadowsocks 代理
- `8088/TCP`：订阅服务

局域网订阅地址：

```text
http://192.168.0.200:8088/sub.yaml
```

订阅文件包含代理密码，不建议将 `8088` 直接暴露到公网。公网使用时只需映射并放行 `8388/TCP` 和 `8388/UDP`。

## 管理命令

```bash
docker-compose ps
docker-compose logs -f
docker-compose restart
docker-compose down
```
