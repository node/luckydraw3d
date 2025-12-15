# 3D 抽奖系统 (3D Lucky Draw System)

这是一个基于 Web 技术构建的现代化、炫酷的 3D 抽奖系统，专为企业年会、活动现场设计。支持离线运行，数据本地存储，无需配置后端服务器。

## ✨ 主要特性

*   **炫酷 3D 视觉效果**：使用 Three.js 构建的 3D 球体动画，每个参与者都是一张独立的卡片。
*   **多格式数据导入**：支持 Excel (`.xlsx`, `.xls`) 和纯文本 (`.txt`) 文件导入，也可直接复制粘贴手动录入。
*   **灵活的抽奖设置**：支持自定义奖项名称、单次抽取数量，可选择是否排除已中奖用户。
*   **实时中奖记录**：左侧侧边栏实时显示中奖历史，支持清空和重置。
*   **数据持久化**：所有数据（用户名单、配置、中奖记录）均保存在浏览器本地存储 (LocalStorage)，刷新页面不丢失，防误触关闭保护。
*   **响应式与可调整 UI**：侧边栏宽度支持鼠标拖拽调整，适应不同分辨率屏幕。
*   **离线可用**：下载依赖库后可完全离线运行（默认使用 CDN）。

## 🚀 快速开始

### 在线/联网使用
1.  直接用现代浏览器（Chrome, Edge, Firefox, Safari）打开 `index.html` 文件。
2.  系统会自动加载演示数据，点击“开始抽奖”即可体验。

### 离线使用
如果活动现场没有网络，请预先下载以下依赖库并修改 `index.html` 中的引用路径：
*   **Vue 3**: `vue.esm-browser.js`
*   **Three.js**: `three.module.js`
*   **Three.js CSS3DRenderer**: `CSS3DRenderer.js`
*   **Tailwind CSS**: `tailwindcss.js` (或编译后的 CSS)
*   **SheetJS**: `xlsx.full.min.js`
*   **Animate.css**: `animate.min.css`

## 📂 目录结构

遵循 KISS (Keep It Simple, Stupid) 原则设计。

> **注意**：为了解决浏览器对本地文件 (`file://`) 的跨域安全限制，`index.html` 已经内联了所有业务逻辑代码，支持**直接双击运行**。
> `js/` 和 `css/` 目录保留作为**开发源码**，供阅读和维护。

```text
zedwork/
├── index.html          # [发布版] 集成所有代码，可离线直接运行
├── css/
│   └── style.css       # [源码] 自定义样式表
├── js/
│   ├── main.js         # [源码] Vue 应用主逻辑
│   ├── store.js        # [源码] 数据状态管理
│   └── visuals.js      # [源码] Three.js 3D 渲染逻辑
└── README.md           # 项目文档
```

## 📝 数据导入格式

点击设置面板中的 **“设置/数据”** 按钮进行导入。

### 1. Excel 导入
支持 `.xlsx` 或 `.xls` 文件。
*   **第一列**：姓名 (必填)
*   **第二列**：部门/工号/描述 (选填)
*   *系统会自动识别首行是否为标题行。*

| 姓名 | 部门 |
| :--- | :--- |
| 张三 | 技术部 |
| 李四 | 运营部 |

### 2. TXT 文本导入
支持 `.txt` 文件，每行一个姓名。

```text
张三
李四
王五
```

## 🛠️ 技术栈

*   **核心框架**: [Vue.js 3](https://vuejs.org/) (ESM build)
*   **3D 引擎**: [Three.js](https://threejs.org/) (CSS3DRenderer)
*   **样式库**: [Tailwind CSS](https://tailwindcss.com/) (CDN Script) + [Animate.css](https://animate.style/)
*   **工具库**: [SheetJS (xlsx)](https://sheetjs.com/)

## ⚠️ 注意事项

1.  **浏览器兼容性**：请使用支持 ES Modules 的现代浏览器。
2.  **数据安全**：数据存储在本地浏览器中，清理浏览器缓存会丢失数据。建议正式使用前先备份人员名单。
3.  **性能**：建议参与人数在 10-500 人范围内以获得最佳 3D 渲染性能。
