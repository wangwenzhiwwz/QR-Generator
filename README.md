# QR Studio Ultra-Flat

> **高清矢量二维码生成器 | High-Definition & Vector QR Generator**

QR Studio Ultra-Flat 是一款基于 **Browser-Side Rendering (浏览器端渲染)** 的极简工具。它摒弃了冗余的视觉装饰，专注于提供高清导出、品牌定制以及极致的扁平化设计美学。

---

## 核心特性 / Key Features

* **Ultra HD Export**: 内部始终以 $1200 \times 1200$ 像素进行渲染，确保导出的 **PNG** 达到印刷级清晰度。
* **Vector Support**: 提供 **SVG** 矢量导出，支持设计稿无限放大不失真。
* **Brand Customization**: 
    * **Logo Embedding**: 支持一键嵌入中心图标（自动处理容错率）。
    * **Visual Styles**: 提供 4 种点阵样式（Square, Dots, Rounded, Fluid）。
* **Productivity Tools**: 
    * **Quick Actions**: 集成一键粘贴 (Paste) 与一键复制图片 (Copy to Clipboard)。
    * **History**: 自动保存最近 5 条记录至 LocalStorage，支持点击回填。
* **Design Language**: 
    * **Ultra-Flat**: 遵循无阴影、高对比度的扁平化设计。
    * **Responsive**: 完美适配 PC（左右布局）与移动端（上下布局）。
    * **Glassmorphism**: 输入区保留微妙的毛玻璃质感，增强通透感。

---

## 技术架构 / Tech Stack

| 组件 / Component | 技术 / Technology | 说明 / Note |
| :--- | :--- | :--- |
| **Core Engine** | `qr-code-styling` | 支持多种样式与矢量导出的核心库 |
| **Styling** | `Tailwind CSS` | 响应式布局与原子化样式管理 |
| **Typeface** | `Inter` | 现代、清晰的非衬线字体 |
| **Storage** | `LocalStorage` | 离线存储最近生成记录 |

---

## 快速使用 / Quick Start

1.  **部署**: 将 `index.html` 放置在任意 Web 服务器或直接本地打开。
2.  **粘贴**: 点击 **[Paste]** 按钮快速导入剪贴板内容。
3.  **定制**: 
    * 上传透明背景的 PNG 作为 **Logo**。
    * 在 **Dot Style** 中选择 `Fluid` 或 `Dots` 以获得更现代的视觉感。
4.  **导出**: 根据需求选择 **PNG (HD)** 或 **SVG (Vector)**。

---

## 核心逻辑说明 / Technical Logic

### 1. 矢量生成与导出
系统利用 `qr-code-styling` 的 API，在导出时动态切换渲染引擎：
```javascript
// PNG 导出逻辑
qrCode.download({ name: "QR", extension: "png" });

// SVG 导出逻辑
qrCode.download({ name: "QR", extension: "svg" });
