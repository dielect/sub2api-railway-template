# Sub2API Railway Template

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/deploy/sub2api-railway-template)

English | [中文](README_CN.md)

One-click deploy [Sub2API](https://github.com/Wei-Shaw/sub2api) on Railway with PostgreSQL and Redis included.

**Railway Deploy Link:**  
https://railway.com/deploy/sub2api-railway-template

---

## Overview

This repository provides a Railway deployment template for [Sub2API](https://github.com/Wei-Shaw/sub2api).

Sub2API is a high-performance AI API gateway built for managing, distributing, and monitoring usage across subscription-based AI accounts. With this template, you can deploy a complete Sub2API stack on Railway in one click, including the core application, PostgreSQL database, and Redis cache.

Railway automatically provisions the required infrastructure and connects all services over its private network, making deployment fast, secure, and easy to manage.

## Features

- One-click deployment on Railway
- Includes **Sub2API**, **PostgreSQL**, and **Redis**
- Suitable for production-ready setup
- Private network communication between services
- Simple initialization flow through the Sub2API web interface

## Included Services

This template deploys the following services:

- **Sub2API Gateway**  
  The main application, including backend API and web UI

- **PostgreSQL**  
  Used for persistent storage such as users, API keys, billing records, and system configuration

- **Redis**  
  Used for caching, rate limiting, queue management, and performance optimization

## Required Environment Variables

After deployment, you need to configure the following environment variables for the **Sub2API** service.

| Variable | Required | Description |
| --- | --- | --- |
| `ADMIN_EMAIL` | Yes | Email address for the initial administrator account. You can set this freely. |
| `TOTP_ENCRYPTION_KEY` | Yes | Encryption key used for TOTP-related data. Must be securely generated. |

### `ADMIN_EMAIL`

You can set any email address you want, for example:

```env
ADMIN_EMAIL=admin@example.com
```

### `TOTP_ENCRYPTION_KEY`

Generate it with:

```bash
openssl rand -hex 32
```

Example:

```env
TOTP_ENCRYPTION_KEY=your_generated_64_char_hex_string
```

> Recommended: keep this value secret and do not change it after your instance is initialized unless you know the impact on existing encrypted data.

## Deployment Steps

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

## Common Use Cases

- Share AI subscription quota across team members
- Track token usage and operational costs
- Build a centralized AI API gateway
- Manage upstream routing, rate limiting, and access control

## Related Links

- **Railway Deploy**: https://railway.com/deploy/sub2api-railway-template
- **Sub2API Repository**: https://github.com/Wei-Shaw/sub2api
- **Docker Image**: https://hub.docker.com/r/weishaw/sub2api
- **Documentation**: https://github.com/Wei-Shaw/sub2api/blob/main/README_CN.md

## Notes

- Make sure `TOTP_ENCRYPTION_KEY` is generated securely before first use
- `ADMIN_EMAIL` can be any email address you choose
- You can further scale services using Railway if your workload grows

---

## License

Please refer to the upstream Sub2API project for license details:  
https://github.com/Wei-Shaw/sub2api
