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

## 保留功能一览

### 📊 Dashboard 仪表盘
- 今日/本月请求统计
- Token 消耗趋势图
- 渠道调用分布
- 快捷操作入口

### 🔌 渠道管理
- 多渠道配置（OpenAI/Claude/Gemini 等）
- 渠道分组与优先级
- 模型映射与权重
- 失败重试策略
- 渠道健康检测

### 🔑 令牌管理
- API Key 生成与管理
- 令牌分组（按团队/项目）
- 模型白名单/黑名单
- 额度限制与有效期
- 请求统计

### 👥 用户管理
- 用户创建/编辑/禁用
- 角色权限控制
- 用户分组

### 📝 日志查询
- 请求日志搜索
- 按渠道/令牌/模型筛选
- 详情查看（请求/响应内容）

### ⚙️ 系统设置
- 站点配置（Logo/名称）
- 模型价格配置
- 支付设置（已禁用）
- 邮件通知
- 第三方登录（可选）

---

## 页面结构

```
├── 首页 → 登录后直跳 Dashboard
├── Dashboard
│   ├── 统计概览
│   └── 快捷操作
├── 渠道
│   ├── 渠道列表
│   └── 新建/编辑渠道
├── 令牌
│   ├── 令牌列表
│   └── 新建/编辑令牌
├── 用户
│   └── 用户列表
├── 日志
│   └── 请求日志
├── 模型
│   └── 模型配置
└── 设置
    ├── 系统设置
    └── 其他配置
```

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

## 支持的模型

| 类型 | 支持的模型 |
|------|-----------|
| OpenAI | GPT-4o, GPT-4, GPT-3.5-turbo, o1, o3 |
| Claude | Claude-3.5-sonnet, Claude-3-opus |
| Google | Gemini Pro, Gemini Flash |
| 国产 | 通义千问、文心一言、讯飞星火、智谱、DeepSeek |
| 其他 | Rerank 模型、Midjourney、Suno |

---

## 环境变量

| 变量名 | 说明 | 默认值 |
|--------|------|--------|
| `SESSION_SECRET` | 会话密钥 | - |
| `SQL_DSN` | 数据库连接（MySQL/PostgreSQL） | SQLite |
| `REDIS_CONN_STRING` | Redis 连接（可选，用于缓存） | - |

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
