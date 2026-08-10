# Clash 订阅转换工具

[![GitHub release](https://img.shields.io/github/v/release/yourusername/clash-converter)](https://udith77-cyber.github.io/clash-converter/)
[![Docker Pulls](https://img.shields.io/docker/pulls/yourusername/clash-converter)](https://hub.docker.com/r/yourusername/clash-converter)
[![License](https://img.shields.io/github/license/yourusername/clash-converter)](LICENSE)

一个高性能的Clash订阅链接转换工具，支持多协议转换和规则增强。

![界面预览](screenshot.png)

## ✨ 特性

- 🔄 **多格式支持**：SS/SSR/V2Ray/Trojan 转 Clash 配置
- 🧩 **规则增强**：内置 20+ 常用规则集（GeoIP/广告拦截/流媒体解锁）
- 🌍 **节点过滤**：按地区/协议/延迟筛选节点
- 🚀 **高性能**：基于 Go 实现，单核可处理 10k+ 节点
- 🐳 **容器化部署**：提供 Docker 镜像，一键启动
- 🔒 **隐私安全**：所有转换在服务端内存完成，不保存用户数据

## 🚀 快速开始

### 在线服务（推荐）
访问公开实例：[[https://udith77-cyber.github.io/clash-converter/]](https://clash-converter.example.com)

### 自托管部署

#### 使用 Docker（最简单）
```bash
docker run -d \
  --name clash-converter \
  -p 8080:8080 \
  -e RULESET_MODE=full \
  --restart unless-stopped \
  ghcr.io/yourusername/clash-converter:latest
