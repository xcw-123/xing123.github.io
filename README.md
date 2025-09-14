# 项目部署指南：使用GitHub和Netlify（小白友好版）

## 准备工作
在开始之前，请确保您已经注册了以下账号：
- [GitHub账号](https://github.com/signup)（免费）
- [Netlify账号](https://app.netlify.com/signup)（免费，可使用GitHub账号直接登录）

## 第一步：在GitHub上创建新仓库

1. 登录您的GitHub账号
2. 点击右上角的"+"图标，选择"New repository"
3. 填写仓库信息：
   - Repository name: 输入仓库名称（例如"my-design-project"）
   - Description: 可选，输入简短描述
   - 选择"Public"（公开仓库，免费）
   - 不要勾选"Initialize this repository with a README"
   - 点击"Create repository"按钮

## 第二步：通过GitHub网页界面上传项目文件

1. 在新创建的仓库页面，您会看到"Quick setup"部分
2. 点击"uploading an existing file"链接
3. 点击"Choose your files"按钮，然后选择您电脑上下载的项目文件夹中的所有文件
   > **注意**：请确保选择所有项目文件和文件夹，包括隐藏文件
4. 拉到页面底部，在"Commit changes"部分：
   - 填写"Add files via upload"作为提交信息
   - 点击"Commit changes"按钮

## 第三步：在Netlify上部署项目

1. 登录您的Netlify账号（可使用GitHub账号直接授权登录）
2. 点击"Add new site"按钮，然后选择"Import an existing project"
3. 在"Where is your site hosted?"下选择"GitHub"
4. 您可能需要授权Netlify访问您的GitHub账号
5. 在仓库列表中找到并选择您刚刚创建的仓库
6. 在"Build settings"页面，设置以下选项：
   - Build command: `npm run build`
   - Publish directory: `dist`
   - 点击"Show advanced"，然后点击"New variable"添加：
     - Key: `NODE_VERSION`
     - Value: `18`
7. 点击"Deploy site"按钮

## 第四步：等待部署完成并访问您的网站

1. Netlify会开始部署您的项目，这可能需要1-2分钟
2. 部署完成后，您会看到"Site is live"的提示
3. 点击生成的随机域名（类似"xxxxxx.netlify.app"）即可访问您的网站

## 第五步：自定义域名（可选）

如果您想使用自己的域名，可以：
1. 在项目部署页面点击"Domain settings"
2. 点击"Add custom domain"并按照提示操作
3. 这一步可能需要在您的域名提供商处进行DNS设置，对于新手可以暂时跳过

## 常见问题解决

### 部署失败怎么办？
1. 检查Build command和Publish directory是否正确设置
2. 确保添加了NODE_VERSION环境变量
3. 点击部署日志查看具体错误信息
4. 可以尝试点击"Trigger deploy" -> "Deploy site"重新部署

### 网站显示空白或样式错乱？
1. 检查浏览器控制台是否有错误（按F12打开开发者工具）
2. 确保项目文件已全部上传到GitHub
3. 重新部署项目

### 如何更新网站内容？
1. 回到GitHub仓库页面
2. 找到需要更新的文件并点击
3. 点击右上角的铅笔图标进行编辑
4. 编辑完成后，拉到页面底部点击"Commit changes"
5. Netlify会自动检测到变化并重新部署您的网站（可能需要几分钟）

恭喜！您已经成功通过GitHub网页界面部署了您的项目。如有任何问题，请查看Netlify的[官方文档](https://docs.netlify.com/)或在GitHub上提交Issue。