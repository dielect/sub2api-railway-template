# Sub2API Railway Template

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/deploy/sub2api-railway-template)

English | [中文](#中文)

One-click deploy [Sub2API](https://github.com/Wei-Shaw/sub2api) on Railway with PostgreSQL and Redis included.

**Railway Deploy Link:**  
https://railway.com/deploy/sub2api-railway-template

---

## English

### Overview

This repository provides a Railway deployment template for [Sub2API](https://github.com/Wei-Shaw/sub2api).

Sub2API is a high-performance AI API gateway built for managing, distributing, and monitoring usage across subscription-based AI accounts. With this template, you can deploy a complete Sub2API stack on Railway in one click, including the core application, PostgreSQL database, and Redis cache.

Railway automatically provisions the required infrastructure and connects all services over its private network, making deployment fast, secure, and easy to manage.

### Features

- One-click deployment on Railway
- Includes **Sub2API**, **PostgreSQL**, and **Redis**
- Suitable for production-ready setup
- Private network communication between services
- Simple initialization flow through the Sub2API web interface

### Included Services

This template deploys the following services:

- **Sub2API Gateway**  
  The main application, including backend API and web UI

- **PostgreSQL**  
  Used for persistent storage such as users, API keys, billing records, and system configuration

- **Redis**  
  Used for caching, rate limiting, queue management, and performance optimization

### Required Environment Variables

After deployment, you need to configure the following environment variables for the **Sub2API** service.

| Variable | Required | Description |
| --- | --- | --- |
| `ADMIN_EMAIL` | Yes | Email address for the initial administrator account. You can set this freely. |
| `TOTP_ENCRYPTION_KEY` | Yes | Encryption key used for TOTP-related data. Must be securely generated. |

#### `ADMIN_EMAIL`

You can set any email address you want, for example:

```env
ADMIN_EMAIL=admin@example.com
```

#### `TOTP_ENCRYPTION_KEY`

Generate it with:

```bash
openssl rand -hex 32
```

Example:

```env
TOTP_ENCRYPTION_KEY=your_generated_64_char_hex_string
```

> Recommended: keep this value secret and do not change it after your instance is initialized unless you know the impact on existing encrypted data.

### Deployment Steps

1. Open the Railway deploy link:  
   https://railway.com/deploy/sub2api-railway-template
2. Create a new Railway project from this template
3. Wait for Railway to provision:
   - Sub2API
   - PostgreSQL
   - Redis
4. Open the **Sub2API** service in your Railway project
5. Add the required environment variables:
   - `ADMIN_EMAIL`
   - `TOTP_ENCRYPTION_KEY`
6. Go to **Settings**
7. Click **Generate Domain**
8. Open the generated domain in your browser
9. Complete the Sub2API initialization process

### Common Use Cases

- Share AI subscription quota across team members
- Track token usage and operational costs
- Build a centralized AI API gateway
- Manage upstream routing, rate limiting, and access control

### Related Links

- **Railway Deploy**: https://railway.com/deploy/sub2api-railway-template
- **Sub2API Repository**: https://github.com/Wei-Shaw/sub2api
- **Docker Image**: https://hub.docker.com/r/weishaw/sub2api
- **Documentation**: https://github.com/Wei-Shaw/sub2api/blob/main/README_CN.md

### Notes

- Make sure `TOTP_ENCRYPTION_KEY` is generated securely before first use
- `ADMIN_EMAIL` can be any email address you choose
- You can further scale services using Railway if your workload grows

---

## 中文

### 项目简介

这个仓库提供了一个用于在 Railway 上部署 [Sub2API](https://github.com/Wei-Shaw/sub2api) 的模板。

Sub2API 是一个高性能的 AI API 网关，适用于统一管理、分发和监控基于订阅账号的 AI 配额使用。通过这个模板，你可以在 Railway 上一键部署完整的 Sub2API 运行环境，包括核心应用、PostgreSQL 数据库和 Redis 缓存。

Railway 会自动创建所需的基础设施，并通过私有网络连接各个服务，使部署过程更加快速、安全且易于管理。

### 功能特性

- 支持 Railway 一键部署
- 内置 **Sub2API**、**PostgreSQL** 和 **Redis**
- 适合快速搭建生产可用环境
- 服务之间通过 Railway 私有网络通信
- 可通过 Sub2API Web 界面完成初始化配置

### 包含的服务

该模板会部署以下服务：

- **Sub2API Gateway**  
  主应用服务，包含后端 API 和 Web 管理界面

- **PostgreSQL**  
  用于持久化存储用户、API Key、计费记录和系统配置等数据

- **Redis**  
  用于缓存、限流、队列管理和性能优化

### 必填环境变量

部署完成后，你需要为 **Sub2API** 服务配置以下环境变量：

| 变量名 | 必填 | 说明 |
| --- | --- | --- |
| `ADMIN_EMAIL` | 是 | 初始化管理员账号使用的邮箱地址，可自由填写 |
| `TOTP_ENCRYPTION_KEY` | 是 | 用于加密 TOTP 相关数据的密钥，必须安全生成 |

#### `ADMIN_EMAIL`

你可以自由填写任意邮箱地址，例如：

```env
ADMIN_EMAIL=admin@example.com
```

#### `TOTP_ENCRYPTION_KEY`

请使用以下命令生成：

```bash
openssl rand -hex 32
```

示例：

```env
TOTP_ENCRYPTION_KEY=你生成的64位十六进制字符串
```

> 建议：请妥善保管该密钥。实例初始化完成后，除非你明确了解影响，否则不要随意修改。

### 部署步骤

1. 打开 Railway 部署链接：  
   https://railway.com/deploy/sub2api-railway-template
2. 使用该模板创建一个新的 Railway 项目
3. 等待 Railway 自动创建以下服务：
   - Sub2API
   - PostgreSQL
   - Redis
4. 打开 Railway 项目中的 **Sub2API** 服务
5. 添加必填环境变量：
   - `ADMIN_EMAIL`
   - `TOTP_ENCRYPTION_KEY`
6. 进入 **Settings**
7. 点击 **Generate Domain**
8. 使用生成的域名在浏览器中打开服务
9. 完成 Sub2API 初始化配置

### 常见使用场景

- 团队共享 AI 订阅配额
- 统计 Token 使用量与成本
- 搭建统一的 AI API 网关入口
- 管理上游路由、限流和访问控制

### 相关链接

- **Railway 部署地址**: https://railway.com/deploy/sub2api-railway-template
- **Sub2API 项目地址**: https://github.com/Wei-Shaw/sub2api
- **Docker 镜像**: https://hub.docker.com/r/weishaw/sub2api
- **项目文档**: https://github.com/Wei-Shaw/sub2api/blob/main/README_CN.md

### 注意事项

- 请在首次使用前安全生成 `TOTP_ENCRYPTION_KEY`
- `ADMIN_EMAIL` 可以填写任意你希望使用的邮箱
- 如果业务规模增长，可以进一步使用 Railway 的扩缩容能力

---

## License

Please refer to the upstream Sub2API project for license details:  
https://github.com/Wei-Shaw/sub2api
