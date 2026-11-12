# elementary-function.github.io

周禹的个人主页。纯静态站点，没有构建步骤。

## 文件结构

```
index.html          主页（单页，所有板块都在这里）
css/style.css       全站样式
blog/*.html         随笔，每篇一个 HTML
files/*.pdf         论文 PDF，供下载
images/             照片
.nojekyll           告诉 GitHub Pages 跳过 Jekyll，别删
404.html            找不到页面时显示
```

## 怎么改

**改个人信息**
`index.html` 里搜 `周禹`、`河海大学`、`3D 视觉`，逐处替换。

**换头像**
把照片命名为 `profile.jpg` 放进 `images/` 覆盖原文件即可。
如果新照片构图不同、脸被裁掉了，去 `css/style.css` 改这一行的百分比：

```css
.avatar img { object-position: 36% 22%; }
```

第一个数是水平位置，越大越靠右；第二个是垂直位置，越大越靠下。

**改邮箱**
搜 `1946809464@qq.com`，有 5 处，全部替换。

**加一篇论文**
复制 `<li class="pub">` 那一整块，改标题、作者、期刊、卷期。
PDF 放进 `files/`，文件名用英文小写加连字符，再把 `pub-links` 里的路径改掉。
作者列表里自己名字要包在 `<span class="me">` 里，会加下划线。

**加一段教育经历**
复制 `<div class="tl-item">`，改日期、学校、学历。顺序是新的在上。

**加一个项目**
复制 `<article class="card">`，改标题、描述、标签和链接。

**加一篇随笔**
复制 `blog/hello-world.html`，改 `<title>`、`<h1>`、`<time>` 和正文。
再回 `index.html` 的「随笔」板块，复制一个 `<li>` 改成新链接。

**改配色**
`css/style.css` 最上面的 `:root` 里改 `--accent`（强调色）和 `--bg`（背景色）。
深色模式在下面的 `@media (prefers-color-scheme: dark)` 里，跟着一起改。

## 本地预览

装 VS Code 的 Live Server 扩展，右键 `index.html` → Open with Live Server。

或者命令行：

```bash
python -m http.server 8000
```

然后开 http://localhost:8000

## 发布

```bash
git add -A
git commit -m "更新内容"
git push origin main
```

如果 `push` 报 `HTTP2 framing layer` 或 `schannel` 错误，换成：

```bash
git -c http.version=HTTP/1.1 push origin main
```

等一两分钟，GitHub Pages 自动更新。看到的还是旧页面就 `Ctrl+Shift+R` 强刷。

## 注意

- 文件名和路径**区分大小写**，全用小写英文，别用中文名。
- 仓库名必须叫 `elementary-function.github.io`，改了名字这个域名就失效。
- `.nojekyll` 不能删。
- `files/` 里那篇水下三维重建的 PDF 有 13MB，仓库别塞太多这种大文件。
