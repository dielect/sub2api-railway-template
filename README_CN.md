# Sub2API Railway Template

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/deploy/sub2api-railway-template)

[English](README.md) | 中文

一键部署 [Sub2API](https://github.com/Wei-Shaw/sub2api) 到 Railway，内置 PostgreSQL 和 Redis。

**Railway 部署链接：**  
https://railway.com/deploy/sub2api-railway-template

---

## 项目简介

这个仓库提供了一个用于在 Railway 上部署 [Sub2API](https://github.com/Wei-Shaw/sub2api) 的模板。

Sub2API 是一个高性能的 AI API 网关，适用于统一管理、分发和监控基于订阅账号的 AI 配额使用。通过这个模板，你可以在 Railway 上一键部署完整的 Sub2API 运行环境，包括核心应用、PostgreSQL 数据库和 Redis 缓存。

Railway 会自动创建所需的基础设施，并通过私有网络连接各个服务，使部署过程更加快速、安全且易于管理。

## 功能特性

- 支持 Railway 一键部署
- 内置 **Sub2API**、**PostgreSQL** 和 **Redis**
- 适合快速搭建生产可用环境
- 服务之间通过 Railway 私有网络通信
- 可通过 Sub2API Web 界面完成初始化配置

## 包含的服务

该模板会部署以下服务：

- **Sub2API Gateway**  
  主应用服务，包含后端 API 和 Web 管理界面

- **PostgreSQL**  
  用于持久化存储用户、API Key、计费记录和系统配置等数据

- **Redis**  
  用于缓存、限流、队列管理和性能优化

## 必填环境变量

部署完成后，你需要为 **Sub2API** 服务配置以下环境变量：

| 变量名 | 必填 | 说明 |
| --- | --- | --- |
| `ADMIN_EMAIL` | 是 | 初始化管理员账号使用的邮箱地址，可自由填写 |
| `TOTP_ENCRYPTION_KEY` | 是 | 用于加密 TOTP 相关数据的密钥，必须安全生成 |

### `ADMIN_EMAIL`

你可以自由填写任意邮箱地址，例如：

```env
ADMIN_EMAIL=admin@example.com
```

### `TOTP_ENCRYPTION_KEY`

请使用以下命令生成：

```bash
openssl rand -hex 32
```

示例：

```env
TOTP_ENCRYPTION_KEY=你生成的64位十六进制字符串
```

> 建议：请妥善保管该密钥。实例初始化完成后，除非你明确了解影响，否则不要随意修改。

## 部署步骤

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

## 常见使用场景

- 团队共享 AI 订阅配额
- 统计 Token 使用量与成本
- 搭建统一的 AI API 网关入口
- 管理上游路由、限流和访问控制

## 相关链接

- **Railway 部署地址**: https://railway.com/deploy/sub2api-railway-template
- **Sub2API 项目地址**: https://github.com/Wei-Shaw/sub2api
- **Docker 镜像**: https://hub.docker.com/r/weishaw/sub2api
- **项目文档**: https://github.com/Wei-Shaw/sub2api/blob/main/README_CN.md

## 注意事项

- 请在首次使用前安全生成 `TOTP_ENCRYPTION_KEY`
- `ADMIN_EMAIL` 可以填写任意你希望使用的邮箱
- 如果业务规模增长，可以进一步使用 Railway 的扩缩容能力

---

## 许可证

许可证详情请参考上游 Sub2API 项目：  
https://github.com/Wei-Shaw/sub2api
