[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]

## 目录

- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
[[CONTENT]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]
- [[ITEM_8]]
- [[ITEM_9]]
- [[ITEM_10]]
- [[ITEM_11]]
- [[ITEM_12]]

## 功能特性

- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

## 快速开始

### 平台支持

- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]

### 前置要求

- [[ITEM_1]]
- [[ITEM_2]]

### 安装

[[CONTENT]]

```bash
pipx install tokdash
```

[[CONTENT]]

```bash
python3 -m pip install --user tokdash
```

### 首次运行

[[CONTENT]]

```bash
tokdash setup
```

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]

```bash
tokdash setup --auto --json
```

[[CONTENT]]

```bash
tokdash setup --dry-run
```

### 验证

```bash
tokdash doctor
```

[[CONTENT]]
[[CONTENT]]

### 更新或移除

```bash
tokdash update       # 升级受管运行时，并在可能时重启服务
tokdash uninstall    # 精确撤销 setup 创建的内容；默认保留使用历史
```

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]

[[CONTENT]]

```bash
pipx upgrade tokdash
# 或：python3 -m pip install --user -U tokdash
```

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]

```bash
# 先升级你接下来要运行的 tokdash 命令，例如：
python3 -m pip install --user -U tokdash
# 如果是 conda base 安装：
conda run -n base python -m pip install -U tokdash
tokdash setup --runtime venv --force
tokdash doctor
```

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]

### 远程访问

[[CONTENT]]

- [[ITEM_1]]
- [[ITEM_2]]

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]

### 前台运行备用方式

[[CONTENT]]

```bash
tokdash serve
```

[[CONTENT]]

[[CONTENT]]
[[CONTENT]]


### OpenClaw 摘要（定时报表）

[[CONTENT]]

#### 面向人类用户

[[CONTENT]]

```text
Install and configure scheduled Tokdash usage reports for OpenClaw by following the instructions here:
https://raw.githubusercontent.com/JingbiaoMei/Tokdash/main/docs/agents/openclaw_reporting/AGENTS.md

Or read the guide yourself, but seriously, let an agent do it.
```

#### 面向 LLM 代理

[[CONTENT]]

```bash
curl -s https://raw.githubusercontent.com/JingbiaoMei/Tokdash/main/docs/agents/openclaw_reporting/AGENTS.md
```

### 状态栏集成（Statusline integration）

[[CONTENT]]

[[CONTENT]]

- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]

[[CONTENT]]

[[CONTENT]]

[[CONTENT]]

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

## 配置

[[CONTENT]]

- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]
- [[ITEM_8]]
- [[ITEM_9]]

[[CONTENT]]

[[CONTENT]]

- [[ITEM_10]]
- [[ITEM_11]]
- [[ITEM_12]]
- [[ITEM_13]]
- [[ITEM_14]]
- [[ITEM_15]]

[[CONTENT]]

```bash
tokdash db status --pretty
tokdash db sync --pretty
tokdash db verify --verify-period today --pretty
tokdash db repair --dry-run --pretty
tokdash db resync --pretty
tokdash db watch --pretty
```

[[CONTENT]]

```bash
tokdash setup
# 当向导询问是否配置 Tailscale Serve 时，确认即可。
# Serve 成功后，setup 会打印准确的 https://...ts.net/tokdash 地址。
```

[[CONTENT]]

```bash
tailscale serve --bg --https=443 --set-path=/tokdash http://127.0.0.1:55423
```

[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]

## 隐私与安全

- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
- [[ITEM_4]]

### 额度跟踪（可选）

[[CONTENT]]

```bash
tokdash quota consent --codex-api on --claude-api on --antigravity-api on
tokdash quota consent --poll-interval 30      # 后台轮询周期：15、30、60 或 120 分钟
tokdash quota consent --enabled off           # 总开关：关闭全部额度跟踪
tokdash quota poll
tokdash quota show
```

[[CONTENT]]

[[CONTENT]]

[[CONTENT]]

[[CONTENT]]

[[CONTENT]]

## API（本地）

[[CONTENT]]

- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]

[[CONTENT]]

```bash
curl 'http://127.0.0.1:55423/api/usage?period=today'
```

[[CONTENT]]

## 费用精度说明

[[CONTENT]]

## 历史数据保留

[[CONTENT]]

- [[ITEM_1]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
- [[ITEM_2]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]

## 路线图

[[CONTENT]]

## 贡献 / 安全

- [[ITEM_1]]
- [[ITEM_2]]

## 项目结构

```text
tokdash/
├── main.py                 # 源码入口（python3 main.py）
├── tokdash                 # CLI 包装器（./tokdash serve）
├── src/
│   └── tokdash/
│       ├── cli.py
│       ├── api.py                # FastAPI 路由 / 应用
│       ├── compute.py            # 聚合 / 合并逻辑
│       ├── dateutil.py           # 共享的日期范围解析
│       ├── sessions.py           # 会话浏览器逻辑
│       ├── pricing.py            # PricingDatabase 封装
│       ├── assets.py             # 静态资源管理
│       ├── model_normalization.py
│       ├── pricing_db.json
│       ├── sources/
│       │   ├── openclaw.py       # OpenClaw 会话日志解析器
│       │   └── coding_tools.py   # 本地编程工具解析器
│       └── static/
│           ├── index.html        # 单页仪表盘
│           ├── theme-config.js   # 主题调色板 & 热力图颜色
│           └── themes.css        # 各主题 CSS 覆写
└── docs/                   # Onboarding 指南、API 文档、发布说明与 agent 提示词
```

## License

[[CONTENT]]
