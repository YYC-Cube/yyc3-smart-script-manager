# YYC³ 智能脚本生成和管理系统

> **版本**: v1.0.0 | **创建时间**: 2025-12-08 | **维护团队**: YYC3 AI Family

## 🎯 系统概述

YYC³智能脚本生成和管理系统是一个应用级的DevOps自动化平台，能够：

### 🚀 核心功能
- **智能脚本生成** - 基于应用类型自动生成标准脚本
- **配置管理** - 统一的配置文件和环境变量管理
- **远程执行** - 跨服务器的脚本部署和执行
- **服务集成** - 多服务应用的统一管理
- **监控告警** - 实时监控和智能告警系统
- **版本控制** - 脚本版本管理和回滚机制

### 📋 应用支持
- **Web应用** (Next.js, React, Vue)
- **API服务** (Node.js, Python FastAPI, Go)
- **数据库** (PostgreSQL, MySQL, Redis)
- **容器化** (Docker, Kubernetes)
- **云服务** (AWS, 阿里云, 腾讯云)

## 🏗️ 系统架构

```
┌─────────────────────────────────────────────────────┐
│                YYC³ 智能脚本管理平台              │
├─────────────────────────────────────────────────────┤
│  🎛️ Web管理界面                                    │
│  ├── 脚本生成向导  ├── 应用管理面板                          │
│  ├── 配置管理器    ├── 执行监控仪表板                        │
│  └── 告警中心      └── 版本控制系统                          │
└─────────────────────────────────────────────────────┘
                            │
┌─────────────────────────────────────────────────────┐
│                  🧠 智能引擎核心                    │
├─────────────────────────────────────────────────────┤
│  🔍 应用分析器  ├── 📝 脚本生成器                            │
│  │              ├── 🧪 配置管理器                            │
│  │              ├── 🌐 远程执行器                            │
│  │              └── 📊 监控收集器                            │
│  │                  │                                           │
│  └───────────────┘ └──────────────────────────────────────┘
        │                    │
┌─────────────────────┐ ┌──────────────────────────────────────┐
│  📚 脚本模板库        │ │  ⚙️ 配置仓库                    │
│  ├── Web应用模板      │ ├── 环境配置                       │
│  ├── API服务模板      │ ├── 服务配置                       │
│  ├── 数据库模板      │ ├── 部署配置                       │
│  └── 容器化模板      │ └── 安全配置                       │
└─────────────────────┘� └──────────────────────────────────────┘
                            │
┌─────────────────────────────────────────────────────┐
│  🌐 远程服务器集群      │  📊 监控告警系统                  │
│  ├── admin@0379.email │  ├── 实时状态监控                   │
│  ├── deploy@0379.world │  ├── 智能告警机制                   │
│  ├── database@nas.local│  ├── 日志聚合分析                   │
│  └── service@ecs.aliyun │  └── 性能指标统计                   │
└─────────────────────────────────────────────────────┘�
```

## 🚀 快速开始

### 1. 系统初始化
```bash
# 克隆系统
git clone https://github.com/YYC-Cube/yyc3-smart-script-manager.git
cd yyc3-smart-script-manager

# 或者
git clone git@github.com:YYC-Cube/yyc3-smart-script-manager.git
cd yyc3-smart-script-manager

# 安装依赖
npm install

# 初始化配置
npm run init
```

### 2. 创建第一个应用
```bash
# 创建Web应用配置
npm run create-app --type web --name my-website

# 生成标准脚本
npm run generate-scripts --app my-website

# 部署到远程服务器
npm run deploy --app my-website --server admin@0379.email
```

### 3. 管理应用
```bash
# 查看所有应用
npm run list-apps

# 查看应用详情
npm run show-app --name my-website

# 更新应用配置
npm run update-app --name my-website
```

## 📖 使用指南

### 创建应用配置

#### 1. 基础配置文件
```json
{
  "name": "my-website",
  "type": "web",
  "description": "公司官网",
  "version": "1.0.0",
  "author": "YYC3 Team",
  "repository": "https://github.com/company/my-website.git",
  "servers": [
    {
      "name": "production",
      "host": "admin@0379.email",
      "path": "/var/www/my-website",
      "nginx": true,
      "ssl": true
    },
    {
      "name": "staging",
      "host": "deploy@0379.world",
      "path": "/var/www/staging/my-website",
      "nginx": true,
      "ssl": false
    }
  ],
  "scripts": {
    "dev": "npm run dev",
    "build": "npm run build",
    "start": "pm2 start ecosystem.config.js",
    "deploy": "npm run build && rsync -av dist/ ${SERVER_PATH}",
    "rollback": "rsync -av ${BACKUP_PATH}/ dist/"
  }
}
```

#### 2. 高级配置
```json
{
  "name": "api-service",
  "type": "api",
  "runtime": "node",
  "ports": {
    "http": 3000,
    "ws": 3001
  },
  "database": {
    "postgresql": {
      "host": "localhost",
      "port": 5432,
      "database": "mydb",
      "user": "postgres",
      "password": "env:DB_PASSWORD"
    },
    "redis": {
      "host": "localhost",
      "port": 6379,
      "db": 0
    }
  },
  "monitoring": {
    "healthCheck": "/health",
    "metrics": "/metrics",
    "alerting": {
      "email": "admin@0379.email",
      "slack": "#alerts"
    }
  }
}
```

### 脚本生成功能

#### 自动生成的脚本类型

**1. 部署脚本 (deploy.sh)**
```bash
#!/bin/bash
# 自动生成的部署脚本 - my-website
# 创建时间: 2025-12-08 16:30:00
# 部署目标: admin@0379.email

set -e

# 配置变量
APP_NAME="my-website"
SERVER_USER="admin@0379.email"
SERVER_PATH="/var/www/my-website"
BACKUP_PATH="/var/backups/my-website"
REPO_URL="https://github.com/company/my-website.git"
BRANCH="main"

echo "🚀 开始部署 $APP_NAME 到 $SERVER_USER..."

# 检查服务器连接
ssh -o ConnectTimeout=10 $SERVER_USER "echo '✅ 服务器连接成功'"

# 创建备份
echo "💾 创建备份..."
ssh $SERVER_USER "sudo mkdir -p $BACKUP_PATH && sudo cp -r $SERVER_PATH $BACKUP_PATH/$(date +%Y%m%d_%H%M%S)"

# 拉取最新代码
echo "📥 拉取最新代码..."
git pull origin $BRANCH

# 构建应用
echo "🔨 构建应用..."
npm run build

# 上传文件
echo "📤 上传文件到服务器..."
rsync -avz --delete dist/ $SERVER_USER:$SERVER_PATH/

# 重启服务
echo "🔄 重启服务..."
ssh $SERVER_USER "cd $SERVER_PATH && pm2 restart ecosystem.config.js"

# 健康检查
echo "🏥 执行健康检查..."
sleep 5
curl -f $SERVER_URL/health || exit 1

echo "✅ 部署完成！"
echo "🌐 访问地址: $SERVER_URL"
```

**2. 监控脚本 (monitor.sh)**
```bash
#!/bin/bash
# 自动生成的监控脚本 - my-website
# 创建时间: 2025-12-08 16:30:00

APP_NAME="my-website"
SERVER_URL="https://0379.email"
HEALTH_ENDPOINT="$SERVER_URL/health"
ALERT_EMAIL="admin@0379.email"

while true; do
    # 健康检查
    if curl -f $HEALTH_ENDPOINT >/dev/null 2>&1; then
        echo "✅ $APP_NAME 健康检查通过 $(date)"
    else
        echo "❌ $APP_NAME 健康检查失败 $(date)"
        echo "📧 发送告警邮件..."
        echo "应用 $APP_NAME 健康检查失败，请立即检查！" | mail -s "🚨 $APP_NAME 健康检查告警" $ALERT_EMAIL
    fi

    sleep 30
done
```

**3. 备份脚本 (backup.sh)**
```bash
#!/bin/bash
# 自动生成的备份脚本 - my-website
# 创建时间: 2025-12-08 16:30:00

APP_NAME="my-website"
SERVER_USER="admin@0379.email"
APP_PATH="/var/www/my-website"
BACKUP_ROOT="/var/backups"
RETENTION_DAYS=7

TIMESTAMP=$(date +%Y%m%d_%H%M%S)
BACKUP_DIR="$BACKUP_ROOT/$APP_NAME/$TIMESTAMP"

echo "💾 开始备份 $APP_NAME..."

# 创建备份目录
ssh $SERVER_USER "mkdir -p $BACKUP_DIR"

# 备份应用文件
echo "📦 备份应用文件..."
ssh $SERVER_USER "rsync -av $APP_PATH/ $BACKUP_DIR/app/"

# 备份数据库
echo "🗄️ 备份数据库..."
ssh $SERVER_USER "pg_dump mydb > $BACKUP_DIR/database.sql"

# 备份配置文件
echo "⚙️ 备份配置文件..."
ssh $SERVER_USER "cp -r $APP_PATH/.env* $BACKUP_DIR/config/"

# 清理过期备份
echo "🧹 清理过期备份..."
ssh $SERVER_USER "find $BACKUP_ROOT -type d -mtime +$RETENTION_DAYS -exec rm -rf {} \;"

echo "✅ 备份完成: $BACKUP_DIR"
```

### 远程执行功能

#### 1. 批量服务器管理
```bash
# 查看所有服务器状态
npm run list-servers

# 批量部署应用
npm run batch-deploy --apps "website,api,database"

# 批量健康检查
npm run health-check --servers "production,staging"
```

#### 2. 实时监控面板
```bash
# 启动监控面板
npm run monitor-panel

# 查看实时状态
npm run status-dashboard

# 启动告警系统
npm run alert-system
```

## 🔧 高级功能

### 1. 智能故障诊断
- **自动问题检测** - 基于日志和指标的智能分析
- **故障自动修复** - 常见问题的自动修复机制
- **智能回滚** - 自动检测并安全回滚

### 2. 性能优化
- **资源监控** - CPU、内存、磁盘、网络实时监控
- **自动扩容** - 基于负载的自动扩缩容
- **性能调优** - 自动性能分析和优化建议

### 3. 安全管理
- **访问控制** - 基于角色的权限管理
- **安全扫描** - 代码安全漏洞扫描
- **加密传输** - 所有远程操作使用加密传输

### 4. 团队协作
- **多人协作** - 团队成员权限管理
- **审批流程** - 部署和发布审批工作流
- **知识库** - 最佳实践和故障解决方案库

## 📱 监控和告警

### 1. 实时监控指标
- **服务可用性** - 响应时间、错误率
- **资源使用率** - CPU、内存、磁盘、网络
- **业务指标** - 用户访问量、交易量、转化率

### 2. 智能告警机制
- **阈值告警** - 基于阈值的自动告警
- **异常检测** - 基于机器学习的异常检测
- **告警收敛** - 智能告警聚合和降噪

### 3. 可视化仪表板
- **总览仪表板** - 所有应用的总体状态
- **详情仪表板** - 单个应用的详细信息
- **趋势分析** - 历史数据和趋势分析

## 🔧 API接口

### 核心API接口

```bash
# 应用管理
POST /api/apps                    # 创建应用
GET  /api/apps                   # 获取应用列表
GET  /api/apps/:id               # 获取应用详情
PUT  /api/apps/:id               # 更新应用配置
DELETE /api/apps/:id            # 删除应用

# 脚本管理
POST /api/scripts/generate         # 生成脚本
GET  /api/scripts/:id              # 获取脚本内容
PUT  /api/scripts/:id              # 更新脚本
POST /api/scripts/:id/execute     # 执行脚本

# 部署管理
POST /api/deploy                  # 部署应用
POST /api/deploy/:id/rollback      # 回滚应用
GET  /api/deploy/status          # 获取部署状态

# 监控管理
GET  /api/monitor/apps           # 获取应用监控状态
GET  /api/monitor/servers        # 获取服务器监控状态
GET  /api/alerts                 # 获取告警列表
POST /api/alerts/acknowledge      # 确认告警
```

### API使用示例

```javascript
// 创建应用
const response = await fetch('/api/apps', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    name: 'my-api-service',
    type: 'api',
    runtime: 'node',
    servers: [
      {
        name: 'production',
        host: 'admin@0379.email',
        path: '/var/www/my-api'
      }
    ]
  })
});

// 部署应用
const deployResponse = await fetch('/api/deploy', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    appId: 'app-123',
    server: 'production'
  })
});
```

## 🚀 部署指南

### 1. 开发环境部署
```bash
# 克隆项目
git clone https://github.com/YYC-Cube/yyc3-smart-script-manager.git
cd yyc3-smart-script-manager

# 安装依赖
npm install

# 配置环境变量
cp .env.example .env

# 初始化数据库
npm run init-db

# 启动开发服务器
npm run dev
```

### 2. 生产环境部署
```bash
# 构建生产版本
npm run build

# 配置Nginx
sudo cp config/nginx.conf /etc/nginx/sites-available/yyc3-script-manager

# 启动服务
sudo systemctl start yyc3-script-manager
sudo systemctl enable yyc3-script-manager
```

### 3. Docker部署
```bash
# 构建Docker镜像
docker build -t yyc3-script-manager .

# 运行容器
docker run -d \
  --name yyc3-script-manager \
  -p 3000:3000 \
  -v $(pwd)/config:/app/config \
  -v $(pwd)/logs:/app/logs \
  yyc3-script-manager
```

### 4. Kubernetes部署
```bash
# 应用Kubernetes配置
kubectl apply -f k8s/deployment.yaml

# 检查部署状态
kubectl get pods -n yyc3-system
```

## 📚 文档和教程

### 开发文档
- [API参考](./docs/api-reference.md)
- [插件开发](./docs/plugin-development.md)
- [配置参考](./docs/configuration-reference.md)
- [故障排除](./docs/troubleshooting.md)

### 用户指南
- [快速入门](./guides/quick-start.md)
- [应用配置](./guides/app-configuration.md)
- [脚本管理](./guides/script-management.md)
- [监控设置](./guides/monitoring-setup.md)

### 最佳实践
- [安全配置](./best-practices/security.md)
- [性能优化](./best-practices/performance.md)
- [故障恢复](./best-practices/disaster-recovery.md)
- [团队协作](./best-practices/team-collaboration.md)

## 🤝 社区和支持

### 贡献指南
- [贡献代码](./contributing/guidelines.md)
- [报告问题](./contributing/report-issues.md)
- [功能建议](./contributing/feature-requests.md)
- [文档改进](./contributing/documentation.md)

### 联系方式
- **GitHub**: https://github.com/YYC-Cube/yyc3-smart-script-manager
- **邮箱**: support@yyc3.com
- **文档**: https://docs.yyc3.com/smart-script-manager
- **社区**: https://community.yyc3.com

### 技术支持
- **论坛**: https://forum.yyc3.com
- **博客**: https://blog.yyc3.com
- **视频教程**: https://video.yyc3.com
- **在线课程**: https://learn.yyc3.com

## 📄 许可证

本项目采用 MIT 许可证，详情请查看 [LICENSE](LICENSE) 文件。

---

<div align="center">

**[⬆️ 回到顶部](#yyc³-智能脚本生成和管理系统)**

Made with ❤️ by YYC3 AI Family Team

**言启象限，语枢智能** 🚀

</div>