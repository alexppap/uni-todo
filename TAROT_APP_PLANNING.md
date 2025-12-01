# 塔罗牌占卜小程序规划文档

## 一、项目概述

### 1.1 项目定位
基于 **uni-app x** 框架开发的跨平台塔罗牌占卜应用，支持微信小程序、支付宝小程序、App（Android/iOS）等多端运行。提供专业的塔罗牌占卜服务，包括每日一抽、多种牌阵占卜、塔罗学习等功能。

### 1.2 目标用户
- 塔罗牌爱好者
- 寻求心灵指引的用户
- 对占卜文化感兴趣的年轻群体（18-35岁为主）
- 学习塔罗牌的初学者

### 1.3 核心价值
- **便捷性**：随时随地进行塔罗占卜
- **专业性**：提供准确的牌义解读和多种经典牌阵
- **记录性**：保存历史占卜记录，追踪个人成长
- **学习性**：塔罗知识库，帮助用户深入了解塔罗文化

---

## 二、功能规划

### 2.1 核心功能模块

#### 2.1.1 首页（Dashboard）
- **每日一抽**
  - 每日限一次免费抽取
  - 展示今日运势卡牌
  - 提供简要解读
  - 支持分享到社交平台

- **快速占卜入口**
  - 爱情占卜
  - 事业占卜
  - 学业占卜
  - 财运占卜
  - 健康占卜

- **精选内容**
  - 塔罗小知识
  - 每日星座运势
  - 推荐牌阵

#### 2.1.2 占卜模块
- **牌阵选择**
  - 单张抽取（快速占卜）
  - 三角牌阵（过去-现在-未来）
  - 凯尔特十字牌阵（深度分析）
  - 时间之流牌阵（时间线分析）
  - 爱情牌阵（关系专项）
  - 决策牌阵（选择题）
  - 自定义牌阵

- **占卜流程**
  1. 选择占卜主题/问题
  2. 输入具体问题（可选）
  3. 选择牌阵类型
  4. 冥想/净化环节（动画引导）
  5. 抽牌交互（翻牌动画）
  6. 展示结果和解读
  7. 保存记录

- **结果展示**
  - 卡牌展示（正位/逆位）
  - 牌面含义解读
  - 综合分析
  - 建议与指引
  - 支持语音朗读（可选）

#### 2.1.3 塔罗牌库
- **完整牌库**
  - 大阿卡纳（22张）
  - 小阿卡纳（56张）：权杖、圣杯、宝剑、星币

- **卡牌详情**
  - 高清牌面图
  - 正位含义
  - 逆位含义
  - 象征意义
  - 关键词
  - 背景故事
  - 相关星座/元素

- **牌库功能**
  - 分类浏览
  - 搜索功能
  - 收藏喜欢的牌
  - 学习模式（随机测试）

#### 2.1.4 历史记录
- **记录列表**
  - 按时间倒序展示
  - 显示占卜主题、牌阵类型、日期
  - 支持筛选（按主题、牌阵）
  - 支持搜索

- **记录详情**
  - 查看完整占卜结果
  - 添加笔记/心得
  - 标记重要记录
  - 分享记录

- **数据统计**
  - 占卜次数统计
  - 最常抽到的牌
  - 占卜主题分布
  - 月度/年度报告

#### 2.1.5 学习中心
- **塔罗入门**
  - 塔罗历史
  - 如何选牌
  - 如何解读
  - 常见误区

- **牌义学习**
  - 系统化课程
  - 每日一牌学习
  - 牌义记忆卡片
  - 互动测试

- **牌阵教学**
  - 各类牌阵详解
  - 适用场景
  - 解读技巧
  - 案例分析

#### 2.1.6 个人中心
- **用户信息**
  - 头像/昵称设置
  - 出生日期（用于个性化占卜）
  - 星座信息

- **我的收藏**
  - 收藏的卡牌
  - 收藏的文章

- **设置**
  - 占卜提醒
  - 音效开关
  - 震动反馈
  - 主题切换（日间/夜间）
  - 隐私设置
  - 关于我们

### 2.2 特色功能

#### 2.2.1 AI 智能解读（可选）
- 基于用户输入的问题，提供个性化解读
- 结合多张牌的关联性分析
- 更贴合用户实际情况的建议

#### 2.2.2 社区功能（后期规划）
- 占卜分享广场
- 用户交流讨论
- 塔罗师入驻
- 在线咨询服务

#### 2.2.3 冥想音乐
- 占卜前冥想引导
- 多种舒缓背景音乐
- 白噪音选择

---

## 三、技术架构

### 3.1 技术栈

#### 前端框架
- **uni-app x**: 下一代跨平台开发框架
- **Vue 3**: 使用组合式 API (`<script setup>`)
- **TypeScript (UTS)**: 类型安全的逻辑代码
- **SCSS**: 样式预处理

#### 状态管理
- **Pinia**: Vue 3 官方推荐的状态管理库
- 模块化 store 设计

#### 数据存储
- **本地存储**: uni.storage（用户设置、历史记录）
- **云数据库**: uniCloud（可选，用于数据同步和备份）

#### 动画和交互
- **CSS3 动画**: 卡牌翻转、过渡效果
- **Canvas**: 自定义抽牌动画
- **uni-ui 组件库**: 基础 UI 组件

### 3.2 项目目录结构

```
uni-todo/
├── pages/                      # 页面目录
│   ├── index/                 # 首页
│   │   └── index.uvue
│   ├── divination/            # 占卜相关页面
│   │   ├── spread-select.uvue    # 牌阵选择
│   │   ├── question-input.uvue   # 问题输入
│   │   ├── meditation.uvue       # 冥想引导
│   │   ├── draw-cards.uvue       # 抽牌页面
│   │   └── result.uvue           # 结果展示
│   ├── cards/                 # 牌库相关
│   │   ├── library.uvue          # 牌库列表
│   │   └── detail.uvue           # 卡牌详情
│   ├── history/               # 历史记录
│   │   ├── list.uvue             # 记录列表
│   │   └── detail.uvue           # 记录详情
│   ├── learn/                 # 学习中心
│   │   ├── index.uvue            # 学习首页
│   │   ├── lesson.uvue           # 课程详情
│   │   └── test.uvue             # 互动测试
│   └── profile/               # 个人中心
│       ├── index.uvue            # 个人中心首页
│       └── settings.uvue         # 设置页面
│
├── components/                 # 公共组件
│   ├── TarotCard.uvue         # 塔罗牌卡片组件
│   ├── CardFlip.uvue          # 翻牌动画组件
│   ├── SpreadLayout.uvue      # 牌阵布局组件
│   ├── InterpretCard.uvue     # 解读卡片组件
│   └── AudioPlayer.uvue       # 音频播放组件
│
├── composables/               # 组合式函数
│   ├── useTarotDeck.uts       # 塔罗牌数据逻辑
│   ├── useDivination.uts      # 占卜逻辑
│   ├── useHistory.uts         # 历史记录逻辑
│   └── useAnimation.uts       # 动画控制逻辑
│
├── stores/                    # Pinia 状态管理
│   ├── user.uts               # 用户信息
│   ├── cards.uts              # 牌库数据
│   ├── divination.uts         # 占卜状态
│   └── settings.uts           # 应用设置
│
├── data/                      # 静态数据
│   ├── major-arcana.uts       # 大阿卡纳数据
│   ├── minor-arcana.uts       # 小阿卡纳数据
│   ├── spreads.uts            # 牌阵数据
│   └── interpretations.uts    # 解读文本数据
│
├── utils/                     # 工具函数
│   ├── shuffle.uts            # 洗牌算法
│   ├── storage.uts            # 存储封装
│   ├── date.uts               # 日期处理
│   └── share.uts              # 分享功能
│
├── static/                    # 静态资源
│   ├── images/
│   │   ├── cards/             # 塔罗牌图片（78张）
│   │   │   ├── major/         # 大阿卡纳
│   │   │   └── minor/         # 小阿卡纳
│   │   ├── bg/                # 背景图
│   │   └── icons/             # 图标
│   ├── audio/                 # 音频文件
│   │   ├── bgm/               # 背景音乐
│   │   └── sfx/               # 音效
│   └── fonts/                 # 字体文件
│
├── App.uvue                   # 应用入口
├── main.uts                   # 主文件
├── pages.json                 # 页面路由配置
├── manifest.json              # 应用配置
├── uni.scss                   # 全局样式变量
└── CLAUDE.md                  # 项目说明
```

### 3.3 核心技术实现

#### 3.3.1 洗牌算法
使用 **Fisher-Yates 洗牌算法**确保随机性：
```typescript
function shuffleDeck(deck: Card[]): Card[] {
  const shuffled = [...deck];
  for (let i = shuffled.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
  }
  return shuffled;
}
```

#### 3.3.2 正逆位判断
抽牌时随机决定正逆位（可配置概率）：
```typescript
function drawCard(deck: Card[]): DrawnCard {
  const card = deck[Math.floor(Math.random() * deck.length)];
  const isReversed = Math.random() < 0.5; // 50% 概率逆位
  return { ...card, isReversed };
}
```

#### 3.3.3 翻牌动画
使用 CSS3 3D 变换实现翻牌效果：
```scss
.card-flip {
  perspective: 1000px;

  .card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    transform-style: preserve-3d;
    transition: transform 0.8s cubic-bezier(0.4, 0.0, 0.2, 1);

    &.flipped {
      transform: rotateY(180deg);
    }
  }
}
```

#### 3.3.4 数据持久化
封装 storage 工具类：
```typescript
class TarotStorage {
  // 保存占卜记录
  async saveDivinationRecord(record: DivinationRecord): Promise<void> {
    const records = await this.getRecords();
    records.unshift(record);
    uni.setStorageSync('divination_records', records);
  }

  // 获取历史记录
  async getRecords(): Promise<DivinationRecord[]> {
    return uni.getStorageSync('divination_records') || [];
  }
}
```

---

## 四、数据模型设计

### 4.1 核心数据结构

#### 4.1.1 塔罗牌数据结构
```typescript
interface Card {
  id: string;                    // 唯一标识
  name: string;                  // 中文名称
  nameEn: string;                // 英文名称
  type: 'major' | 'minor';       // 大/小阿卡纳
  suit?: 'wands' | 'cups' | 'swords' | 'pentacles'; // 牌组（小阿卡纳）
  number: number;                // 编号
  imageUrl: string;              // 图片路径
  keywords: string[];            // 关键词
  uprightMeaning: string;        // 正位含义
  reversedMeaning: string;       // 逆位含义
  description: string;           // 详细描述
  symbolism: string[];           // 象征意义
  element?: string;              // 对应元素
  astrology?: string;            // 对应星座
}
```

#### 4.1.2 牌阵数据结构
```typescript
interface Spread {
  id: string;                    // 牌阵 ID
  name: string;                  // 牌阵名称
  description: string;           // 描述
  cardCount: number;             // 需要卡牌数量
  positions: SpreadPosition[];   // 牌位定义
  category: string;              // 分类（爱情/事业/通用等）
  difficulty: 'easy' | 'medium' | 'hard'; // 难度
  imageUrl?: string;             // 牌阵示意图
}

interface SpreadPosition {
  index: number;                 // 位置索引
  name: string;                  // 位置名称（如"过去"、"现在"）
  description: string;           // 位置含义说明
  x: number;                     // 布局 x 坐标（百分比）
  y: number;                     // 布局 y 坐标（百分比）
  rotation?: number;             // 旋转角度
}
```

#### 4.1.3 占卜记录数据结构
```typescript
interface DivinationRecord {
  id: string;                    // 记录 ID
  userId?: string;               // 用户 ID（如果有登录）
  timestamp: number;             // 占卜时间戳
  spreadId: string;              // 使用的牌阵 ID
  spreadName: string;            // 牌阵名称
  category: string;              // 占卜类别
  question?: string;             // 用户问题
  drawnCards: DrawnCard[];       // 抽到的牌
  interpretation: string;        // 综合解读
  notes?: string;                // 用户笔记
  isImportant?: boolean;         // 是否标记为重要
  tags?: string[];               // 标签
}

interface DrawnCard {
  card: Card;                    // 卡牌信息
  position: SpreadPosition;      // 所在牌位
  isReversed: boolean;           // 是否逆位
}
```

#### 4.1.4 用户数据结构
```typescript
interface UserProfile {
  id: string;                    // 用户 ID
  nickname: string;              // 昵称
  avatar: string;                // 头像
  birthday?: string;             // 生日
  zodiac?: string;               // 星座
  preferences: UserPreferences;  // 偏好设置
  stats: UserStats;              // 统计数据
}

interface UserPreferences {
  theme: 'light' | 'dark';       // 主题
  soundEnabled: boolean;         // 音效开关
  vibrationEnabled: boolean;     // 震动反馈
  dailyReminder: boolean;        // 每日提醒
  reminderTime?: string;         // 提醒时间
}

interface UserStats {
  totalDivinations: number;      // 总占卜次数
  favoriteCards: string[];       // 最常抽到的牌
  joinDate: number;              // 加入时间
  longestStreak: number;         // 最长连续占卜天数
}
```

### 4.2 静态数据示例

#### 大阿卡纳数据示例
```typescript
const majorArcana: Card[] = [
  {
    id: 'major_00',
    name: '愚者',
    nameEn: 'The Fool',
    type: 'major',
    number: 0,
    imageUrl: '/static/images/cards/major/00_fool.png',
    keywords: ['新开始', '冒险', '纯真', '自由'],
    uprightMeaning: '代表新的开始、冒险精神和无限可能。鼓励你跟随内心，勇敢迈出第一步。',
    reversedMeaning: '可能暗示鲁莽、缺乏计划或逃避责任。需要更加谨慎和理性。',
    description: '愚者是塔罗牌的第一张或第零张牌，象征着旅程的开始...',
    symbolism: ['白玫瑰：纯洁', '小狗：忠诚伙伴', '悬崖：未知的冒险'],
    element: '风',
    astrology: '天王星'
  },
  // ... 其他 21 张大阿卡纳
];
```

#### 牌阵数据示例
```typescript
const spreads: Spread[] = [
  {
    id: 'spread_past_present_future',
    name: '时间三角',
    description: '最经典的三张牌阵，揭示过去、现在和未来的能量流动',
    cardCount: 3,
    category: '通用',
    difficulty: 'easy',
    positions: [
      {
        index: 0,
        name: '过去',
        description: '过去的影响和经历',
        x: 20,
        y: 50,
        rotation: 0
      },
      {
        index: 1,
        name: '现在',
        description: '当前的状态和挑战',
        x: 50,
        y: 50,
        rotation: 0
      },
      {
        index: 2,
        name: '未来',
        description: '未来的发展趋势',
        x: 80,
        y: 50,
        rotation: 0
      }
    ]
  },
  // ... 其他牌阵
];
```

---

## 五、UI/UX 设计规范

### 5.1 设计风格

#### 视觉风格
- **神秘主义**：深色调为主，营造神秘氛围
- **优雅简洁**：避免过度装饰，保持界面清晰
- **现代感**：符合年轻用户审美

#### 配色方案

**深色主题（默认）**
- 主色：`#6A4C93`（深紫色）
- 辅助色：`#FFB400`（金色）
- 背景色：`#1A1A2E`（深蓝黑）
- 卡片背景：`#16213E`（深蓝灰）
- 文字主色：`#FFFFFF`
- 文字副色：`#B8B8D1`

**浅色主题**
- 主色：`#8B5FBF`（紫色）
- 辅助色：`#FFB400`（金色）
- 背景色：`#F5F5F5`
- 卡片背景：`#FFFFFF`
- 文字主色：`#333333`
- 文字副色：`#666666`

#### 字体规范
- 标题：思源黑体 / PingFang SC Medium
- 正文：苹方 / PingFang SC Regular
- 数字：DIN Alternate Bold
- 英文：Cinzel（装饰性标题）

### 5.2 关键页面设计要点

#### 5.2.1 首页
- 顶部：用户头像 + 每日一抽卡片（大卡片展示）
- 中部：快速占卜入口（网格布局，6个分类）
- 底部：精选内容流（横向滚动）
- 导航栏：首页、牌库、历史、学习、我的

#### 5.2.2 抽牌页面
- 全屏沉浸式体验
- 卡牌背面展示（可点击翻转）
- 星空粒子动效背景
- 翻牌有音效和震动反馈
- 优雅的翻转动画（800ms）

#### 5.2.3 结果页面
- 顶部：展示所有抽到的牌（小卡片）
- 中部：当前查看的牌详情
- 底部：综合解读 + 建议
- 支持左右滑动切换不同牌位
- 底部操作栏：保存、分享、重新占卜

### 5.3 交互细节

#### 动效设计
- 页面切换：淡入淡出 + 轻微缩放
- 卡片翻转：3D 翻转效果
- 按钮点击：轻微缩放反馈
- 加载状态：优雅的骨架屏或星空动画

#### 反馈机制
- 触觉反馈：重要操作时震动
- 音效反馈：抽牌、翻牌、保存等操作
- 视觉反馈：按钮状态变化、Toast 提示

---

## 六、开发计划

### 6.1 开发阶段划分

#### 第一阶段：MVP 核心功能（2-3周）
**目标**：实现基本占卜功能，可以完成完整的占卜流程

**任务清单**：
1. **基础架构搭建**
   - 初始化 uni-app x 项目
   - 配置 pages.json 路由
   - 搭建 Pinia store
   - 创建公共组件

2. **数据准备**
   - 整理 78 张塔罗牌数据
   - 准备卡牌图片资源
   - 定义 3-5 个基础牌阵

3. **核心页面开发**
   - 首页（简化版）
   - 牌阵选择页
   - 抽牌页面
   - 结果展示页
   - 历史记录列表

4. **核心功能实现**
   - 洗牌算法
   - 抽牌逻辑
   - 翻牌动画
   - 本地存储历史记录
   - 基础解读展示

#### 第二阶段：完善体验（2-3周）
**目标**：优化用户体验，增加辅助功能

**任务清单**：
1. **功能完善**
   - 每日一抽功能
   - 添加更多牌阵（7-10个）
   - 完善解读内容
   - 添加问题输入功能

2. **牌库模块**
   - 牌库列表页
   - 卡牌详情页
   - 搜索和筛选
   - 收藏功能

3. **个人中心**
   - 用户信息设置
   - 偏好设置
   - 数据统计展示

4. **UI/UX 优化**
   - 优化动画效果
   - 添加背景音乐和音效
   - 适配深色/浅色主题
   - 完善加载和错误状态

#### 第三阶段：学习与社区（2周）
**目标**：增加学习功能，提升用户粘性

**任务清单**：
1. **学习中心**
   - 塔罗入门教程
   - 每日一牌学习
   - 牌义测试功能

2. **增强功能**
   - 冥想引导页面
   - 分享功能完善
   - 占卜笔记功能
   - 月度报告生成

3. **性能优化**
   - 图片懒加载
   - 代码分包优化
   - 减少包体积

#### 第四阶段：高级功能（后续迭代）
**可选功能**：
- AI 智能解读
- 云端数据同步
- 社区功能
- 塔罗师入驻
- 付费咨询服务

### 6.2 技术难点和解决方案

#### 6.2.1 卡牌资源管理
**难点**：78 张高清卡牌图片较大，影响加载速度和包体积

**解决方案**：
- 使用图片压缩工具优化图片大小（推荐 WebP 格式）
- 实现图片懒加载
- 首次只加载常用牌，其他按需加载
- 考虑使用 CDN 托管图片

#### 6.2.2 复杂牌阵布局
**难点**：不同牌阵有不同的布局方式，需要灵活的布局系统

**解决方案**：
- 使用绝对定位 + 百分比坐标系统
- 封装 SpreadLayout 组件，根据牌阵数据动态渲染
- 支持自定义旋转角度和间距

#### 6.2.3 翻牌动画性能
**难点**：多张卡牌同时翻转可能导致性能问题

**解决方案**：
- 使用 CSS3 硬件加速（transform3d）
- 避免同时触发过多动画
- 使用 requestAnimationFrame 优化动画
- 考虑使用 Canvas 实现复杂动画

#### 6.2.4 数据持久化
**难点**：历史记录可能较多，本地存储有限制

**解决方案**：
- 本地只保留最近 100 条记录
- 提供导出功能（JSON 格式）
- 后期接入云存储服务（uniCloud）

#### 6.2.5 跨平台兼容性
**难点**：不同平台（小程序/App）API 和表现可能不一致

**解决方案**：
- 使用 uni-app x 的条件编译
- 封装平台相关 API
- 充分测试各平台表现

---

## 七、数据埋点和分析

### 7.1 关键指标

#### 用户行为指标
- DAU/MAU（日活/月活）
- 占卜次数/用户
- 页面停留时长
- 功能使用率

#### 业务指标
- 每日一抽完成率
- 不同牌阵使用率
- 历史记录查看率
- 分享转化率

### 7.2 埋点计划
- 页面浏览事件
- 按钮点击事件
- 占卜完成事件
- 分享事件
- 异常事件

---

## 八、上线准备

### 8.1 小程序上线检查清单

#### 微信小程序
- [ ] 注册小程序账号
- [ ] 配置服务器域名
- [ ] 隐私政策和用户协议
- [ ] 内容审核（避免敏感词汇）
- [ ] 提交审核（注意类目选择）

#### 其他平台
- [ ] 支付宝小程序适配
- [ ] 百度小程序适配
- [ ] 字节跳动小程序适配

### 8.2 App 上线
- [ ] Android 签名配置
- [ ] iOS 证书配置
- [ ] 应用市场资料准备
- [ ] 隐私政策和权限说明

### 8.3 运营准备
- [ ] 推广素材准备
- [ ] 社交媒体账号
- [ ] 用户反馈渠道
- [ ] 版本更新计划

---

## 九、风险和挑战

### 9.1 合规风险
- **内容审核**：塔罗占卜属于边缘内容，需要注意表述方式
  - 避免宣传封建迷信
  - 强调娱乐和心理引导属性
  - 添加免责声明

### 9.2 技术风险
- **性能问题**：大量图片和动画可能影响性能
- **兼容性问题**：不同平台表现差异
- **数据安全**：用户隐私保护

### 9.3 运营风险
- **用户留存**：如何保持用户活跃度
- **内容更新**：持续提供新鲜内容
- **竞品压力**：市场已有类似产品

---

## 十、总结

### 10.1 项目亮点
1. **技术先进**：采用 uni-app x 框架，性能优越
2. **跨平台支持**：一次开发，多端运行
3. **专业内容**：完整的 78 张塔罗牌和多种牌阵
4. **优质体验**：精美 UI 和流畅动画
5. **学习功能**：不仅是占卜工具，也是学习平台

### 10.2 成功关键因素
- 精准的用户定位
- 专业的内容质量
- 流畅的交互体验
- 持续的功能迭代
- 有效的运营推广

### 10.3 后续规划
- 根据用户反馈持续优化
- 探索商业化可能（会员、咨询服务）
- 建设用户社区
- 拓展更多占卜方式（如星座、生肖等）

---

## 附录

### A. 参考资源
- 塔罗牌在线资料库
- uni-app x 官方文档：https://doc.dcloud.net.cn/uni-app-x/
- Vue 3 官方文档
- 设计参考：Dribbble, Behance

### B. 关键技术文档
- Fisher-Yates 洗牌算法
- CSS 3D 变换
- Canvas 动画
- uni-app x 性能优化指南

### C. 竞品分析
- 类似产品功能对比
- 差异化竞争策略

---

**文档版本**：v1.0
**创建日期**：2025-11-29
**最后更新**：2025-11-29
