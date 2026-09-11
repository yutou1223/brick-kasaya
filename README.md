# 砖纹袈裟 · 信仰的现代传承 / The Brick-Pattern Kasaya

一份来自文档《砖纹袈裟-信仰的现代传承》的图文网页作品，含中文版、英文版与**跟随手机系统语言自动跳转**的双语二维码入口。

## 永久访问地址

| 用途 | 网址 |
|---|---|
| 双语入口（二维码指向这里） | https://yutou1223.github.io/brick-kasaya/ |
| 中文版 | https://yutou1223.github.io/brick-kasaya/zh/ |
| 英文版 | https://yutou1223.github.io/brick-kasaya/en/ |

## 双语跳转规则

`docs/index.html` 读取 `navigator.languages`：

- 任一项以 `zh` 开头（`zh`、`zh-CN`、`zh-Hans-CN`、`zh-TW`、`zh-HK` …）→ 进入中文版 `/zh/`
- 其余所有语言（`en`、`ja`、`de`、`fr` …）→ 进入英文版 `/en/`
- 无语言信息时兜底进入英文版

页面上另有「中文版 / English Version」手动按钮；手动选择会写入 `sessionStorage`，本次会话内不再被自动跳转覆盖。禁用 JavaScript 时由 `<noscript>` 的 meta refresh 兜底进入英文版。

## 目录结构

```
docs/                      ← GitHub Pages 发布目录
├─ index.html              双语入口（语言路由页，含二维码）
├─ 404.html                找不到页面时回到入口
├─ qr/                     二维码：1400px PNG、SVG、512px、256px
├─ zh/                     中文版页面 + 图片资源
└─ en/                     英文版页面 + 图片资源
standalone/               离线单文件版（图片已内嵌，不参与发布）
```

## 二维码

`docs/qr/bilingual-qr.png`（1400×1400，容错等级 H，留白 3 模块）指向双语入口。已用解码库反向校验，三个尺寸均能正确解出永久地址。此地址固定不变，二维码可长期印刷使用。

## 本地预览

```powershell
python tools/site_server.py --dir docs --port 8944
# 打开 http://127.0.0.1:8944/
```

## 说明

- 页面设计为暖色陶土 + 麻绳米色，背景含 CSS 绘制的错缝砖纹肌理，正文首字下沉，图片可点击放大。
- 图片取自原始文档（889×1087），`<picture>` 优先加载体积更小的 JPEG 版本。
- 英文版沿用与中文版完全相同的栅格、卡片尺寸、正文栏宽、配色与阴影，仅字体栈与标题字号按拉丁字母调整。
