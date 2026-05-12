<div align="center">

# New API（企业内网版）

🍥 **大模型网关与AI资产管理系统**

适合企业内网部署的精简版本

</div>

---

## 项目说明

基于 New API 精简的企业内网版本，移除了公开版功能，专注于 API 网关核心能力。

**已移除功能：**
- 充值/钱包/订阅功能
- 兑换码系统
- Playground 聊天测试
- 价格表/Model Square
- 排行榜
- 用户协议/隐私政策页面
- 控制台日志/充值记录

---

## 快速开始

### 克隆项目

```bash
git clone https://github.com/stephen-jx/new-api.git
cd new-api
```

### Docker 部署（推荐）

```bash
# 使用 SQLite
docker run --name new-api -d --restart always \
  -p 3000:3000 \
  -e TZ=Asia/Shanghai \
  -v ./data:/data \
  calciumion/new-api:latest

# 或使用 Docker Compose
docker-compose up -d
```

部署完成后访问 `http://localhost:3000`

**默认管理员：** 用户名 `root`，密码 `123456`

---

## 主要特性

| 特性 | 说明 |
|------|------|
| 🎨 现代化 UI | 简洁的企业内网风格界面 |
| 🔒 权限管理 | 令牌分组、模型限制、用户管理 |
| 📈 数据看板 | 可视化统计分析 |
| 🔄 智能路由 | 渠道加权、失败重试、模型限流 |

---

## 模型支持

- OpenAI Compatible API
- Claude Messages
- Google Gemini
- Rerank 模型
- Midjourney-Proxy
- Suno-API

---

## 环境变量

| 变量名 | 说明 | 默认值 |
|--------|------|--------|
| `SESSION_SECRET` | 会话密钥 | - |
| `SQL_DSN` | 数据库连接（MySQL/PostgreSQL） | SQLite |
| `REDIS_CONN_STRING` | Redis 连接 | - |

---

## 部署要求

- Docker 或 Docker Compose
- SQLite（默认）或 MySQL ≥ 5.7.8 或 PostgreSQL ≥ 9.6

---

## 许可证

本项目基于 [Calcium-Ion/new-api](https://github.com/Calcium-Ion/new-api) 二次开发，遵循 AGPLv3 许可证。

---

<div align="center">

Made with ❤️ for enterprise internal use

</div>
