# Wei Guo — 个人学术主页

纯静态单页（`index.html`），由 GitHub Pages 直接托管，无需构建。

## 本地预览
VS Code 安装 Live Server，右键 `index.html` → Open with Live Server。网址后加 `?lang=zh` 直接打开中文版。

## 更新
修改文件后，在 VS Code 左侧"源代码管理"中填写说明 → 提交 → 同步更改。1–2 分钟后网站自动更新。

## 页面结构（用 Ctrl+F 搜索 id 定位）
| 区块 | id | 说明 |
|---|---|---|
| 首屏 | `hero` | 姓名与滚动文字；背景为实时绘制的偏振取向场 |
| 简介 | `about` | 照片、简介、学位、研究兴趣 |
| 研究 | `research` | 按研究主题分组，每个主题附相关论文；综述单独一栏 |
| 动态 | `news` | `[日期]` + 一句话，最新的放最上面 |
| 节选作品 | `publications` | 论文列表与学术服务 |
| 联系 | `contact` | 邮箱、ORCID、Google Scholar、实验室 |
| 生活 | `life` | 生活照片墙，点击可放大 |

## 常见修改
- **双语**：每段文字都有 `class="en"` 和 `class="zh"` 两个版本，修改时一起改。
- **首屏滚动文字**：搜索 `var ROLES`，分别修改 `en` 和 `zh` 两个列表。英文前缀是 "I'm "，每句自带 a / an。
- **加动态**：在 `<ul class="news">` 下第一行复制一个 `<li>`，日期手动填写。想配图就在 `<li>` 里加
  `<img class="news-img" src="assets/xxx.jpg" alt="说明">`。
- **加论文**：在 `publications` 的 `<ol class="publist">` 里复制一个 `<li>`；若属于某个研究主题，也在该主题的 `<ul class="cites">` 里加一条。自己的名字用 `<span class="me">Guo, W.</span>`。
- **换头像**：把照片放进 `assets/`（例如 `assets/wg.jpg`），把 `<img class="portrait" src="...">` 的 `src` 改为 `assets/wg.jpg`。
- **加链接**（GitHub、LinkedIn 等）：在 `contact` 的 `<ul class="clinks">` 里复制一个 `<li>`。
- **生活照片**：把照片放进 `assets/life/`，命名为 `life-01.jpg` … `life-06.jpg`，再在 `<section id="life">` 里改每张的中英文说明；不需要的 `<figure>` 直接删除，想多放就复制一个。建议每张压到 1200 px 宽、300 KB 以内。本地预览时空位显示为虚线框；上线后缺照片的位置自动隐藏，一张都没有时整个"生活"栏目和导航链接都会隐藏。
