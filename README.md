# dimbuffer 的技术笔记

公开站点：<https://dimbuffer.github.io>

用来记录技术成长和踩坑。页面是中文的。

## 站点里有什么

- **笔记**：首页，按时间列出 `_posts/` 里的文章
- **关于**：说明这是 dimbuffer 的公开笔记本
- **标签**：由每篇笔记 front matter 里的 `tags` 自动汇总。导航里没有单独入口，首页和文章里的标签会链到这里

常用标签：踩坑、学习笔记、项目。需要更细的分类时，直接在笔记里加新标签即可。

## 新增一篇笔记

只需要新建一个 Markdown 文件，不用改配置，也不用再加页面。

1. 在 `_posts/` 下新建文件。
2. 文件名必须是 `YYYY-MM-DD-短标题.md`。日期用四位年、两位月、两位日；短标题用英文或拼音，用连字符，不要用空格。例如：`_posts/2026-11-11-git-push-rejected.md`。
3. 在文件开头写上 front matter，正文用中文。格式可以照着示例笔记抄：[`_posts/2026-11-11-example-note-not-listed.md`](_posts/2026-11-11-example-note-not-listed.md)。

```yaml
---
layout: post
title: "笔记标题"
date: 2026-11-11
tags:
  - 踩坑
---

先写现象，再写原因和处理。
```

- `title`：页面上显示的标题，用中文。
- `date`：可以省略。省略时用文件名里的日期。不要写成未来的日期，否则构建时不会发布。
- `layout`：可以省略。`_config.yml` 已经把 `_posts/` 下的文章默认成 `post` 布局。
- `tags`：列表。优先用「踩坑」「学习笔记」「项目」，也可以自增。

4. 把改动合并进 `main`。GitHub Pages 会用 `main` 分支的根目录自动构建并发布。构建通常需要一两分钟，完成后就能在 <https://dimbuffer.github.io> 看到新笔记。

## 写的时候注意

不要在笔记、关于页或这个 README 里写真实姓名、学校、电话、邮箱、成绩、所在城市或其他个人身份信息。公开使用的名字只有 dimbuffer。

## 本地预览（可选）

需要本机已安装 Ruby。

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

浏览器打开 <http://127.0.0.1:4000>。不预览也可以：推到 `main` 之后由 GitHub Pages 构建。

## 发布方式

仓库的 GitHub Pages 从 `main` 分支的 `/`（站点根目录）发布，使用 Jekyll 和 GitHub Pages 自带的 minima 主题。合并到 `main` 后就会更新 <https://dimbuffer.github.io>，不需要另外上传生成好的 HTML。
