# 度克设计 - 项目部署指南

## 项目概述
这是一个基于React 18、TypeScript和Tailwind CSS构建的现代室内设计展示网站。

## 环境要求
- Node.js 18.x 或更高版本
- npm 或 pnpm 包管理器

## 安装步骤

### 1. 下载项目代码
从GitHub仓库下载项目代码到本地

### 2. 安装依赖
```bash
# 使用npm
npm install

# 或使用pnpm
pnpm install
```

## 本地开发
```bash
# 启动开发服务器
npm run dev
# 或
pnpm dev

# 服务器将运行在 http://localhost:3000
```

## 构建项目
```bash
# 构建生产版本
npm run build
# 或
pnpm build

# 构建产物将生成在 dist/ 目录下
```

## 部署指南

### 使用GitHub和Netlify部署

#### 1. 准备GitHub仓库
1. 登录GitHub账号，创建新仓库
2. 上传项目文件到仓库（可通过GitHub网页界面直接上传）

#### 2. 配置Netlify
1. 登录Netlify账号，点击"New site from Git"
2. 选择GitHub，并授权访问你的仓库
3. 选择刚刚创建的仓库
4. 构建设置：
   - 构建命令: `npm run build` 或 `pnpm build`
   - 发布目录: `dist`
5. 点击"Deploy site"开始部署

## 常见问题排查

### 构建错误: 无法解析/src/main.tsx
这通常是由于构建路径配置不正确导致的。请确保:
1. package.json中的构建脚本正确
2. 没有修改vite.config.ts文件（该文件已锁定）

### 部署后页面空白
检查Netlify部署日志，常见原因:
1. 依赖安装失败 - 尝试在构建命令前添加`npm install`
2. 构建命令错误 - 确保使用正确的构建命令
3. 资源路径问题 - 确保index.html中的资源引用正确

### 路由问题
对于单页应用(SPA)，需要配置Netlify重定向:
1. 创建或修改netlify.toml文件
2. 添加以下内容:
```toml
[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

## 技术栈
- React 18
- TypeScript
- Tailwind CSS
- Vite
- Framer Motion (动画效果)
- React Router (路由管理)