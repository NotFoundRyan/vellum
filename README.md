# 素笺 - 微信公众号排版工具

一款优雅的 Markdown 排版工具，专为微信公众号创作者打造。

## 功能特色

- **实时预览** - 左侧编辑，右侧即时渲染，所见即所得
- **配色与样式分离** - 独立选择配色方案和组件样式，组合出个性化风格
- **一键复制** - 渲染后的富文本可直接粘贴到微信公众号编辑器
- **代码高亮** - 支持多种编程语言语法高亮
- **新手引导** - 首次使用提供全程引导，快速上手
- **主题预设** - 支持导入/导出预设组合
- **文件操作** - 支持新建、打开、保存 Markdown 文件
- **导出 HTML** - 可导出渲染后的 HTML 文件

## 界面预览

应用采用温暖的牛皮纸风格，契合"素笺"的书卷气质。左侧为 Markdown 编辑器 + 工具栏，右侧为手机框预览模拟微信文章效果，浮动面板用于选择配色与组件样式。

## 新手引导

首次启动应用将自动进入新手引导，共 6 个步骤。如已关闭，可通过菜单 **帮助 > 新手引导** 重新进入。

| 步骤 | 内容 | 图片 |
|------|------|------|
| 1 | 欢迎页 - 介绍应用功能 | ![](https://raw.githubusercontent.com/NotFoundRyan/Sujian/main/docs/pics/Onboarding-01-Welcome.png) |
| 2 | 编辑区 - Markdown 文本输入 | ![](https://raw.githubusercontent.com/NotFoundRyan/Sujian/main/docs/pics/Onboarding-02-Editor.png) |
| 3 | 工具栏 - 格式快捷操作 | ![](https://raw.githubusercontent.com/NotFoundRyan/Sujian/main/docs/pics/Onboarding-03-Toolbar.png) |
| 4 | 暗黑模式 - 切换预览主题 | ![](https://raw.githubusercontent.com/NotFoundRyan/Sujian/main/docs/pics/Onboarding-04-DarkMode.png) |
| 5 | 预览区 - 手机端效果预览 | ![](https://raw.githubusercontent.com/NotFoundRyan/Sujian/main/docs/pics/Onboarding-05-Preview.png) |
| 6 | 复制到微信 - 一键复制富文本 | ![](https://raw.githubusercontent.com/NotFoundRyan/Sujian/main/docs/pics/Onboarding-06-Copy.png) |

## 配色方案

| 配色 | 风格特点 |
|------|---------|
| **素雅** | 极简黑白，经典耐看 |
| **暖阳** | 温暖橙棕，复古文艺 |
| **墨竹** | 清新绿色，自然雅致 |
| **星河** | 梦幻紫色，现代科技 |
| **杂志** | 红黑撞色，报刊风格 |
| **文艺** | 米色暖调，书卷气息 |
| **莫兰迪** | 低饱和灰调，高级冷淡风 |

## 快捷键

| 快捷键 | 功能 |
|--------|------|
| `Ctrl+N` | 新建文档 |
| `Ctrl+O` | 打开文件 |
| `Ctrl+S` | 保存文件 |
| `Ctrl+E` | 导出 HTML |
| `F11` | 全屏切换 |
| `Tab` | 插入 4 空格缩进 |

## 工具栏功能

| 按钮 | 功能 | Markdown 语法 |
|------|------|---------------|
| **B** | 加粗 | `**文字**` |
| *I* | 斜体 | `*文字*` |
| H1/H2/H3 | 标题 | `# ` `## ` `### ` |
| 引用 | 引用块 | `> ` |
| 代码 | 行内代码 | `` `代码` `` |
| 终端 | 代码块 | ` ``` ` |
| 链接 | 超链接 | `[文字](url)` |
| 图片 | 图片 | `![描述](url)` |
| 列表 | 无序/有序列表 | `- ` `1. ` |
| 分割线 | 水平线 | `---` |
| 表格 | 表格模板 | `| 列1 | 列2 |` |

## 特殊语法

### 金句卡片

短引用（少于 100 字）会自动渲染为居中的金句卡片样式：

```markdown
> 好的排版不是装饰，而是对读者的尊重。
```

### 图片说明

图片后紧跟的斜体文字会自动转为图片说明：

```markdown
![图片](url)
*这是图片说明*
```

## 技术栈

- **Electron** - 跨平台桌面应用框架
- **Marked** - Markdown 解析器
- **Highlight.js** - 代码语法高亮
- **Font Awesome** - 图标库
- **Noto Serif SC** - 中文衬线字体
- **JetBrains Mono** - 等宽代码字体

## 常见问题

### 复制到微信后样式丢失？

微信公众号编辑器会过滤部分样式。素笺已针对微信兼容性优化：所有样式使用内联 `style` 属性，代码高亮颜色直接写入元素，不依赖外部 CSS 文件。

### 如何重置新手引导？

通过菜单 **帮助 > 新手引导** 可随时重新查看。

### 支持哪些 Markdown 语法？

支持标准 GFM（GitHub Flavored Markdown）语法，包括：标题、段落、引用、加粗、斜体、删除线、有序/无序列表、代码块、行内代码、表格、链接、图片、水平分割线。

## 作者

Ryan
