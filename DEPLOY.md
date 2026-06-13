# 部署到 Cloudflare Pages

## 一次性配置（5 分钟）

1. 注册 Cloudflare 账号：https://dash.cloudflare.com/sign-up
2. 进入 **Workers 和 Pages** → **Create application** → **Pages** → **Connect to Git**
3. 授权 Cloudflare 访问你的 GitHub/GitLab 账号，选本仓库
4. **构建设置**：
   - **Framework preset**: `None`
   - **Build command**: *(留空)*
   - **Build output directory**: `/` （仓库根，因为 index.html 在根）
   - **Root directory**: *(留空)*
5. 点 **Save and Deploy**，第一次部署约 30 秒
6. 完成后会得到 `你的项目.pages.dev` 子域名（如 `ruizhi.pages.dev`）

## 后续更新

```bash
git add .
git commit -m "更新内容"
git push
```
Cloudflare 自动检测 push，1 分钟内重新部署。

## 绑定自定义域名

**前提**：你已有域名（如 `sichuanruizhi.com`），且 Cloudflare 是该域名的 DNS 服务商。

1. Cloudflare Pages 项目页 → **Custom domains** → **Set up a custom domain**
2. 输入根域名 `sichuanruizhi.com` 或子域名 `www.sichuanruizhi.com`
3. Cloudflare 自动加 CNAME 记录，等待几分钟生效
4. 自动签发 SSL 证书，HTTPS 开箱即用

如果域名 DNS 不在 Cloudflare：在域名注册商处加一条 CNAME 指向 `你的项目.pages.dev`。

## 路由 / 缓存策略

- 仓库根的 `_headers` 文件已配置：`/assets/*` 永久缓存 1 年，其他资源默认 + 安全头
- 仓库根的 `_redirects` 文件已配置 301 重定向
- 详细规则见 Cloudflare 文档：https://developers.cloudflare.com/pages/configuration/headers/

## 故障排查

| 现象 | 处理 |
|---|---|
| 部署失败：Build failed | Build command 必须留空；Output dir 必须是 `/` |
| 中文文件名乱码 | 检查 git 是否配置 `core.quotepath false` |
| 改文件没生效 | 看 Pages → Deployments → 最近一次是否绿色 |
| 自定义域名 404 | DNS 记录类型必须是 CNAME，不是 A 记录 |

## 监控

- 实时访问：https://dash.cloudflare.com → Analytics → Pages
- 每月免费额度：不限请求数 / 不限带宽 / 500 次部署 / 100 个自定义域名
