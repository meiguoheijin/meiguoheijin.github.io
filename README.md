# 爱壹帆网站 - GitHub Pages 部署指南

这是一个静态网站项目，可以轻松部署到 GitHub Pages。

## 📋 部署步骤

### 方法一：通过 GitHub 网页界面部署（推荐新手）

1. **创建 GitHub 仓库**
   - 访问 [GitHub](https://github.com) 并登录
   - 点击右上角的 "+" 号，选择 "New repository"
   - 仓库名称建议使用：`aiyifan` 或 `yifan-website`
   - 选择 Public（公开）或 Private（私有）
   - **不要**勾选 "Initialize this repository with a README"
   - 点击 "Create repository"

2. **上传文件到 GitHub**
   - 在新建的仓库页面，点击 "uploading an existing file"
   - 将整个项目文件夹的所有文件拖拽上传
   - 或者点击 "choose your files" 选择文件
   - 上传完成后，点击 "Commit changes"

3. **启用 GitHub Pages**
   - 在仓库页面，点击 "Settings"（设置）
   - 在左侧菜单中找到 "Pages"
   - 在 "Source" 部分，选择 "Deploy from a branch"
   - Branch 选择 "main" 或 "master"，文件夹选择 "/ (root)"
   - 点击 "Save"
   - 等待几分钟，GitHub 会生成你的网站地址
   - 网站地址格式：`https://你的用户名.github.io/仓库名/`

### 方法二：通过 Git 命令行部署（推荐有经验的用户）

1. **初始化 Git 仓库**
   ```bash
   cd "/Users/jessica/Desktop/github/爱一帆"
   git init
   git add .
   git commit -m "Initial commit: 爱壹帆网站"
   ```

2. **连接到 GitHub 仓库**
   ```bash
   # 替换 YOUR_USERNAME 和 YOUR_REPO_NAME 为你的实际信息
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git branch -M main
   git push -u origin main
   ```

3. **启用 GitHub Pages**
   - 按照方法一的第3步操作

## 🔧 项目结构

```
爱一帆/
├── index.html          # 主页面
├── files/              # 资源文件目录
│   ├── style.9b4b7f3f.css  # 样式文件
│   ├── yfsp.jpg        # 图片资源
│   └── yfsp.png        # 图标文件
└── README.md           # 本文件
```

## 📝 注意事项

1. **文件路径**：确保所有资源文件的路径都是相对路径（如 `./files/xxx`），这样在 GitHub Pages 上才能正常显示

2. **仓库名称**：如果仓库名称包含中文字符，GitHub Pages 的 URL 可能会显示编码后的字符

3. **更新网站**：每次修改文件后，需要重新提交并推送到 GitHub，GitHub Pages 会自动更新（通常需要几分钟）

4. **自定义域名**（可选）：如果想使用自己的域名，可以在 GitHub Pages 设置中添加自定义域名

## 🚀 快速部署命令

如果你已经创建了 GitHub 仓库，可以使用以下命令快速部署：

```bash
cd "/Users/jessica/Desktop/github/爱一帆"
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git push -u origin main
```

记得将 `YOUR_USERNAME` 和 `YOUR_REPO_NAME` 替换为你的实际 GitHub 用户名和仓库名！

## 📞 需要帮助？

如果遇到问题，可以：
- 查看 [GitHub Pages 官方文档](https://docs.github.com/en/pages)
- 检查浏览器控制台是否有错误信息
- 确保所有文件都已正确上传到 GitHub

