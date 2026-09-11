# 图文作品集 / Illustrated Phone-Case Stories

一个 GitHub Pages 站点，收录来自文档的图文网页作品。每件作品都含**中文版、英文版**与**跟随手机系统语言自动跳转**的双语二维码入口，网址永久固定。

## 永久访问地址

### 作品一 · 砖纹袈裟 · 信仰的现代传承 / The Brick-Pattern Kasaya

| 用途 | 网址 |
|---|---|
| 双语入口（二维码指向这里） | https://yutou1223.github.io/brick-kasaya/ |
| 中文版 | https://yutou1223.github.io/brick-kasaya/zh/ |
| 英文版 | https://yutou1223.github.io/brick-kasaya/en/ |

### 作品二 · 大漠孤行 · 长安月 / Solitary Journey Across the Desert

| 用途 | 网址 |
|---|---|
| 双语入口（二维码指向这里） | https://yutou1223.github.io/brick-kasaya/damo/ |
| 中文版 | https://yutou1223.github.io/brick-kasaya/damo/zh/ |
| 英文版 | https://yutou1223.github.io/brick-kasaya/damo/en/ |

### 作品三 · 誓向西行 · 长安月 / The Vow to Go West

| 用途 | 网址 |
|---|---|
| 双语入口（二维码指向这里） | https://yutou1223.github.io/brick-kasaya/xixing/ |
| 中文版 | https://yutou1223.github.io/brick-kasaya/xixing/zh/ |
| 英文版 | https://yutou1223.github.io/brick-kasaya/xixing/en/ |

### 作品四 · 云端的小小祈愿 · 唐风守护者 / A Little Wish in the Clouds

| 用途 | 网址 |
|---|---|
| 双语入口（二维码指向这里） | https://yutou1223.github.io/brick-kasaya/qiyuan/ |
| 中文版 | https://yutou1223.github.io/brick-kasaya/qiyuan/zh/ |
| 英文版 | https://yutou1223.github.io/brick-kasaya/qiyuan/en/ |

## 双语跳转规则

各作品的入口页读取 `navigator.languages`：

- 任一项以 `zh` 开头（`zh`、`zh-CN`、`zh-Hans-CN`、`zh-TW`、`zh-HK` …）→ 进入中文版
- 其余所有语言（`en`、`ja`、`de`、`fr` …）→ 进入英文版
- 无语言信息时兜底进入英文版

页面上另有「中文版 / English Version」手动按钮；手动选择会写入 `sessionStorage`，本次会话内不再被自动跳转覆盖。禁用 JavaScript 时由 `<noscript>` 的 meta refresh 兜底进入英文版。（预览路由页不跳转：在入口地址后加 `?stay=1`。）

## 目录结构

```
docs/                        ← GitHub Pages 发布目录
├─ index.html                作品一双语入口（语言路由页，含二维码）
├─ qr/                       作品一二维码：分享卡片 / 1400px / SVG / 512px / 256px
├─ zh/  en/                  作品一中文版 / 英文版（页面 + 图片资源）
├─ damo/                     作品二
│  ├─ index.html             作品二双语入口
│  ├─ qr/                    作品二二维码
│  ├─ 404.html               找不到页面时回到入口
│  └─ zh/  en/               作品二中文版 / 英文版（页面 + 图片资源 + 单文件版）
├─ xixing/                   作品三
│  ├─ index.html             作品三双语入口
│  ├─ qr/                    作品三二维码
│  ├─ 404.html               找不到页面时回到入口
│  └─ zh/  en/               作品三中文版 / 英文版（页面 + 图片资源 + 单文件版）
├─ qiyuan/                   作品四
│  ├─ index.html             作品四双语入口
│  ├─ qr/                    作品四二维码
│  ├─ 404.html               找不到页面时回到入口
│  └─ zh/  en/               作品四中文版 / 英文版（页面 + 图片资源 + 单文件版）
└─ 404.html                  全站 404 → 回到作品一入口
standalone/                  作品一离线单文件版（图片已内嵌，不参与发布）
```

## 二维码

每个作品目录下的 `qr/` 都有一套，内容已用解码库反向校验，全部指向该作品的双语入口：

| 文件 | 说明 |
|---|---|
| `bilingual-qr-card.png` | 分享卡片（1800×2560，含标题、二维码、永久网址与跳转规则） |
| `bilingual-qr-card.svg` | 同一张卡片的矢量版 |
| `bilingual-qr.png` | 二维码高清图（1400×1400，容错等级 H，留白 3 模块） |
| `bilingual-qr.svg` | 二维码矢量版，可无损放大印刷 |
| `bilingual-qr-512.png` / `bilingual-qr-256.png` | 网页与文档用尺寸 |

地址固定不变，二维码可长期印刷使用，不会因服务重启而失效。

## 本地预览

```powershell
python tools/site_server.py --dir docs --port 8944
# 打开 http://127.0.0.1:8944/          （作品一）
# 打开 http://127.0.0.1:8944/damo/     （作品二）
```

## 设计说明

两件作品共用同一套设计语言（暖色底纹 + 居中卡片 + 双栏图文 + 首字/引文块 + 结语通栏 + 图片点击放大），配色取自各自图片：

- 作品一：陶土棕 + 麻绳米色，背景为 CSS 绘制的错缝**砖纹**肌理，正文首字下沉。
- 作品二：琥珀金 + 沙漠黄，背景为 CSS 绘制的**流沙纹**肌理，引文用左侧色条块呈现。
- 作品三：深藏蓝 + 中国红 + 描金，外围为 CSS 生成的夜空星点与云纹，内层是带三色描边的纸张面板，师徒对话用左侧金色细线 + 说话人小字呈现。
- 作品四：米色祥云 + 青绿波涛 + 中国红 + 描金，背景为 CSS 生成的多层**云海**肌理，标题分隔线用金→红→青→金四色渐变。

四件作品的栅格完全一致：页面 1180px、图片卡 400px、正文栏 676px、栏间距 56px；英文版沿用相同的栅格、卡片尺寸与阴影，仅按拉丁字母调整字体栈与大标题字号。（作品一为顶层站点，其余为子目录，四个入口页互相链接。）

## 更新内容

```powershell
# 本机无法直连 github.com:443，故用 GitHub API 推送
tools\push-via-api.ps1 -Token <PAT> -Owner yutou1223 -Repo brick-kasaya -Root <站点目录> -RemotePathPrefix docs/damo
```
