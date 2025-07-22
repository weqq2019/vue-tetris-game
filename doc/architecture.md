# 🏗️ Vue Tetris Game - 项目架构设计

> **版本**: v1.0  
> **更新时间**: 2025-07-22  
> **用途**: 项目架构设计和目录结构规划

---

## 🎯 架构概览

Vue Tetris Game采用现代化前端架构，基于Vue3 Composition API + HTML5 Canvas，实现高性能的游戏渲染和流畅的用户交互体验。

### 🔧 技术选型理由

- **Vue3 Composition API** - 更好的逻辑复用和类型推导
- **TypeScript** - 类型安全和更好的开发体验  
- **HTML5 Canvas** - 高性能图形渲染
- **Pinia** - 轻量级状态管理
- **Vite** - 快速开发构建工具

---

## 📁 目标项目结构设计

```
vue-tetris-game/
├── 📋 配置文件
│   ├── package.json           # 项目依赖和脚本
│   ├── vite.config.ts         # Vite构建配置
│   ├── tsconfig.json          # TypeScript配置
│   ├── eslint.config.js       # 代码规范配置
│   └── .gitignore             # Git忽略文件
├── 📝 项目文档
│   ├── README.md              # 项目说明
│   ├── CHANGELOG.md           # 变更日志
│   ├── structure.md           # 项目结构 (实时)
│   ├── CLAUDE.md              # Claude Code规范
│   └── doc/
│       ├── todo.md            # 开发任务
│       ├── architecture.md    # 架构设计 (本文件)
│       ├── game-design.md     # 游戏设计文档
│       └── api.md             # 游戏API文档
├── 🎮 源码目录
│   ├── src/
│   │   ├── components/        # Vue组件
│   │   │   ├── GameBoard.vue  # 游戏画布组件
│   │   │   ├── GameControls.vue # 游戏控制组件
│   │   │   ├── ScorePanel.vue # 分数面板
│   │   │   ├── NextBlock.vue  # 下一个方块预览
│   │   │   └── common/        # 通用组件
│   │   │       ├── Button.vue # 按钮组件
│   │   │       └── Modal.vue  # 弹窗组件
│   │   ├── composables/       # 组合式API
│   │   │   ├── useGame.ts     # 游戏核心逻辑
│   │   │   ├── useKeyboard.ts # 键盘控制
│   │   │   ├── useAudio.ts    # 音效管理
│   │   │   └── useCanvas.ts   # Canvas渲染
│   │   ├── stores/            # Pinia状态管理
│   │   │   ├── game.ts        # 游戏状态
│   │   │   ├── settings.ts    # 设置状态
│   │   │   └── leaderboard.ts # 排行榜状态
│   │   ├── utils/             # 工具函数
│   │   │   ├── gameLogic.ts   # 游戏逻辑算法
│   │   │   ├── canvas.ts      # Canvas绘制工具
│   │   │   ├── constants.ts   # 游戏常量
│   │   │   ├── storage.ts     # 本地存储
│   │   │   └── helpers.ts     # 通用辅助函数
│   │   ├── types/             # TypeScript类型定义
│   │   │   ├── game.ts        # 游戏相关类型
│   │   │   ├── canvas.ts      # Canvas相关类型
│   │   │   └── api.ts         # API相关类型
│   │   ├── assets/            # 静态资源
│   │   │   ├── audio/         # 音频文件
│   │   │   │   ├── bgm.mp3    # 背景音乐
│   │   │   │   ├── move.wav   # 移动音效
│   │   │   │   ├── rotate.wav # 旋转音效
│   │   │   │   ├── clear.wav  # 消除音效
│   │   │   │   └── gameover.wav # 游戏结束音效
│   │   │   ├── images/        # 图片资源
│   │   │   │   ├── blocks/    # 方块纹理
│   │   │   │   ├── bg/        # 背景图片
│   │   │   │   └── ui/        # UI图标
│   │   │   └── styles/        # 样式文件
│   │   │       ├── base.css   # 基础样式
│   │   │       ├── game.css   # 游戏样式
│   │   │       └── responsive.css # 响应式样式
│   │   ├── App.vue            # 根组件
│   │   └── main.ts            # 入口文件
│   ├── public/                # 公共资源
│   │   ├── favicon.ico        # 网站图标
│   │   ├── robots.txt         # 爬虫配置
│   │   └── manifest.json      # PWA配置
│   └── index.html             # HTML模板
├── 🧪 测试文件
│   ├── tests/                 # 测试目录
│   │   ├── unit/              # 单元测试
│   │   ├── e2e/               # 端到端测试
│   │   └── setup.ts           # 测试配置
│   └── vitest.config.ts       # 测试工具配置
└── 🛠️ 开发工具
    ├── vue-tetris-game.code-workspace # VS Code工作区
    └── project-rules-cn/      # 开发规范
```

---

## 🏗️ 架构分层设计

### 📱 表现层 (Presentation Layer)
- **Vue组件** - 负责UI渲染和用户交互
- **Canvas渲染** - 游戏画面绘制和动画效果
- **响应式设计** - 适配不同设备和屏幕尺寸

### 🧠 逻辑层 (Business Logic Layer)  
- **Composables** - 封装业务逻辑的组合函数
- **Game Logic** - 游戏核心算法和规则实现
- **State Management** - Pinia状态管理和数据流

### 💾 数据层 (Data Layer)
- **Local Storage** - 本地数据持久化
- **Game State** - 游戏状态和配置管理
- **Audio Assets** - 音频资源加载和管理

---

## 🎮 核心模块设计

### 🎯 游戏引擎 (Game Engine)
```typescript
// useGame.ts - 游戏核心逻辑
interface GameEngine {
  board: GameBoard           // 游戏面板
  currentBlock: Tetromino    // 当前方块
  nextBlock: Tetromino       // 下一个方块
  score: number              // 分数
  level: number              // 关卡
  lines: number              // 消除行数
  
  // 核心方法
  update(): void             // 游戏循环更新
  moveBlock(direction): void // 移动方块
  rotateBlock(): void        // 旋转方块
  dropBlock(): void          // 方块下降
  clearLines(): void         // 消除满行
}
```

### 🎨 渲染引擎 (Render Engine)
```typescript
// useCanvas.ts - Canvas渲染管理
interface RenderEngine {
  canvas: HTMLCanvasElement  // Canvas元素
  context: CanvasRenderingContext2D // 绘制上下文
  
  // 渲染方法
  drawBoard(): void          // 绘制游戏面板
  drawBlock(block): void     // 绘制方块
  drawGrid(): void           // 绘制网格
  animate(): void            // 动画循环
}
```

### 🔊 音效引擎 (Audio Engine)
```typescript
// useAudio.ts - 音效管理
interface AudioEngine {
  bgm: HTMLAudioElement      // 背景音乐
  sfx: Map<string, HTMLAudioElement> // 音效集合
  
  // 音效方法
  playBGM(): void            // 播放背景音乐
  playSFX(name): void        // 播放音效
  setVolume(volume): void    // 设置音量
  mute(): void               // 静音切换
}
```

### ⌨️ 输入系统 (Input System)
```typescript
// useKeyboard.ts - 键盘控制
interface InputSystem {
  keyMap: Map<string, Function> // 按键映射
  
  // 输入方法
  bindKeys(): void           // 绑定按键事件
  handleKeyDown(event): void // 处理按键按下
  handleKeyUp(event): void   // 处理按键释放
}
```

---

## 📊 状态管理设计

### 🎮 游戏状态 (Game Store)
```typescript
// stores/game.ts
interface GameState {
  // 游戏数据
  board: number[][]          // 游戏面板 (10x20)
  currentBlock: Tetromino    // 当前方块
  nextBlocks: Tetromino[]    // 下几个方块队列
  heldBlock: Tetromino | null // 保留方块
  
  // 游戏统计
  score: number              // 当前分数
  lines: number              // 消除行数
  level: number              // 当前关卡
  time: number               // 游戏时间
  
  // 游戏状态
  isPlaying: boolean         // 是否正在游戏
  isPaused: boolean          // 是否暂停
  isGameOver: boolean        // 是否游戏结束
}
```

### ⚙️ 设置状态 (Settings Store)
```typescript
// stores/settings.ts
interface SettingsState {
  // 音效设置
  musicVolume: number        // 音乐音量 (0-1)
  sfxVolume: number          // 音效音量 (0-1)
  isMuted: boolean           // 是否静音
  
  // 控制设置
  keyBindings: KeyBindings   // 按键绑定
  autoRepeat: boolean        // 自动重复
  dropDelay: number          // 下降延迟
  
  // 显示设置
  showGrid: boolean          // 显示网格
  showGhost: boolean         // 显示预览
  theme: string              // 主题名称
}
```

---

## 🎯 组件设计规范

### 📱 组件职责划分
- **GameBoard.vue** - 游戏主画布，负责Canvas渲染
- **GameControls.vue** - 游戏控制，按钮和设置面板
- **ScorePanel.vue** - 分数显示，游戏统计信息
- **NextBlock.vue** - 下一个方块预览
- **Settings.vue** - 游戏设置，音效和控制配置

### 🔄 组件通信模式
- **Props Down** - 父组件向子组件传递数据
- **Events Up** - 子组件向父组件发送事件
- **Store Shared** - 通过Pinia共享全局状态
- **Provide/Inject** - 跨层级组件通信

---

## ⚡ 性能优化策略

### 🎨 Canvas优化
- **RequestAnimationFrame** - 使用标准动画循环
- **Dirty Rectangle** - 只重绘变化区域
- **Off-screen Canvas** - 预渲染复杂图形
- **图层分离** - 分离静态和动态内容

### 🧠 逻辑优化
- **Computed Properties** - 缓存计算结果
- **Event Delegation** - 减少事件监听器
- **Lazy Loading** - 按需加载资源
- **Code Splitting** - 代码分割和懒加载

### 💾 内存优化
- **Object Pooling** - 对象池复用
- **Event Cleanup** - 及时清理事件监听
- **Resource Management** - 音频和图片资源管理

---

## 🚀 部署架构

### 📦 构建配置
- **Vite Production Build** - 生产环境优化构建
- **Asset Optimization** - 静态资源压缩和优化
- **Code Splitting** - 按路由和功能分割代码
- **Tree Shaking** - 移除未使用代码

### 🌐 部署方案
- **Static Hosting** - 静态文件托管 (Netlify/Vercel)
- **CDN Distribution** - 全球CDN加速
- **PWA Support** - 渐进式Web应用支持
- **Offline Capability** - 离线使用能力

---

## 📱 响应式设计

### 🖥️ 桌面端 (Desktop)
- **大屏游戏区域** - 充分利用屏幕空间
- **完整控制面板** - 所有功能和设置可见
- **键盘优化** - 主要使用键盘控制

### 📱 移动端 (Mobile)
- **垂直布局** - 适配手机屏幕比例
- **触摸控制** - 手势和虚拟按键
- **响应式字体** - 自适应文字大小

### 📟 平板端 (Tablet)
- **混合布局** - 介于桌面和移动之间
- **触摸+键盘** - 支持多种输入方式
- **灵活控制** - 可配置的控制方案

---

## 🔧 开发工具配置

### 📝 代码规范
- **ESLint** - JavaScript/TypeScript代码检查
- **Prettier** - 代码格式化工具
- **Husky** - Git Hooks自动化
- **Commitizen** - 规范化提交信息

### 🧪 测试配置
- **Vitest** - 单元测试框架
- **Vue Test Utils** - Vue组件测试
- **Cypress** - 端到端测试
- **Coverage Report** - 测试覆盖率报告

---

**🎮 基于此架构设计，Vue Tetris Game将成为一个高质量的现代化游戏项目！**