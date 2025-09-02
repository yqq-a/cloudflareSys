# 📚 部署指南

## 🚀 快速部署步骤

### 1. 部署 Workers 后端

```bash
cd workers
npm install
npx wrangler login
npx wrangler secret put OPENAI_API_KEY
npm run deploy
```

### 2. 部署 Pages 前端

1. 在 [Cloudflare Dashboard](https://dash.cloudflare.com/) 创建 Pages 项目
2. 连接此 GitHub 仓库
3. 设置构建配置：
   - 构建命令: `cd pages && npm install && npm run build`
   - 输出目录: `pages/dist`

### 3. 获取 OpenAI API Key

1. 访问 [OpenAI Platform](https://platform.openai.com/)
2. 注册并创建 API Key
3. 在 Workers 中设置环境变量

## 🔧 本地开发

### Workers 开发
```bash
cd workers
npm run dev
```

### Pages 开发
```bash
cd pages
npm run dev
```

## 📝 配置说明

- 修改 `pages/src/components/AIChatPage.tsx` 中的 API 地址
- Workers 部署后会提供一个 `.workers.dev` 域名
- 将该域名配置到前端页面中

## 💰 成本估算

- Cloudflare Workers: 免费版每天 100,000 请求
- Cloudflare Pages: 完全免费
- OpenAI API: GPT-3.5-turbo 约 $0.002/1K tokens