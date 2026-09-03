# An-Bao Xu's Homepage

学术个人主页，基于 [jemdoc](http://jemdoc.jaboc.net/) 生成，托管在 GitHub Pages：

**https://anbaoxu.github.io**

## 文件结构

| 文件 | 作用 |
|---|---|
| `index.jemdoc` | 页面源文件（**日常改这个**） |
| `index.html` | 由 jemdoc.py 生成的网页（不要手改） |
| `jemdoc.py` | 生成器（已转为 Python 3 兼容版） |
| `index.conf` | 页面模板配置（页眉/页脚等） |
| `jemdoc.css` | 样式表 |
| `files/CV.pdf` | 简历 |
| `pictures/` | 照片 |

## 更新流程

### 论文列表（自动同步 ORCID）

Publications 板块**不需要手动更新**：网页加载时由 `index.conf` 里的脚本实时从
ORCID（<https://orcid.org/0000-0003-2755-0013>）公共 API 拉取并渲染。

- 新增/修改论文：直接在 ORCID 中操作即可，主页自动同步（无需改动本仓库）。
- 尚未收录进 ORCID 的条目放在 `index.jemdoc` 的 "Other Papers and Preprints"
  一节；一旦在 ORCID 中补录，请从该节删除，避免重复。

### 其他内容（简介、经历、报告等）

1. 编辑 `index.jemdoc` 的内容；
2. 在本机（需 Python 3，例如 anaconda 的 python3）重新生成网页：

   ```bash
   python3 jemdoc.py -c index.conf index.jemdoc
   ```

3. 提交并推送，约 1 分钟后网站自动更新：

   ```bash
   git add .
   git commit -m "update homepage"
   git push origin main
   ```

## jemdoc 语法要点

- `== 标题`：一级小节标题；`-` 开头：列表项。
- 链接：`[网址 显示文字]`；邮箱：`[name@example.com]` 自动变成 mailto。
- 网址/正文中的 `/文字/` 会被当成斜体，需要原样显示时写成 `\/文字\/`。
- `\n` 表示换行；`~~~` 之间的块是页面顶部（照片 + 联系方式）。
- 引文建议加 DOI 链接，例如：
  `[http://dx.doi.org/10.1155/2013/781276 DOI: 10.1155\/2013\/781276]`
