# ALPHA VAULT

一条信号，挖到能下单的那一层。独立投研——拆开一句话：谁说的、为什么、该买什么。一篇一页，只留结论。
线上：`https://alpha-vault.pages.dev`（Cloudflare Pages，连上本仓库后每次 `git push` 自动上线）。

## 结构

```
alpha-vault/
├── index.html          ← 目录页（招牌 + 在看 tape 头框 + 按时间的编辑目录行）
├── TEMPLATE.html       ← 新研究页的起手模板（内页样式，带返回导航）
├── assets/             ← 以后放共享图片
└── r/                  ← 每一份研究各占一个文件夹
    └── 2026-06-14-nadella-ecosystem/
        └── index.html  ← 线上地址 /r/2026-06-14-nadella-ecosystem/
```

命名规则：文件夹用 `YYYY-MM-DD-英文短题`，全小写、连字符分隔。列表天然按日期排序，URL 也干净。

## 加一篇新研究（两步）

1. **建内页**：复制 `TEMPLATE.html` 到 `r/<日期-短题>/index.html`，填进论点、配图、标的。
2. **上目录**：打开 `index.html`，在对应月份分组里复制一整块 `<a class="entry">…</a>`，改这些字段：
   - `href` → 新文件夹路径
   - `.e-no .date` 日期（`06.14`，分隔点用 `<i>` 标红）
   - `.thesis` 大字论点、`.take` 一句话「为什么/买什么」、`.src` 来源出处
   - `.e-tag` 板块标签、`.e-tickers` 标的
   - 顺手把 `.tapeframe` 里的「在看」tape 加上新标的（保持首尾各一份、无缝滚动）
   - `.chead .ct`（`／ 0N`）和月份分组 `.month .ct`（`N 篇`）计数 +1；新月份就再复制一个 `.month` 块

> 篇数多了再启用顶部「板块」那一栏（现为「·待开」占位）。

## 设计语言（保持一致）

- **目录页（封面）**：暖纸 `#F1EDE3` / 暖墨 `#19170F` / 朱红 `#D23A19` 点睛，绿 `#1E5A3B` 作「板块/做多」语义色。字体：**Fraunces**（拉丁大标题，VAULT 用斜体红）+ **Noto Serif SC**（中文标题）+ **Archivo**（正文）+ **JetBrains Mono**（编号/日期/标的）。护眼亮色，别上深色。
- **研究内页**：沿用 `TEMPLATE.html` 那套纸 + 墨绿 + 衬线，每页底固定免责声明（基于公开信息、非投资建议、标的自验）。

## 本地预览

```bash
cd ~/alpha-vault && python3 -m http.server 8080
# 浏览器开 http://localhost:8080
```

— @beer98
