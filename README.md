# DexSwarm AI · 产品资料中心

面向客户和合作伙伴的中英双语产品手册网站。使用原版手册中的产品图片与品牌色，支持桌面和手机访问。

## 功能

- 中英文网站切换，并在本设备保存语言偏好。
- 中英文产品手册在线阅读：6 页缩略图、翻页、键盘导航、语言版本切换。
- 中英文 PDF 下载，阅读器内也可在独立窗口打开 PDF。
- DexSwarm Ego、UMI Dex 1、UMI G1 与配套 Gripper 产品概览。
- 公司介绍、邮件咨询、电话及微信联系方式。
- 原生 HTML / CSS / JavaScript，无框架、无需安装依赖，无追踪脚本。

## 在 GitHub Pages 发布

仓库管理员只需进行一次设置：

1. 打开 [Settings → Pages](https://github.com/xitong-c/DexSwarmAI_hub/settings/pages)。
2. 在 **Build and deployment → Source** 中选择 **Deploy from a branch**。
3. 在 **Branch** 中选择 **main** 和 **/ (root)**，点击 **Save**。
4. 等待 GitHub 完成部署。之后每次更新 main 分支，网站将自动发布。

启用后的地址：**https://xitong-c.github.io/DexSwarmAI_hub/**

所有本地资源均使用相对路径，兼容仓库子路径。`.nojekyll` 禁用 Jekyll 处理。

## 本地预览

在仓库目录运行：

```sh
python -m http.server 8765
```

浏览器打开 `http://localhost:8765`。请使用 HTTP 服务预览，避免直接打开本地 HTML 时浏览器限制读取 JSON。

## 文件结构

```text
index.html          页面内容与在线阅读器
styles.css          桌面 / 手机布局、视觉样式
app.js              双语文案、阅读器交互、文件大小读取
assets/             官网视觉、封面、产品图片与 12 张手册页面预览
manuals/            中英文 PDF 和 manifest.json
```

## 更新手册

1. 替换 `manuals/dexswarm-product-manual-zh.pdf` 或 `manuals/dexswarm-product-manual-en.pdf`。
2. 从相应 PDF 重新导出 `assets/manual-zh-1.webp` 至 `manual-zh-6.webp`，或对应英文预览。
3. 更新相应 `assets/cover-zh.webp` / `cover-en.webp`。
4. 更新 `manuals/manifest.json` 中的实际文件字节数，并检查下载与预览一致。
5. 若页数变动，同步更新 `app.js` 的 `pageCount`、双语文案中的页数和 HTML 默认页数。
6. 手册改版时同步更新页面卡片上的版本日期 `2026.09`；必要时更新产品参数。

## 手册版本说明

当前手册：2026 年 9 月版本，共 6 页。英文内容对应中文原稿。

网站提供为在线浏览优化的 PDF 副本：文字、矢量对象与页面布局保留，超高分辨率图片优化至约 150 dpi，并移除旧的 Illustrator 私有编辑数据。原始印刷级 PDF 和 AI 编辑交换文件不存入该仓库。

网站中的技术参数均来自产品手册；原文件中已合成为图片的技术图示不会被重新绘制。

联系方式：team.dexswarmai@outlook.com
