# 🎮 Vue Tetris Game

> 基于Vue3和HTML5 Canvas的经典俄罗斯方块游戏

![项目状态](https://img.shields.io/badge/状态-开发中-yellow)
![技术栈](https://img.shields.io/badge/Vue-3.0-4FC08D)
![构建工具](https://img.shields.io/badge/Vite-5.0-646CFF)
![语言](https://img.shields.io/badge/TypeScript-5.0-3178C6)

---

## 🎯 项目简介

Vue Tetris Game是一个现代化的俄罗斯方块游戏，使用Vue3 Composition API和HTML5 Canvas技术构建。项目提供流畅的游戏体验，支持桌面和移动设备，包含完整的游戏功能和现代化的用户界面。

### ✨ 核心特性

- 🧩 **经典玩法** - 完整的俄罗斯方块游戏机制
- 🎨 **现代架构** - Vue3 Composition API + TypeScript
- 📱 **响应式设计** - 完美适配桌面和移动设备
- 🎵 **音效系统** - 背景音乐和游戏音效
- 💾 **数据持久化** - 本地存储最高分记录
- ⚡ **高性能渲染** - HTML5 Canvas优化绘制
- 🎮 **多种控制** - 键盘、触摸和鼠标控制

---

## 🛠️ 技术栈

- **前端框架**: Vue 3.4+ (Composition API)
- **构建工具**: Vite 5.0+
- **语言**: TypeScript 5.0+
- **状态管理**: Pinia 2.0+
- **渲染引擎**: HTML5 Canvas
- **样式**: CSS3 + CSS Variables
- **代码规范**: ESLint + Prettier

---

## 🚀 快速开始

### 📋 环境要求

- Node.js 18+ 
- npm 9+ 或 yarn 1.22+
- 现代浏览器 (Chrome 90+, Firefox 88+, Safari 14+)

### ⚡ 安装依赖

```bash
# 克隆项目
git clone <repository-url>
cd vue-tetris-game

# 安装依赖
npm install
# 或
yarn install
```

### 🔧 开发模式

```bash
# 启动开发服务器
npm run dev
# 或
yarn dev

# 项目将在 http://localhost:5173 运行
```

### 📦 生产构建

```bash
# 构建生产版本
npm run build
# 或
yarn build

# 预览构建结果
npm run preview
# 或
yarn preview
```

---

## 🎮 游戏说明

### 🎯 游戏目标
- 控制下降的方块填满水平行
- 填满的行会自动消除并获得分数
- 随着游戏进行，方块下降速度逐渐增加
- 当方块堆积到顶部时游戏结束

### ⌨️ 控制方式

#### 键盘控制
- `← →` 左右移动方块
- `↓` 加速下降
- `↑` / `Space` 旋转方块
- `P` 暂停/继续游戏
- `R` 重新开始游戏

#### 触摸控制
- 左右滑动：移动方块
- 向下滑动：加速下降
- 点击：旋转方块

---

## 📁 项目结构

```
vue-tetris-game/
├── src/
│   ├── components/          # Vue组件
│   │   ├── GameBoard.vue   # 游戏画布
│   │   ├── GameControls.vue # 游戏控制
│   │   ├── ScorePanel.vue  # 分数面板
│   │   └── NextBlock.vue   # 下一个方块预览
│   ├── composables/        # 组合式API
│   │   ├── useGame.ts      # 游戏核心逻辑
│   │   ├── useKeyboard.ts  # 键盘控制
│   │   └── useAudio.ts     # 音效管理
│   ├── stores/             # Pinia状态管理
│   │   ├── game.ts         # 游戏状态
│   │   └── settings.ts     # 设置状态
│   ├── utils/              # 工具函数
│   │   ├── gameLogic.ts    # 游戏逻辑算法
│   │   ├── canvas.ts       # Canvas绘制工具
│   │   └── constants.ts    # 游戏常量
│   └── assets/             # 静态资源
       ├── audio/           # 音频文件
       ├── images/          # 图片资源
       └── styles/          # 样式文件
```

---

## 📚 开发文档

- 📋 [开发任务列表](./doc/todo.md) - 详细的开发计划和进度
- 🏗️ [项目结构说明](./structure.md) - 完整的架构设计文档
- 📖 [变更日志](./CHANGELOG.md) - 版本更新记录
- 🎮 [游戏设计文档](./doc/game-design.md) - 游戏机制和算法说明

---

## 🔧 开发指南

### VS Code推荐插件
- Vue Language Features (Volar)
- TypeScript Vue Plugin (Volar)
- ESLint
- Prettier
- Auto Rename Tag

### 代码规范
项目使用ESLint和Prettier进行代码格式化和质量检查：

```bash
# 代码检查
npm run lint

# 自动修复
npm run lint:fix

# 格式化代码
npm run format
```

---

## 📈 路线图

### 🟡 v1.0 基础版本
- [x] 项目架构设计
- [ ] 基础游戏逻辑
- [ ] 游戏界面实现
- [ ] 键盘控制

### 🔵 v1.1 功能增强
- [ ] 音效系统
- [ ] 移动端适配
- [ ] 数据持久化
- [ ] 关卡系统

### 🟢 v1.2 优化版本
- [ ] 性能优化
- [ ] 代码分割
- [ ] PWA支持
- [ ] 多语言支持

---

## 🤝 贡献指南

欢迎提交Issue和Pull Request！请确保：

1. 遵循现有的代码风格
2. 添加适当的测试用例
3. 更新相关文档
4. 提交前运行代码检查

---

## 📄 许可证

MIT License - 详见 [LICENSE](./LICENSE) 文件

---

## 📞 联系方式

如有问题或建议，请通过以下方式联系：

- 📧 提交 [Issue](../../issues)
- 💬 发起 [Discussion](../../discussions)

---

**🎮 Happy Gaming!**