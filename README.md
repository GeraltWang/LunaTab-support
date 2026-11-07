# LunaTab 隐私与支持

LunaTab 是用于管理书签、文件夹和小组件的新标签页扩展。本仓库用于发布隐私政策并接收支持问题，由 [GeraltWang](https://github.com/GeraltWang) 维护。

- [阅读隐私政策](https://geraltwang.github.io/LunaTab-support/)
- [Read the privacy policy in English](https://geraltwang.github.io/LunaTab-support/privacy-en.html)
- [提交支持或隐私问题](https://github.com/GeraltWang/LunaTab-support/issues)

GitHub Issues 是公开的。请仅描述问题和请求类型，不要提交密码、联系方式、私人网址或完整备份；需要发送私人信息时，请先询问私密联系渠道。

政策网页与扩展内政策来自同一份正文。工作区默认保存在本机；图标会从来源网站加载；网页搜索使用用户所选的 Google、Bing 或百度，引擎偏好随工作区保存、备份和同步；提交的关键词发送到相应搜索服务；WebDAV 备份和同步仅在用户选择连接后启用。

LunaTab is a new-tab workspace for Bookmarks, Folders and Widgets, maintained by [GeraltWang](https://github.com/GeraltWang). [Get support or submit a privacy request](https://github.com/GeraltWang/LunaTab-support/issues). Issues are public: do not post passwords, contact details, private URLs or complete backups. Ask for a private contact channel before sharing private information.

## 构建与本地预览 / Build and preview

`public/privacy.html` 和 `public/privacy-en.html` 分别是中英文正文的唯一来源，共用 `public/privacy.css`。扩展构建直接打包这些文件；网站构建复制相同文件，不另行维护译文。

```sh
pnpm build
pnpm privacy:site
python3 -m http.server 4173 --directory .output/privacy-site
```

- 可部署目录 / Deployable directory: `.output/privacy-site/`（包含 HTML、CSS、README 和 `.nojekyll`）。
- 中文原地址 / Existing Chinese URL: `https://geraltwang.github.io/LunaTab-support/` → `index.html`；`privacy.html` 使用相同中文正文。
- 英文目标地址 / English target URL: `https://geraltwang.github.io/LunaTab-support/privacy-en.html`。
- 本地预览 / Local preview: `http://localhost:4173/`、`http://localhost:4173/privacy.html`、`http://localhost:4173/privacy-en.html`。
- 扩展内 / In the extension: `/privacy.html`（中文）、`/privacy-en.html`（English）。关于页按当前界面语言选择入口；政策页面上的语言链接只切换阅读语言，不修改界面语言偏好。

Both languages work offline in the built extension and use identical HTML in the website artifact. Deploy the **entire** `.output/privacy-site/` directory, including `privacy.css`, to the support repository’s GitHub Pages site. The existing Chinese root URL stays unchanged. Website deployment and store submission are separate actions; building does not publish either.
