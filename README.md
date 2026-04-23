# 静态站点（GitHub Pages）

本目录为可独立部署的纯静态页面，与 PHP / 迅睿 CMS 无关。

## 本地预览

用浏览器直接打开 `index.html`，或使用任意静态服务器（例如 VS Code Live Server），根目录选 **`docs`**。

## 发布到 GitHub Pages

1. 将 **`docs` 目录** 提交到仓库（可与 PHP 项目同库，也可单独建库并把 `docs` 内文件拷到仓库根目录）。
2. 打开 GitHub：**Settings → Pages**。
3. **Build and deployment**：Source 选 **Deploy from a branch**；Branch 选 **main**（或你的默认分支），文件夹选 **`/docs`**，保存。
4. 等待 1～2 分钟后访问：  
   **`https://<你的用户名>.github.io/<仓库名>/`**

若使用 **User/Organization 站点**（仓库名必须为 `<用户名>.github.io`），请把本目录**内的文件**放到该仓库**根目录**（不要嵌套 `docs` 子文件夹），并在 Pages 设置里选 **root**。

## 资源文件

| 文件 | 说明 |
|------|------|
| `assets/logo.png` | 站点 Logo；缺失时页眉会显示文字品牌名。 |
| `首页图.jpg` | 首屏大图；放在与 `index.html` 同级；缺失时仅渐变背景。 |

## 与本地 `public` 同步

在仓库根目录执行（Windows PowerShell）：

```powershell
.\scripts\sync-static-to-docs.ps1
```

若修改了 CMS 模板，请先执行 `cd public; node _build-static-index.mjs` 再运行上述脚本。
