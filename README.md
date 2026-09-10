# Cooliang iMail 官网

纯静态网站，不需要 npm 安装、构建步骤、数据库或邮箱凭据。

独立项目目录：`D:\code\imail-website`，与 iMail 应用仓库分开管理。

官网源码仓库：https://github.com/cooliang101/imail-website

## 文件

- `index.html`：产品首页
- `privacy.html`：隐私政策
- `terms.html`：服务条款
- `site.css`：响应式样式
- `logo.png`：项目现有图标

目前是待维护者审阅的内容草稿，尚未部署。隐私政策涵盖桌面本地、自托管、云端翻译和 API / MCP 数据边界；上线前请确认这些说明与你实际提供的版本及运营方式相符。

## 放入独立 GitHub 仓库

将以上五个网站文件放在新仓库根目录。此 README 可随仓库保留；不要把 iMail 运行数据、数据库、日志、master.key 或 OAuth 配置上传到官网仓库。

## Cloudflare Pages 部署

1. Workers & Pages 中创建 Pages 项目，连接该 GitHub 仓库。
2. Framework preset 选 None。
3. 网站文件在独立仓库根目录时：Root directory 留空，Build command 填 `exit 0`，Build output directory 填 `.`。
4. 部署完成后，用实际分配的 HTTPS 地址检查首页、`/privacy.html` 和 `/terms.html` 均可公开访问。

也可在 Cloudflare Pages 使用 Direct Upload，上传打包后的五个网站文件；Direct Upload 项目后续不能直接切换为 Git 集成，若希望自动发布，优先使用 Git 集成。

## Google OAuth 回填

品牌名称：`Cooliang iMail`。

设实际部署地址为 `https://你的站点域名`：

- 应用首页：`https://你的站点域名/`
- 应用隐私权政策链接：`https://你的站点域名/privacy.html`
- 应用服务条款链接：`https://你的站点域名/terms.html`
- 授权网域：填写 Google 接受的顶级私有域名，不带协议、路径或端口。自有域名下的子站一般填可注册主域。

不要把这里的示例文字直接复制到 Google 表单。`pages.dev` 免费地址能否用于该项目的域名/品牌验证需按实际控制台结果确认；品牌验证可能要求通过 Google Search Console 证明所有权。网站部署不代表 Google 已批准发布或验证。

支持与开发者联系邮箱沿用 Google 项目当前设置。Google 品牌页中的图标仍需另行上传。

## 本地预览

在本目录运行 `python -m http.server 4311 --bind 127.0.0.1`，访问 `http://127.0.0.1:4311/`。
