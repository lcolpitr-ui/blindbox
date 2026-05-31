# 随缘匣 - 盲盒抽卡 H5 网页版

一个纯粹的单页 H5 应用，部署到 GitHub Pages 后即可通过链接在微信群里分享使用。

**完全免费，无需认证，无需审核。**

## 功能

- 🎴 盲盒抽卡：点击抽取随机获得卡片（稀有/史诗/传奇）
- ✨ 炫酷动画：抖动、粒子爆发、翻转揭晓
- 📖 收藏系统：查看所有已抽取卡片，按稀有度筛选
- 💾 数据持久：抽到的卡片保存在浏览器本地，不会丢失
- 📤 微信分享：链接直接发到群里，群友点击即用
- 📱 手机适配：响应式设计，手机上体验最佳

## 一键部署到 GitHub Pages（免费）

### 步骤 1：创建 GitHub 仓库

1. 登录 [GitHub](https://github.com)（没有账号就注册一个，免费）
2. 点击右上角 `+` → `New repository`
3. 仓库名填 `blindbox`（或其他你喜欢的名字）
4. 选择 **Public**（公开）
5. 点击 `Create repository`

### 步骤 2：上传文件

在仓库页面点击 `uploading an existing file`，把这两个文件拖进去：

```
index.html
README.md
```

或者用 Git 命令：

```bash
cd h5-app
git init
git add index.html README.md
git commit -m "init"
git branch -M main
git remote add origin https://github.com/你的用户名/blindbox.git
git push -u origin main
```

### 步骤 3：开启 GitHub Pages

1. 进入仓库 → `Settings` → `Pages`
2. `Source` 选择 `Deploy from a branch`
3. `Branch` 选择 `main`，目录选 `/ (root)`
4. 点击 `Save`
5. 等 1-2 分钟，页面顶部会显示你的网址：
   ```
   https://你的用户名.github.io/blindbox
   ```

### 步骤 4：分享到微信群

把上面的网址直接发到微信群里，群友点击就能打开使用！

---

## 国内加速方案（可选）

GitHub Pages 在国内某些地区可能较慢，可以搭配以下免费方案：

### 方案 A：Gitee Pages（码云）

1. 注册 [Gitee](https://gitee.com) 账号
2. 导入 GitHub 仓库或新建仓库
3. 进入 `服务` → `Gitee Pages` → 开启
4. 获得国内访问更快的网址：`https://你的用户名.gitee.io/blindbox`

> ⚠️ Gitee Pages 需要实名认证，且免费版会自动加推广页脚

### 方案 B：Vercel（全球 CDN）

1. 注册 [Vercel](https://vercel.com)（用 GitHub 账号直接登录）
2. 导入你的 GitHub 仓库
3. 自动部署，获得 `https://xxx.vercel.app` 域名
4. Vercel 在国内有边缘节点，速度比 GitHub Pages 快

### 方案 C：Cloudflare Pages

1. 注册 [Cloudflare](https://pages.cloudflare.com)
2. 连接 GitHub 仓库，自动部署
3. 获得 `https://xxx.pages.dev` 域名

---

## 微信里怎么用

1. **分享链接**：把部署后的网址发到微信群
2. **点击打开**：群友在微信里直接点击链接，会在微信内置浏览器中打开
3. **收藏链接**：群友可以点右上角 `...` → `收藏`，方便以后打开
4. **浮窗**：在微信内置浏览器中点右上角 `...` → `浮窗`，可以随时切回来

> 微信内置浏览器完全支持这个网页的所有功能，包括动画效果。

---

## 自定义卡片

编辑 `index.html`，找到 `<script>` 标签里的 `appData.cardSeries` 对象：

```javascript
cardSeries: {
  ink: {
    name: '你的系列名',
    cards: [
      {
        id: 'card-001',
        name: '卡片名',
        image: '图片URL',
        rarity: 'rare',        // 'rare' | 'epic' | 'legendary'
        description: '描述',
        probability: 0.15      // 概率，所有卡片加起来=1
      },
      // ... 更多卡片
    ]
  }
}
```

修改后重新上传到 GitHub，GitHub Pages 会自动更新。

---

## 和微信小程序对比

| | H5 网页版 | 微信小程序 |
|---|---|---|
| 费用 | **完全免费** | 企业认证 300 元/年 |
| 审核 | **无需审核** | 需要提交审核 |
| 更新 | 即时生效 | 需审核（1-7天） |
| 分享 | 链接分享 | 小程序卡片分享 |
| 开发 | 标准 HTML/JS | WXML/WXSS 专用语法 |
| 微信能力 | 基础 | 完整（支付、订阅消息等） |
| 域名要求 | 无 | 需配置白名单 |

**结论**：你这个盲盒抽卡场景，H5 网页版完全够用。除非以后需要微信支付、消息推送等高级功能，再考虑迁移到小程序。
