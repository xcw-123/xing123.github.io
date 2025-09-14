# 项目部署指南

## Netlify部署步骤

1. **准备工作**
   - 确保项目已推送到GitHub仓库
   - 注册并登录Netlify账号

2. **部署配置**
   - 导入GitHub仓库
   - 构建命令: `pnpm install && pnpm build`
   - 发布目录: `dist`

3. **环境变量**
   - NODE_VERSION: 18
   - NPM_VERSION: 10
   - PNPM_VERSION: 8.15.6

4. **本地构建测试**
   ```bash
   pnpm install
   pnpm build
   ```
   确保本地能成功构建出dist目录

5. **常见问题解决**
   - 构建失败: 检查Node.js版本是否兼容
   - 依赖安装问题: 尝试删除node_modules后重新安装
   - 路由404问题: 确保Netlify重定向规则正确配置

## 部署优化建议
- 启用Netlify缓存以加快构建速度
- 配置分支预览以测试不同版本
- 设置部署通知以获取构建状态更新