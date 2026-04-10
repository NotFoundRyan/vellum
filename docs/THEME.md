# 素笺 - 主题开发指南

本文档详细说明主题文件的格式和每个属性的作用，帮助您创建自定义主题。

## 目录

- [主题文件结构](#主题文件结构)
- [基础属性](#基础属性)
- [标题样式](#标题样式)
- [正文与段落](#正文与段落)
- [代码样式](#代码样式)
- [列表样式](#列表样式)
- [表格样式](#表格样式)
- [引用与金句卡片](#引用与金句卡片)
- [其他元素](#其他元素)
- [暗黑模式](#暗黑模式)
- [完整示例](#完整示例)
- [导入主题](#导入主题)

---

## 主题文件结构

主题文件是 JSON 格式，包含一系列 CSS 样式字符串。每个属性对应一个 HTML 元素的样式。

```json
{
    "name": "主题名称",
    "dotColor": "#品牌色",
    "brandColor": "#品牌色",
    "h1": "CSS样式字符串",
    "h2": "CSS样式字符串",
    ...
}
```

---

## 基础属性

| 属性 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `name` | string | ✅ | 主题显示名称，显示在主题选择栏 |
| `dotColor` | string | ✅ | 主题圆点颜色，用于主题按钮前的圆点标识 |
| `brandColor` | string | ❌ | 品牌色，部分元素默认使用此颜色 |

### 示例

```json
{
    "name": "我的主题",
    "dotColor": "#ff6b6b",
    "brandColor": "#ff6b6b"
}
```

---

## 标题样式

### h1 - 一级标题（主标题）

文章的主标题，通常居中显示，字号最大。

| 推荐属性 | 推荐值 | 说明 |
|---------|--------|------|
| `font-size` | 24-28px | 主标题字号 |
| `font-weight` | 700-900 | 加粗程度 |
| `text-align` | center | 居中对齐 |
| `letter-spacing` | 4-8px | 字间距，增加呼吸感 |
| `margin` | 30-40px 0 20-30px | 上下边距 |

```json
"h1": "font-size:26px;font-weight:900;color:#1a1a1a;text-align:center;margin:35px 0 25px;letter-spacing:5px;line-height:1.5;"
```

### h2 - 二级标题（章节标题）

文章的章节标题，建议使用左边框或底边框装饰。

| 推荐属性 | 推荐值 | 说明 |
|---------|--------|------|
| `font-size` | 16-18px | 章节标题字号 |
| `font-weight` | 600-700 | 加粗程度 |
| `padding-left` | 10-15px | 左侧内边距（配合边框） |
| `border-left` | 3-4px solid #颜色 | 左侧装饰边框 |

```json
"h2": "font-size:17px;font-weight:700;color:#1a1a1a;margin:28px 0 16px;padding-left:12px;border-left:3px solid #1a1a1a;line-height:1.6;"
```

### h3 - 三级标题

小节标题，样式相对简洁。

```json
"h3": "font-size:16px;font-weight:700;color:#333;margin:22px 0 12px;line-height:1.6;"
```

### h4 - 四级标题

最小级别的标题。

```json
"h4": "font-size:15px;font-weight:700;color:#444;margin:18px 0 10px;line-height:1.6;"
```

---

## 正文与段落

### p - 正文段落

正文是文章的主体，需要保证良好的阅读体验。

| 推荐属性 | 推荐值 | 说明 |
|---------|--------|------|
| `font-size` | 15px | 黄金字号，微信推荐 |
| `color` | #3f3f3f | 深灰色，比纯黑更舒适 |
| `line-height` | 1.75-2.0 | 行高，增加可读性 |
| `letter-spacing` | 0.5-1px | 字间距 |
| `text-align` | justify | 两端对齐 |

```json
"p": "font-size:15px;color:#3f3f3f;line-height:1.75;margin:15px 0;letter-spacing:1px;text-align:justify;"
```

### strong - 加粗文字

用于强调重要内容。

```json
"strong": "font-weight:700;color:#1a1a1a;"
```

**进阶技巧**：使用渐变背景模拟荧光笔效果

```json
"strong": "font-weight:700;color:#1a1a1a;background:linear-gradient(to top,#d0d0d0 40%,transparent 40%);padding:0 2px;"
```

### em - 斜体文字

用于表示强调或术语。

```json
"em": "font-style:italic;color:#666;"
```

---

## 代码样式

### pre - 代码块容器

代码块的外层容器，通常使用深色背景。

```json
"pre": "background:#2b2b2b;border-radius:8px;padding:16px;margin:20px 0;overflow-x:auto;"
```

### code_block - 代码块文字

代码块内的代码文字样式。

```json
"code_block": "color:#a9b7c6;font-size:13px;font-family:\"JetBrains Mono\",monospace;line-height:1.7;"
```

### code_inline - 行内代码

段落中的行内代码，使用浅色背景。

```json
"code_inline": "background:#f5f5f5;color:#c7254e;padding:2px 6px;border-radius:3px;font-size:13px;font-family:\"JetBrains Mono\",monospace;"
```

---

## 列表样式

### ul - 无序列表

```json
"ul": "margin:15px 0;padding-left:20px;color:#3f3f3f;font-size:15px;line-height:1.8;list-style:disc;"
```

### ol - 有序列表

```json
"ol": "margin:15px 0;padding-left:20px;color:#3f3f3f;font-size:15px;line-height:1.8;"
```

### li - 列表项

```json
"li": "margin:6px 0;font-size:15px;line-height:1.8;color:#3f3f3f;"
```

### ulPrefix / olPrefix - 自定义列表前缀

如果设置这些属性，列表前缀会使用自定义样式。

```json
"ulPrefix": "color:#1a1a1a;",
"olPrefix": "color:#1a1a1a;font-weight:700;"
```

---

## 表格样式

### table - 表格容器

```json
"table": "width:100%;border-collapse:collapse;margin:20px 0;font-size:14px;border-top:2px solid #1a1a1a;"
```

### th - 表头单元格

```json
"th": "background:#f5f5f5;padding:12px 14px;text-align:left;font-weight:700;color:#1a1a1a;border:none;border-bottom:2px solid #1a1a1a;font-size:14px;"
```

### td - 数据单元格

```json
"td": "padding:12px 14px;border:none;border-bottom:1px solid #e8e8e8;font-size:14px;color:#3f3f3f;"
```

---

## 引用与金句卡片

### blockquote - 普通引用

用于较长的引用内容。

```json
"blockquote": "border:none;padding:16px 20px;margin:20px 0;background:#f8f8f8;color:#666;font-size:14px;line-height:1.8;letter-spacing:1px;border-radius:8px;"
```

### quoteCard - 金句卡片

当引用内容**少于100字且只有一个段落**时，自动应用金句卡片样式。

```json
"quoteCard": "background:#fafafa;border:none;padding:20px 24px;margin:25px 0;border-radius:8px;text-align:center;"
```

### quoteCardText - 金句卡片文字

```json
"quoteCardText": "font-size:14px;color:#555;line-height:1.9;letter-spacing:1px;"
```

### quoteCardDecor - 金句装饰引号

在金句卡片上下添加装饰性引号。

```json
"quoteCardDecor": "color:#1a1a1a;font-size:48px;font-family:Georgia,serif;line-height:1;opacity:0.15;"
```

---

## 其他元素

### hr - 分割线

```json
"hr": "border:none;height:1px;background:linear-gradient(to right,rgba(26,26,26,0),rgba(26,26,26,0.3),rgba(26,26,26,0));margin:30px 0;"
```

### a - 链接

```json
"a": "color:#1a1a1a;text-decoration:none;font-weight:600;border-bottom:1px dashed #1a1a1a;"
```

### img - 图片

```json
"img": "max-width:100%;border-radius:4px;margin:15px auto;display:block;"
```

**进阶技巧**：添加阴影效果

```json
"img": "max-width:100%;border-radius:4px;margin:15px auto;display:block;box-shadow:0 4px 12px rgba(0,0,0,0.08);"
```

### imgCaption - 图片说明

当图片后紧跟斜体文字时，自动转为图片说明。

Markdown 语法：
```markdown
![图片描述](图片地址)
*这是图片说明*
```

```json
"imgCaption": "font-size:12px;color:#a3a3a3;text-align:center;margin:8px 0 20px;letter-spacing:1px;"
```

### highlight - 高亮文字

使用 `==文字==` 语法高亮文字（需要扩展支持）。

```json
"highlight": "background:#fff3cd;color:#856404;padding:2px 6px;border-radius:2px;"
```

---

## 暗黑模式

为您的主题添加暗黑模式支持，需要配置以下三个属性：

| 属性 | 说明 | 默认值 |
|------|------|--------|
| `darkBg` | 暗黑模式背景色 | #1a1a1a |
| `darkFg` | 暗黑模式前景色（文字） | #d0d0d0 |
| `darkCard` | 暗黑模式卡片背景色 | #2a2a2a |

```json
{
    "darkBg": "#1a1a1a",
    "darkFg": "#d0d0d0",
    "darkCard": "#2a2a2a"
}
```

---

## 完整示例

以下是一个完整的主题文件示例：

```json
{
    "name": "海洋",
    "dotColor": "#0077b6",
    "brandColor": "#0077b6",
    
    "h1": "font-size:26px;font-weight:900;color:#023e8a;text-align:center;margin:35px 0 25px;letter-spacing:5px;line-height:1.5;",
    "h2": "font-size:17px;font-weight:700;color:#0077b6;margin:28px 0 16px;padding:6px 14px;background:linear-gradient(to right,#e8f4f8 0%,#ffffff 100%);border-left:4px solid #0077b6;line-height:1.6;border-radius:2px;",
    "h3": "font-size:16px;font-weight:700;color:#0096c7;margin:22px 0 12px;padding-left:12px;border-left:2px solid #48cae4;line-height:1.6;",
    "h4": "font-size:15px;font-weight:700;color:#00b4d8;margin:18px 0 10px;line-height:1.6;",
    
    "p": "font-size:15px;color:#1a3a4a;line-height:1.75;margin:15px 0;letter-spacing:1px;text-align:justify;",
    "blockquote": "border:none;padding:16px 20px;margin:20px 0;background:#e8f4f8;color:#0077b6;font-size:14px;line-height:1.8;letter-spacing:1px;border-radius:8px;",
    
    "pre": "background:#023e8a;border-radius:8px;padding:16px;margin:20px 0;overflow-x:auto;",
    "code_block": "color:#caf0f8;font-size:13px;font-family:\"JetBrains Mono\",monospace;line-height:1.7;",
    "code_inline": "background:#e8f4f8;color:#0077b6;padding:2px 6px;border-radius:3px;font-size:13px;font-family:\"JetBrains Mono\",monospace;",
    
    "ul": "margin:15px 0;padding-left:0;color:#1a3a4a;font-size:15px;line-height:1.8;list-style:none;",
    "ol": "margin:15px 0;padding-left:0;color:#1a3a4a;font-size:15px;line-height:1.8;list-style:none;",
    "li": "margin:8px 0;font-size:15px;line-height:1.8;color:#1a3a4a;padding-left:20px;position:relative;",
    
    "table": "width:100%;border-collapse:collapse;margin:20px 0;font-size:14px;border-top:2px solid #0077b6;",
    "th": "background:#e8f4f8;padding:12px 14px;text-align:left;font-weight:700;color:#023e8a;border:none;border-bottom:2px solid #0077b6;font-size:14px;",
    "td": "padding:12px 14px;border:none;border-bottom:1px solid #caf0f8;font-size:14px;color:#1a3a4a;",
    
    "hr": "border:none;height:1px;background:linear-gradient(to right,rgba(0,119,182,0),rgba(0,119,182,0.4),rgba(0,119,182,0));margin:30px 0;",
    "a": "color:#0077b6;text-decoration:none;font-weight:600;border-bottom:1px dashed #48cae4;",
    "img": "max-width:100%;border-radius:6px;margin:15px auto;display:block;box-shadow:0 4px 12px rgba(0,0,0,0.08);",
    
    "strong": "font-weight:700;color:#023e8a;background:linear-gradient(to top,#caf0f8 40%,transparent 40%);padding:0 2px;",
    "em": "font-style:italic;color:#0096c7;",
    
    "quoteCard": "background:#e8f4f8;border:none;padding:20px 24px;margin:25px 0;border-radius:8px;text-align:center;",
    "quoteCardText": "font-size:14px;color:#0077b6;line-height:1.9;letter-spacing:1px;",
    "quoteCardDecor": "color:#0077b6;font-size:48px;font-family:Georgia,serif;line-height:1;opacity:0.2;",
    
    "imgCaption": "font-size:12px;color:#48cae4;text-align:center;margin:8px 0 20px;letter-spacing:1px;",
    "highlight": "background:#caf0f8;color:#023e8a;padding:2px 6px;border-radius:2px;",
    
    "ulPrefix": "color:#0077b6;",
    "olPrefix": "color:#0077b6;font-weight:700;",
    
    "darkBg": "#023e8a",
    "darkFg": "#caf0f8",
    "darkCard": "#0077b6"
}
```

---

## 导入主题

### 方法一：通过菜单导入

1. 点击菜单 `主题` → `导入主题...`
2. 选择您的主题 JSON 文件
3. 导入成功后，主题会自动出现在主题选择栏

### 方法二：直接放入主题目录

1. 打开菜单 `主题` → `打开主题目录`
2. 将您的主题 JSON 文件复制到该目录
3. 重启应用，主题会自动加载

### 注意事项

- 主题文件必须是有效的 JSON 格式
- 文件名不要包含 `template`（模板文件会被忽略）
- 建议使用英文文件名，如 `ocean.json`
- 主题文件编码必须是 UTF-8

---

## 调试技巧

### 在浏览器中预览

1. 启动应用后按 `Ctrl+Shift+I` 打开开发者工具
2. 在 Console 中输入以下代码查看当前主题：

```javascript
console.log(window.themeManager.getCurrentTheme());
```

### 快速测试样式

在开发者工具的 Elements 面板中，可以直接修改元素的 style 属性来测试效果。

---

## 常见问题

### Q: 为什么我的样式没有生效？

A: 检查以下几点：
1. JSON 格式是否正确（可用在线 JSON 验证器检查）
2. CSS 属性是否正确拼写
3. 颜色值是否使用正确格式（#rrggbb 或颜色名）

### Q: 如何让标题使用特殊字体？

A: 在样式中添加 `font-family` 属性：

```json
"h1": "font-size:26px;font-weight:900;color:#1a1a1a;text-align:center;margin:35px 0 25px;letter-spacing:5px;line-height:1.5;font-family:\"Noto Serif SC\",serif;"
```

### Q: 渐变背景如何写？

A: 使用 CSS 的 `linear-gradient`：

```json
"h2": "font-size:17px;font-weight:700;color:#1a1a1a;margin:28px 0 16px;padding:6px 14px;background:linear-gradient(to right,#f5f5f5 0%,#ffffff 100%);border-left:4px solid #1a1a1a;line-height:1.6;"
```

---

如有问题，欢迎提交 Issue 或联系作者。
