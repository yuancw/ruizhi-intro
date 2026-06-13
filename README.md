# 0013 · 公司项目介绍（四川锐志）

## 1. 一句话目标
把 `四川锐志(4).pptx` 里的内容做成一页暗金色系、大气的公司介绍网页。

## 2. 状态
**已部署** ✓

- 🌐 在线：https://ruizhi-intro.pages.dev
- 📦 源码：https://github.com/yuancw/ruizhi-intro
- ☁️ 平台：Cloudflare Pages（Git 自动部署）

## 3. 关键文件 / 目录
- `index.html` — 单文件站点（内联 CSS + JS，无外部依赖）
- `assets/` — 精选缩图（62 张，共 ~11 MB）
  - `assets/brand/` — logo 与辅助图形
  - `assets/cover/` — 封面图
  - `assets/cases/drama/` — 剧目多媒体（6 部剧目）
  - `assets/cases/performance/` — 大型开闭幕式 / 文旅演出（10 项）
  - `assets/cases/tech/` — 球幕 / 折角 / IP 3D 技术演示
  - `assets/cases/tv/` — 电视包装
  - `assets/cases/promo/` — 形象宣传片
  - `assets/honor/` — 荣誉墙
- `work/` — 原始 PPTX 解包 + 提取脚本（可清理）

## 4. 设计要点
- 暗金配色：底色 `#0b0b0d`，金色 `#c9a96e`，高亮 `#e8c887`
- 字体：思源宋体 + 思源黑体（Google Fonts）
- 2 级目录：案例展示页用 Tab 切换 4 大类（剧目 / 演出 / 技术 / 影像），每类下展开具体案例
- 动画：滚动渐入、Tab 淡入、Hero 文字渐显、顶部进度条、计数递增、悬停浮起

## 5. 选图策略（避坑）
- 已剔除所有 `._*` 元数据文件
- 章节页装饰图（slide 1/2/3/6/8/12）不取
- 城市鸟瞰/开幕式超大全景尽量少取，每大型演出 case 取 2 张代表图
- 重复元素（如 `image10.jpeg` 装饰小条）剔除

## 6. 下一步 TODO
1. 绑自定义域名（如果有）
2. 接 Cloudflare Analytics 看访问数据
3. 根据客户反馈调整文案 / 配图

## 7. 关联
- 源文件：`/Volumes/Macbot/Codex202606/0013公司项目介绍/四川锐志(4).pptx`
- 全局文档：0001 §4 项目索引（待补本条）· 0003 L003 上下文超限教训
