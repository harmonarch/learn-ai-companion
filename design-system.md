# AI Companion Design System

## 1. 设计定位

当前界面走的是 **轻玻璃感、低压、陪伴型 AI 产品** 路线。

设计关键词：
- 柔和
- 通透
- 低刺激
- 关系感
- 信息层级清楚
- 工具感克制

视觉基调不是效率型后台，也不是娱乐型社交产品，更接近“可长期停留的陪伴式工作台”。

---

## 2. Design Principles

### 2.1 Calm First
整体避免高对比和强攻击性颜色。大面积使用浅白、浅蓝、半透明描边和弱阴影，让界面先传达安全感，再传达功能性。

### 2.2 One Dominant Surface
中间聊天区是主舞台，左侧会话列表和右侧链路摘要都降权处理，只承担辅助浏览和切换作用。

### 2.3 Soft Hierarchy
层级靠字号、字重、透明度、背景明暗差来建立，不靠大量分割线或大块纯色。

### 2.4 Human Over Dashboard
即使右侧有调试/链路摘要，也保持卡片化和温和表达，不做监控面板式压迫感。

### 2.5 Structural Consistency
整个页面统一使用：
- 24px 大容器圆角
- 22px 次级卡片圆角
- 999px 胶囊圆角
- 1px 半透明白色描边
- 轻量背景模糊 + 微弱外阴影

---

## 3. Foundations

### 3.1 Color Tokens

#### Brand / Semantic
| Token | Value | 用途 |
| --- | --- | --- |
| `--primary` | `#FF8400` | 品牌主色、发送按钮、品牌标识、高亮状态 |
| `--foreground` | `#111111` | 主文本 |
| `--muted-foreground` | `#666666` | 次级文本 |
| `--border` | `#CBCCC9` | 语义边框基底 |
| `--card` | `#FFFFFF` | 卡片基底 |
| `--background` | `#F2F3F0` | 系统背景语义值 |

#### Supportive Semantic Tokens
| Token | Light | Dark |
| --- | --- | --- |
| `--color-success` | `#DFE6E1` | `#222924` |
| `--color-warning` | `#E9E3D8` | `#291C0F` |
| `--color-error` | `#E5DCDA` | `#24100B` |
| `--color-info` | `#DFDFE6` | `#222229` |

#### 当前界面实际使用的重点颜色
| 语义 | Value | 说明 |
| --- | --- | --- |
| 品牌橙 | `#FF8400` | logo、主行动感知 |
| 主文本黑 | `#111111` | 标题、正文主信息 |
| 次文本灰 | `#666666` | 标签、时间、弱说明 |
| 弱提示灰蓝 | `#8B93A1` | 在线状态、时间补充信息 |
| 功能灰 | `#6F7785` | 次级图标 |
| 机器人蓝字 | `#315273` | 陪伴回复正文 |
| 蓝色身份色 | `#315B89` | 陪伴对象头像字 |
| 用户橙棕 | `#8C4B23` | 用户头像字 |
| 训练提示橙 | `#B56A09` | 输入区训练标签 |
| 标签橙文案 | `#C78734` | 轻训练文案 |
| 绿色身份色 | `#2F6D4B` | 情绪树洞类角色 |

### 3.2 Surface Gradients

当前系统不是纯白卡片，而是大量使用浅梯度玻璃面。

#### 页面背景 Mesh Gradient
建议保留大画布多点柔光背景：
- `#F9FBFF`
- `#E6EEFF`
- `#F2E7FF`
- `#FFF1F8`
- `#E8FAFF`
- `#D8F3FF`
- `#F4EAFF`
- `#FFF8EF`
- `#EEF9FF`

#### 一级容器背景
适用于顶部导航、左列、聊天主卡、右列：
- 起点接近 `#FFFFFFD8 ~ #FFFFFFC4`
- 中段接近 `#FCFEFFD0 ~ #FFFFFF9B`
- 终点接近 `#F4FAFFD4 ~ #FFFFFF70`
- 旋转角度主要使用 `150deg`

#### 二级卡片背景
适用于列表项、摘要项：
- 默认中性玻璃卡：`#FFFFFF9A → #FFFFFF62 → #FFFFFF32`
- 激活蓝卡：`#DCEBFFCC → #A8C8FFB8`
- 调试列外卡片：`#FCFDFFD8 → #F4F8FFC2 → #EAF1FF9E`
- 输入区卡片：`#FFFEFD → #FFFBF8 → #FEF5EE`

### 3.3 Typography

#### Font Family
| Token | Value | 用途 |
| --- | --- | --- |
| `--font-primary` | `JetBrains Mono` | 结构标题、标签、技术感信息 |
| `--font-secondary` | `Geist` | 业务文本、对话内容、状态说明 |

#### Type Scale
| Size | Weight | 典型用途 |
| --- | --- | --- |
| 18 | 700 | 顶部区块标题、栏标题 |
| 16 | 600 / normal | 对话正文、用户名、输入内容 |
| 15 | 600 / 700 | 列表标题、头像字符 |
| 13 | 500 / normal | 列表说明、状态文案、摘要正文 |
| 12 | 700 / 500 / normal | 标签、时间、辅助说明、导航项 |

#### Typography Rules
- **JetBrains Mono** 负责“系统感”和“信息结构感”。
- **Geist** 负责“对话感”和“产品可读性”。
- 标题尽量短，标签尽量单行。
- 正文多用 13–16px，避免更小字号承载主要内容。

### 3.4 Radius
| Token | Value | 用途 |
| --- | --- | --- |
| `--radius-none` | `0` | 结构占位 |
| `--radius-m` | `16` | 语义基础圆角 |
| `--radius-pill` | `999` | 胶囊、头像、icon button |

#### 当前界面实际圆角层级
- `24px`：一级容器、消息气泡、输入器外壳
- `22px`：列表项、摘要项
- `999px`：头像、导航 pill、圆形 icon 按钮、状态标签

### 3.5 Spacing
当前设计里的主要 spacing scale：
- `2`
- `4`
- `6`
- `8`
- `12`
- `14`
- `16`
- `18`
- `20`

建议映射：
| Spacing | 用途 |
| --- | --- |
| 2 | 紧贴型文本组、导航内文案间距 |
| 4 | 标签组、卡片内部标题与描述 |
| 6 | 在线状态、短状态组合 |
| 8 | 列表垂直堆叠、操作按钮组 |
| 12 | 卡片内部默认内容间距 |
| 14 | 聊天气泡外层节奏 |
| 16 | 栏容器 padding、主区块间距 |
| 18 | 大段消息组垂直间距 |
| 20 | 主内容横向 padding |

### 3.6 Border & Effects

#### Border
- 默认 `1px`
- 颜色为半透明白：`#FFFFFF80`、`#FFFFFF8E`、`#FFFFFFA8`、`#FFFFFFB0`、`#FFFFFFD9`
- 目标不是分隔，而是增加玻璃边缘感

#### Effects
- `background_blur`: `8 / 12 / 14 / 16 / 18 / 20`
- 外阴影 blur 以 `10 / 12 / 16 / 18 / 22` 为主
- 阴影颜色偏蓝白或暖橙，透明度低

效果原则：
- 阴影只做“悬浮感”，不做“厚重感”
- 模糊只做“柔化边缘”，不做强玻璃拟物

---

## 4. Layout System

### 4.1 Overall Shell
当前桌面端主画布：
- Frame: `1440 × 980`
- 外层 padding: `16`
- 主区块 gap: `16`
- 三栏结构

### 4.2 Column Structure
| 区域 | 宽度 | 角色 |
| --- | --- | --- |
| 顶部导航 | 高 `72` | 全局模式切换 |
| 左侧会话栏 | `258` | 会话浏览与切换 |
| 中间聊天区 | 自适应填充 | 主交互区 |
| 右侧链路摘要 | `252` | 低干扰调试信息 |

### 4.3 Visual Hierarchy
- 中间聊天区占最大视觉权重
- 左右两侧都使用相同圆角与玻璃表面，但内容密度更高、字号更小
- 右侧调试区默认弱化，只保留摘要，不抢聊天注意力

### 4.4 Container Rules
一级容器统一规则：
- `cornerRadius: 24`
- 浅色梯度背景
- `1px` 半透明白色描边
- 轻背景模糊
- 弱外阴影

二级卡片统一规则：
- `cornerRadius: 22`
- `padding: 12`
- `gap: 4` 或 `12`
- 低对比浅渐变背景

---

## 5. Component System

### 5.1 Brand Header
组成：
- 左侧品牌 icon
- 品牌名
- 胶囊式导航切换

规则：
- 品牌使用橙色
- 导航容器使用 48px 高的 pill 容器
- 激活项更亮、更实，未激活项降低不透明度

### 5.2 Navigation Pill
#### Active
- 白色更强的梯度面
- 更亮描边
- 黑色图标 + 深色文字
- 带轻阴影

#### Inactive
- 更淡的透明梯度
- 透明度约 `0.82`
- 图标与文字用灰色系

### 5.3 Conversation Rail Card
用于左侧最近互动列表。

结构：
- 左：圆形角色徽标 44 × 44
- 右：标题 + 时间 + 一行说明
- 整卡 `padding: 12`
- `cornerRadius: 22`

变体：
- **Active / Companion**：蓝色玻璃卡
- **Neutral**：中性白色玻璃卡
- **Emotion / Support**：绿色头像底色识别角色类型

### 5.4 Avatar Badge
规则：
- 圆形
- 文本通常单字
- 字体使用 JetBrains Mono 700
- 尺寸 40 或 44
- 用背景色区分角色，不靠额外图形

### 5.5 Chat Header
结构：
- 左：对象头像 + 名称 + 在线状态
- 右：三个圆形 icon button

规则：
- 头像 40 × 40
- 在线状态文本使用 13px Geist
- 工具按钮 32 × 32，胶囊圆角，弱玻璃底

### 5.6 Message Bubble
#### Assistant Bubble
- 蓝色浅梯度背景
- 正文文本颜色偏蓝灰
- `cornerRadius: 24`
- `padding: 14 16`
- 固定宽度约 `360`

#### User Bubble
- 暖粉橙渐变背景
- 文本颜色更深
- 同样使用 `24px` 圆角
- 右对齐

#### Meta Pattern
每条消息建议拆成：
- 头像 / 发送者
- 名称 + 时间
- 气泡正文

### 5.7 Composer Shell
输入器是底部高优先级操作区。

规则：
- `cornerRadius: 24`
- 暖白渐变背景
- `padding: 16`
- 主输入内容 16px
- 左下保留辅助状态标签
- 右侧发送按钮使用品牌橙渐变

### 5.8 Icon Button
尺寸体系：
- 32 × 32：头部轻操作
- 40 × 40：输入区次操作
- 44 × 44：发送按钮 / 强动作

规则：
- 全部圆角 999
- 统一使用半透明浅底或品牌色渐变底
- 避免纯描边空心按钮

### 5.9 Status Chip
用于“轻训练 ON”之类的弱提示。

规则：
- pill 造型
- 小图标 + 12px 文案
- 低对比浅底
- 橙色文案用于轻提醒，不用于警报

### 5.10 Debug Summary Panel
右侧调试摘要不是技术后台，而是“温和摘要卡”。

结构：
- 面板标题
- 多个摘要项纵向堆叠
- 每个摘要项含：标签 + 1~2 行解释

规则：
- 外层卡片比左侧和中间更浅、更冷
- 内层摘要项统一 22px 圆角、12px padding
- 标题使用 JetBrains Mono 18/700
- 标签使用 JetBrains Mono 12/700
- 正文使用 Geist 13/500

---

## 6. Content Rules

### 6.1 文案语气
- 短句
- 不喊口号
- 不做强运营感文案
- 以陪伴、引导、解释为主

### 6.2 信息密度
- 左侧列表每卡最多两行核心信息
- 右侧摘要每卡最多一个标签 + 一段结论
- 中间消息内容允许更自然的句子长度

### 6.3 状态表达
状态建议保持轻量：
- 在线
- 聊天中
- 正在输入
- 轻训练 ON

避免使用高压术语，比如警报、告警、严重错误，除非确实是系统故障场景。

---

## 7. Theme Guidance

文件里已经预留 `Mode = Light / Dark` 主题轴。

### Light Mode
当前设计已基本成型，核心特征：
- 白蓝雾面背景
- 白色半透明边框
- 黑字灰字组合
- 蓝橙绿作为角色和状态识别色

### Dark Mode
当前只存在 token，界面样式还没完整落地。后续落地时建议保留这些关系：
- 仍使用低饱和品牌橙作强调
- 背景走深灰蓝，不走纯黑
- 卡片继续保留半透明与轻描边逻辑
- 文本层级维持“高亮白 / 次级灰 / 状态色”三层关系

---

## 8. Implementation Heuristics

### 8.1 适合复用的组件
优先抽成组件：
- Navigation Pill
- Conversation Rail Card
- Avatar Badge
- Message Bubble
- Icon Button
- Status Chip
- Summary Item Card

### 8.2 不建议过度抽象的部分
- 不同角色头像色
- 不同消息气泡色
- 调试摘要具体内容块

这些更适合基于同一骨架做 variant，而不是完全独立组件。

### 8.3 前端实现建议
适合映射成以下 token 层：
- color tokens
- typography tokens
- radius tokens
- spacing tokens
- shadow / blur presets
- component variants

建议在代码里拆成：
- `surface-primary`
- `surface-secondary`
- `surface-active-blue`
- `surface-warm-input`
- `surface-debug`

---

## 9. Quick Spec

### App Shell
- canvas: `1440 × 980`
- outer padding: `16`
- main gap: `16`

### Panel
- radius: `24`
- padding: `16`
- border: `1px translucent white`
- fill: light glass gradient

### Secondary Card
- radius: `22`
- padding: `12`
- gap: `4 / 12`

### Bubble
- radius: `24`
- padding: `14 16`
- width: `360`

### Pill / Circular Control
- radius: `999`
- sizes: `32 / 40 / 44`

### Type Pair
- structural: `JetBrains Mono`
- content: `Geist`

---

## 10. 一句话定义

这套 Design System 的核心，不是做一个“功能很多的聊天界面”，而是做一个 **看起来温和、信息分层清楚、适合长期互动的陪伴型 AI 工作台**。
