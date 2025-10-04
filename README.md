# 📱 九宫格计数器 (PWA)

一个适配手机端的九宫格计数器网页小应用：  
- 手机屏幕下半部分是 1-9 九宫格按钮  
- 每次点击对应数字按钮，该数字的计数器加 1  
- 上半部分显示计数结果  
- 支持 **本地存储**（刷新后数据不丢失）  
- 支持 **导出/重置功能**  
- 支持 **PWA 安装**（添加到主屏幕，像原生应用一样使用）  
- 支持 **离线访问**（通过 Service Worker 缓存）

---

## 📂 文件结构

```
mobile-tile-counter/
├─ index.html              # 主网页（包含逻辑和 SW 注册）
├─ manifest.json           # PWA 应用清单
├─ sw.js                   # Service Worker 脚本（缓存优先 + 后台更新）
├─ assets/
│   └─ icon.png            # 应用图标 (512x512 PNG)
└─ .github/
   └─ workflows/
      └─ deploy.yml        # GitHub Actions 自动部署配置
```

---

## 🚀 本地运行

1. 克隆仓库到本地：
   ```bash
   git clone https://github.com/<你的用户名>/mobile-tile-counter.git
   cd mobile-tile-counter
   ```

2. 本地启动一个静态服务器（推荐 Python/Node 任意方式）：

   - 如果你有 Python3：
     ```bash
     python3 -m http.server 8080
     ```
     打开浏览器访问：`http://localhost:8080`

   - 或者用 Node.js (http-server)：
     ```bash
     npm install -g http-server
     http-server -p 8080
     ```
     然后访问：`http://localhost:8080`

> ⚠️ 注意：  
> Service Worker **必须在 HTTPS 环境下运行**。  
> `http://localhost` 是开发特例，可以直接测试。

---

## 🌍 部署到 GitHub Pages

1. 推送代码到 GitHub 仓库：
   ```bash
   git add .
   git commit -m "init project"
   git push origin main
   ```

2. GitHub Actions 会自动执行 `.github/workflows/deploy.yml` 脚本，生成并发布到 **gh-pages** 分支。

3. 打开 GitHub 仓库 → **Settings** → **Pages**，选择：
   - Source: `Deploy from a branch`
   - Branch: `gh-pages`

4. 保存后，稍等几分钟，就可以通过：
   ```
   https://<你的用户名>.github.io/mobile-tile-counter/
   ```
   访问到应用。

---

## 🛠️ 功能特性

- **九宫格输入**：点击数字按钮进行计数  
- **本地存储**：自动保存计数结果到 `localStorage`  
- **导出功能**：一键导出 `counts.json` 文件  
- **重置功能**：清空所有计数  
- **PWA 支持**：可以添加到主屏幕，像原生应用一样打开  
- **离线支持**：即使断网也能正常运行  
- **自动更新**：当检测到新版本，会提示用户刷新页面

---

## 📸 界面示例

（建议这里放一张手机截图）

---

## 📜 License

MIT License
