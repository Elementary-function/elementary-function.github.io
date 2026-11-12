# elementary-function.github.io

个人主页。纯静态站点，没有构建步骤。

## 文件结构

```
index.html          主页（单页，所有板块都在这里）
css/style.css       全站样式
blog/*.html         文章，每篇一个 HTML
images/             照片、项目截图（现在还是空的）
.nojekyll           告诉 GitHub Pages 跳过 Jekyll，别删
404.html            找不到页面时显示
```

## 怎么改

**改名 / 改标语**
`index.html` 里搜 `Main Function`、`写代码，也写字`、`功在平时`，直接替换。

**换头像**
把照片命名为 `profile.jpg` 放进 `images/`，再把 `index.html` 里的

```html
<div class="avatar">M</div>
```

换成

```html
<div class="avatar"><img src="images/profile.jpg" alt=""></div>
```

**改邮箱**
`index.html` 里搜 `1946809464@qq.com`，有 5 处，全部替换。

**加一个项目**
复制 `<article class="card">` 那一整块，改标题、描述、技术栈标签和链接。
加完后把那张虚线占位卡（`card card-hint`）删掉。

**加一段经历**
复制 `<div class="tl-item">` 那一整块，改日期、标题、描述。顺序是新的在上。

**加一篇文章**
复制 `blog/hello-world.html`，改 `<title>`、`<h1>`、`<time>` 和正文。
再回 `index.html` 的「文章」板块，复制一个 `<li>` 改成新链接。

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

等一两分钟，GitHub Pages 自动更新。如果看到的还是旧页面，用 `Ctrl+Shift+R` 强刷。

## 注意

- 文件名和路径**区分大小写**，全用小写英文，别用中文名。
- 仓库名必须叫 `elementary-function.github.io`，改了名字这个域名就失效。
- `.nojekyll` 不能删。
