# 爱壹帆网站 - GitHub Pages 部署指南

这是一个静态网站项目，可以轻松部署到 GitHub Pages。

## 🌐 GitHub Pages 域名规则

GitHub Pages 有两种域名格式：

### 格式一：根域名（推荐）
- **仓库名称**：`你的用户名.github.io`（例如：`jscpython.github.io`）
- **网站地址**：`https://你的用户名.github.io/`（根域名，更简洁）
- **示例**：`https://jscpython.github.io/`

### 格式二：子路径域名
- **仓库名称**：任意名称（例如：`hamer`、`aiyifan`）
- **网站地址**：`https://你的用户名.github.io/仓库名/`（包含仓库名）
- **示例**：`https://jscpython.github.io/hamer/`

**建议**：如果想获得更简洁的域名（如 `https://yfsptv-io.github.io/`），请创建名为 `你的用户名.github.io` 的仓库。

## 📋 部署步骤

### 方法一：通过 GitHub 网页界面部署（推荐新手）

1. **创建 GitHub 仓库**
   - 访问 [GitHub](https://github.com) 并登录
   - 点击右上角的 "+" 号，选择 "New repository"
   - **仓库名称选择**：
     - 想要根域名（`https://用户名.github.io/`）：仓库名必须是 `你的用户名.github.io`（例如：`jscpython.github.io`）
     - 想要子路径域名（`https://用户名.github.io/仓库名/`）：可以使用任意名称（例如：`hamer`、`aiyifan`）
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
   - 网站地址：
     - 如果仓库名是 `用户名.github.io`：`https://你的用户名.github.io/`
     - 如果仓库名是其他名称：`https://你的用户名.github.io/仓库名/`

### 方法二：通过 Git 命令行部署（推荐有经验的用户）

**前提条件**：确保你已经创建了 GitHub 仓库（例如：`hamer`）

1. **初始化 Git 仓库并提交代码**
   ```bash
   cd "/Users/jessica/Desktop/github/爱一帆"
   git init
   git add .
   git commit -m "Initial commit: 爱壹帆网站"
   ```

2. **连接到 GitHub 仓库**
   ```bash
   # 替换 YOUR_USERNAME 和 YOUR_REPO_NAME 为你的实际信息
   # 例如：git remote add origin https://github.com/jscpython/hamer.git
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git branch -M main
   ```

3. **推送代码到 GitHub（需要身份验证）**
   
   推送代码时，GitHub 会要求身份验证。有两种方式：

   **方式 A：使用 HTTPS + 个人访问令牌（推荐）**
   
   1. 创建个人访问令牌：
      - 访问：https://github.com/settings/tokens
      - 点击 "Generate new token" → "Generate new token (classic)"
      - 给令牌起个名字（如：`hamer-deploy`）
      - 勾选 `repo` 权限（包含所有仓库权限）
      - 点击 "Generate token"
      - **重要**：复制生成的令牌（只显示一次，请妥善保存）
   
   2. 推送代码：
      ```bash
      git push -u origin main
      ```
      - 用户名：输入你的 GitHub 用户名
      - 密码：**粘贴个人访问令牌**（不是 GitHub 密码）
   
   **方式 B：使用 SSH（如果已配置 SSH 密钥）**
   
   1. 如果使用 SSH，先更改远程地址：
      ```bash
      git remote set-url origin git@github.com:YOUR_USERNAME/YOUR_REPO_NAME.git
      ```
   
   2. 推送代码：
      ```bash
      git push -u origin main
      ```

4. **启用 GitHub Pages**
   - 访问你的仓库页面：`https://github.com/YOUR_USERNAME/YOUR_REPO_NAME`
   - 点击 "Settings"（设置）
   - 在左侧菜单中找到 "Pages"
   - 在 "Source" 部分：
     - 选择 "Deploy from a branch"
     - Branch 选择 "main"
     - Folder 选择 "/ (root)"
   - 点击 "Save"
   - 等待 1-2 分钟，GitHub 会生成你的网站地址
   - 网站地址：
     - 如果仓库名是 `用户名.github.io`：`https://YOUR_USERNAME.github.io/`
     - 如果仓库名是其他名称：`https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`
   - 示例：
     - 根域名：`https://jscpython.github.io/`（仓库名必须是 `jscpython.github.io`）
     - 子路径：`https://jscpython.github.io/hamer/`（仓库名是 `hamer`）

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

3. **身份验证**：
   - GitHub 已不再支持使用密码推送代码
   - 必须使用个人访问令牌（Personal Access Token）或 SSH 密钥
   - 个人访问令牌创建后只显示一次，请妥善保存

4. **更新网站**：每次修改文件后，需要重新提交并推送到 GitHub：
   ```bash
   git add .
   git commit -m "更新说明"
   git push
   ```
   GitHub Pages 会自动更新（通常需要 1-2 分钟）

5. **自定义域名**（可选）：如果想使用自己的域名，可以在 GitHub Pages 设置中添加自定义域名

6. **检查部署状态**：在仓库的 "Actions" 标签页可以查看部署状态和日志

## 🚀 快速部署命令

### 示例一：使用根域名（仓库名：jscpython.github.io）

如果你想获得 `https://jscpython.github.io/` 这样的根域名：

```bash
# 1. 进入项目目录
cd "/Users/jessica/Desktop/github/爱一帆"

# 2. 初始化并提交代码（如果还没做）
git init
git add .
git commit -m "Initial commit: 爱壹帆网站"
git branch -M main

# 3. 连接到 GitHub 仓库（仓库名必须是：用户名.github.io）
git remote add origin https://github.com/jscpython/jscpython.github.io.git

# 4. 推送代码（需要身份验证）
git push -u origin main
# 推送时会要求输入用户名和密码
# 用户名：jscpython
# 密码：使用个人访问令牌（不是 GitHub 密码）
```

### 示例二：使用子路径域名（仓库名：hamer）

如果你想使用 `https://jscpython.github.io/hamer/` 这样的子路径域名：

```bash
# 1. 进入项目目录
cd "/Users/jessica/Desktop/github/爱一帆"

# 2. 初始化并提交代码（如果还没做）
git init
git add .
git commit -m "Initial commit: 爱壹帆网站"
git branch -M main

# 3. 连接到 GitHub 仓库（仓库名可以是任意名称）
git remote add origin https://github.com/jscpython/hamer.git

# 4. 推送代码（需要身份验证）
git push -u origin main
# 推送时会要求输入用户名和密码
# 用户名：jscpython
# 密码：使用个人访问令牌（不是 GitHub 密码）
```

**重要提示**：
- 将 `jscpython` 替换为你的实际 GitHub 用户名
- 想要根域名，仓库名必须是 `你的用户名.github.io`
- 推送时需要个人访问令牌，不是 GitHub 密码
- 如果遇到身份验证问题，参考上面的"方式 A：使用 HTTPS + 个人访问令牌"

## 📞 需要帮助？

如果遇到问题，可以：
- 查看 [GitHub Pages 官方文档](https://docs.github.com/en/pages)
- 检查浏览器控制台是否有错误信息
- 确保所有文件都已正确上传到 GitHub

