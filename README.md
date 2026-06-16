# ALPHA VAULT · 投研档案库

把每一条 alpha 钉在纸上 —— 按日期归档，一页一论点，不再随手丢失。
线上：`https://alpha-vault.pages.dev`（Cloudflare Pages，连上本仓库后每次 `git push` 自动上线）。

## 结构

```
alpha-vault/
├── index.html          ← 整合页（招牌 + 头框 banner + 按日期的卷宗卡片）
├── TEMPLATE.html       ← 新研究页的起手模板（已带返回导航 + 配色 + 字体）
├── assets/             ← 以后放共享图片
└── r/                  ← 每一份研究各占一个文件夹
    └── 2026-06-14-nadella-ecosystem/
        └── index.html  ← 线上地址 /r/2026-06-14-nadella-ecosystem/
```

命名规则：文件夹用 `YYYY-MM-DD-英文短题`，全小写、连字符分隔。这样列表天然按日期排序，URL 也干净。

## 加一篇新研究（两步）

1. **建页**：复制 `TEMPLATE.html` 到 `r/<日期-短题>/index.html`，填进你的论点、配图、标的。
2. **挂卡**：打开 `index.html`，在对应日期分组里复制一张 `<a class="dossier">…</a>` 卡片，改：
   - `href` → 新文件夹路径
   - `No.0xx` 编号、`2026.xx.xx` 日期、`X 长文解读` 类型标签
   - 封面 SVG（可换成该研究的专属示意图）、标题、`dsum` 一句话「研究了什么」、`dtick` 标的
   - 分组头部 `<span class="ct">N 篇</span>` 计数 +1；新月份就再复制一个 `.group` 块

> 以后篇数多了，再启用顶部「按板块」那一栏（现在是 soon 占位）。

## 设计语言（house style，保持一致）

- 配色：纸 `#E7E8E3` / 墨 `#1B1D1B` / 墨绿 `#15543A`，护眼亮色，别上深色。
- 字体：标题 Noto Serif SC · 正文 Noto Sans SC · 拉丁 Space Grotesk · 数字/印章 Space Mono。
- 每页底部固定免责声明：基于公开信息的思考框架，非投资建议，标的自行实时验证。

## 本地预览

```bash
cd ~/alpha-vault && python3 -m http.server 8080
# 浏览器开 http://localhost:8080
```

— @zmyroy
