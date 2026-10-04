# LLM 笔记

一个用于记录 LLM 阅读、实验与思考的中文笔记网站。采用 Quarto + GitHub Pages，支持全文搜索、分类筛选、文章目录和代码复制。

- 网站：https://bbfss.github.io/llm-notes/
- 仓库：https://github.com/bbfss/llm-notes

## 平时怎么放笔记

1. 复制 `templates/note.md` 到 `notes/`，改成自己的文件名，例如 `notes/rag-experiment.md`。
2. 修改文件顶部的标题、日期、分类与简介，正文用 Markdown 编写。现有 `.md` 笔记也可以直接放进去，只需补上顶部信息。
3. 提交到 GitHub 的 `main` 分支，网站会自动更新，首页会自动收录新文章。

不需要在电脑上运行任何命令，也可以在 GitHub 仓库中选择 **Add file → Create new file**，输入 `notes/你的文件名.md`，粘贴笔记并提交。

标题等顶部信息示例：

```yaml
---
title: "我的第一篇 RAG 实验"
date: 2026-10-04
categories: [RAG, 实验记录]
description: "比较两种切分方式对检索结果的影响。"
---
```

文件名建议使用英文、小写与短横线；标题和正文可以用中文。日期改成实际记录日期。分类可自行新增。

图片可放在文章旁边的 `notes/images/` 文件夹，引用方式如 `![实验结果](images/result.png)`。

## 首次上线

1. 在你的 GitHub 账号创建公开仓库 `llm-notes`，默认分支使用 `main`。
2. 将这个目录内的源文件提交到仓库，包括隐藏目录 `.github/`；不要提交 `_site/` 与 `.quarto/`。
3. 打开仓库 **Settings → Pages → Build and deployment → Source**，选择 **GitHub Actions**。
4. 打开 **Actions → Publish LLM Notes → Run workflow**，选择 `main` 并运行。
5. 流程成功后，在 **Settings → Pages** 查看网站地址。项目网站通常是 `https://你的用户名.github.io/llm-notes/`。

仓库和网站内容均为公开内容。

## 本地预览（可选）

安装 Quarto 1.10.18 后，在此目录运行：

```sh
quarto preview
```

生成可发布的静态网页：

```sh
quarto render
```

首页是 `index.qmd`，网站设置是 `_quarto.yml`，样式是 `styles.css`。`templates/` 不会渲染成文章。
