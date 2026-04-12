# 素笺 更新日志

## 新功能 (Feat)

- 新增模块化架构，`theme-manager.js` 封装主题加载、解析、渲染逻辑
- 新增 `style-panel.js` 样式面板组件，浮动面板 UI 封装
- 新增 `toast.js` 提示组件，支持成功/错误/信息三种提示类型
- 新增 `onboarding.js` 新手引导组件，6 步引导流程（欢迎页、编辑区、工具栏、暗黑模式、预览区、复制到微信）
- 新增自定义输入对话框 `prompt.css/dialog`，替代 Electron 禁用的 `prompt()` 函数
- 新增菜单项「帮助 > 新手引导」，支持手动重新进入引导

## 修复 (Fix)

- 修复 Electron 渲染进程中 `prompt()` 被禁用的问题
- 修复 `getUserDataDir()` 类型检查和错误处理
- 修复 `themes:save` 预设数据有效性验证
- 修复 `themes:import` 返回读取失败的文件列表
- 修复 `config:set` JSON 解析失败时使用空配置而非崩溃
- 修复 `file:save` 添加 content 类型检查和写入异常处理
- 修复导入主题文件验证必要字段 `name` 和 `palette`

## 优化 (Optimize)

- CSS 模块化拆分，renderer.js 从 1154 行精简到约 420 行
- IPC 通道规范化，统一使用 `:` 分隔命名（如 `themes:list`、`file:save`）
- 用户设置持久化，自动保存配色方案、字体方案、组件样式、暗模式状态
- 全屏菜单添加 F11 快捷键
- 引导步骤位置优化，避免被遮挡
- 最后一步显示"开始使用"按钮

## 重构 (Refactor)

- 三层分离架构：theme-manager（主题管理）、style-panel（UI 组件）、renderer（主控制器）
- CSS 模块化：从单一 styles.css 拆分为 8 个独立模块
- preload.js 重构：统一 API 命名空间

## 其他 (Chore)

- 删除 `src/themes/` 目录（11 个冗余主题文件）
- 删除 `ThemeManager._styleCache` 未使用变量
- 依赖更新：marked.js 11.9.0、highlight.js 11.9.0、Font Awesome 6.5.0
