# gif-maker — Banner Ad Editor

一个零依赖、单 HTML 文件的动画 banner 编辑器。在画布上拖拽元素做动画,一键导出 **GIF / PNG / HTML5 广告包(zip)**。

A zero-dependency, single-file banner ad editor. Drag elements on a canvas, animate them, and export **GIF / PNG / HTML5 ad zip** — all in the browser.

## 使用 Usage

直接用浏览器打开 `index.html` 即可(如遇 CDN 模块被拦截,在目录下运行 `npx serve` 用 http 打开)。

Open `index.html` in a browser. If the CDN module import is blocked under `file://`, run `npx serve` and open via http.

## 功能 Features

- **元素**:文字(支持 `**粗体**` / `{#hex 变色}` 内联标记)、图片(本地上传,自动压缩)、圆角色块、动画柱状图
- **动画**:每个元素独立的入场(淡入/滑入/生长/起点→终点移动)与退场(精确到秒的淡出),拖拽时间轴逐帧检查
- **画布操作**:拖拽移动、四边/角缩放手柄、中线吸附对齐(Alt 临时关闭)、元素锁定
- **GIF 导出**:自动压缩阶梯(帧间差分 → 降色数 → 照片柔化 → 降帧率),直到满足目标体积(默认 ≤80KB)
- **HTML5 导出**:符合 Google Ad Manager clickTag 规范的 zip(`ad.size` meta、新窗口点击跳转、24fps rAF、无 SVG/eval/定时器);默认 subload 结构(index.html + assets.js + backup.png),可选 single-file 单文件模式
- **广告规格预设**:Leaderboard 728×90、EASA 472×114、Skyscraper 160×600、Half Page 300×600、README 头图 1280×320
- 设计自动保存在浏览器 localStorage

## 技术 Tech

原生 Canvas 2D + [gifenc](https://github.com/mattdesl/gifenc)(GIF 编码)+ [fflate](https://github.com/101arrowz/fflate)(zip 打包),均由 CDN 按需加载,无构建步骤。

Vanilla Canvas 2D + gifenc (GIF encoding) + fflate (zip), loaded from CDN. No build step.
