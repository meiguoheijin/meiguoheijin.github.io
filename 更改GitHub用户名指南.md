# 更改 GitHub 用户名指南

## 📝 更改用户名：lindayajessica → meiguoheijin

### 第一步：在 GitHub 网站上更改用户名

1. **登录 GitHub**
   - 访问：https://github.com
   - 使用 `lindayajessica` 账号登录

2. **进入账号设置**
   - 点击右上角头像
   - 选择 "Settings"（设置）
   - 或直接访问：https://github.com/settings/account

3. **更改用户名**
   - 在 "Change username" 部分
   - 输入新用户名：`meiguoheijin`
   - 点击 "Change username" 按钮
   - 确认更改（可能需要输入密码）

### 第二步：了解更改后的影响

✅ **GitHub 会自动处理的事项：**
- 所有仓库 URL 会自动重定向（从旧用户名到新用户名）
- 现有的 Git 克隆、分支、推送仍然可以工作一段时间
- GitHub Pages 网站会自动更新

⚠️ **需要手动更新的事项：**
- 本地仓库的远程地址（建议更新）
- 任何引用旧用户名的文档或链接
- SSH 密钥不需要更改

### 第三步：更新本地 Git 配置

#### 1. 更新本地用户名配置

```bash
cd "/Users/jessica/Desktop/github/爱一帆"

# 更新当前项目的用户名
git config user.name "meiguoheijin"

# 查看确认
git config user.name
```

#### 2. 更新远程仓库地址

虽然 GitHub 会自动重定向，但建议更新为新地址：

**如果使用 HTTPS：**
```bash
# 查看当前远程地址
git remote -v

# 更新为新用户名
git remote set-url origin https://github.com/meiguoheijin/仓库名.git
```

**如果使用 SSH：**
```bash
# 查看当前远程地址
git remote -v

# 更新为新用户名
git remote set-url origin git@github.com:meiguoheijin/仓库名.git
```

#### 3. 验证更新

```bash
# 查看远程地址是否正确
git remote -v

# 测试连接
git fetch
```

### 第四步：更新 GitHub Pages 域名（如果使用根域名）

如果你创建了根域名仓库，需要：

1. **重命名仓库**
   - 旧仓库名：`lindayajessica.github.io`
   - 新仓库名：`meiguoheijin.github.io`

2. **操作步骤**
   - 访问仓库：https://github.com/lindayajessica/lindayajessica.github.io
   - 点击 "Settings"
   - 滚动到 "Danger Zone"
   - 点击 "Rename repository"
   - 输入新名称：`meiguoheijin.github.io`
   - 确认重命名

3. **更新本地远程地址**
   ```bash
   cd "/Users/jessica/Desktop/github/爱一帆"
   git remote set-url origin https://github.com/meiguoheijin/meiguoheijin.github.io.git
   ```

4. **新的网站地址**
   - 旧地址：`https://lindayajessica.github.io/`
   - 新地址：`https://meiguoheijin.github.io/`
   - GitHub 会自动从旧地址重定向到新地址

### 第五步：针对当前项目的完整配置

```bash
cd "/Users/jessica/Desktop/github/爱一帆"

# 1. 更新用户名和邮箱
git config user.name "meiguoheijin"
git config user.email "你的邮箱"  # 替换为实际邮箱

# 2. 如果要使用根域名，创建仓库：meiguoheijin.github.io
# 在 GitHub 网站上创建仓库后，更新远程地址：
git remote set-url origin https://github.com/meiguoheijin/meiguoheijin.github.io.git

# 3. 查看配置
git config user.name
git config user.email
git remote -v

# 4. 推送代码
git push -u origin main
```

## ⚠️ 重要注意事项

### 1. 用户名要求
- 只能包含字母、数字和连字符
- 不能以连字符开头或结尾
- 最长 39 个字符
- 用户名唯一，如果已被占用则无法使用

### 2. 更改限制
- GitHub 允许随时更改用户名
- 更改后，旧用户名会被释放，其他人可以使用
- 建议不要频繁更改用户名

### 3. 重定向时间
- GitHub 会保持重定向一段时间
- 但建议尽快更新所有引用旧用户名的地方

### 4. 影响范围
- 更改用户名会影响所有仓库的 URL
- 但不影响仓库内容、提交历史、Star、Fork 等

## 📋 检查清单

更改完成后，请检查：

- [ ] GitHub 网站上用户名已更改
- [ ] 本地 Git 配置已更新（`git config user.name`）
- [ ] 远程仓库地址已更新（`git remote -v`）
- [ ] 能够成功推送代码（`git push`）
- [ ] GitHub Pages 网站可以访问（如果使用）
- [ ] 仓库名已更新（如果使用根域名）

## 🚀 快速命令（更改用户名后执行）

```bash
cd "/Users/jessica/Desktop/github/爱一帆"

# 更新本地配置
git config user.name "meiguoheijin"
git config user.email "你的邮箱"

# 更新远程地址（根域名示例）
git remote set-url origin https://github.com/meiguoheijin/meiguoheijin.github.io.git

# 验证
git config user.name
git remote -v

# 推送代码
git push -u origin main
```

## 📞 参考资源

- [GitHub 官方文档：更改用户名](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-personal-account-settings/changing-your-github-username)
- [重命名仓库的影响](https://docs.github.com/en/repositories/creating-and-managing-repositories/renaming-a-repository)

