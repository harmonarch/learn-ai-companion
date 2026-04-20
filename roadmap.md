# AI 电子伴侣 - 学习路线图 (Roadmap)

> 基于教程 https://aicompanion.usehook.cn/
> 最后更新：2026-04-20
> 教程状态：共 136 章，已新增 Vercel AI SDK 专题（Ch116-136）

---

## 学习路径总览

```
Phase 1          Phase 2          Phase 3          Phase 4          Phase 5          Phase 6          Phase 7
理论认知 ──────▶ LangChain ─────▶ LangGraph ─────▶ Monorepo ──────▶ Hono.js ───────▶ Zod 契约层 ───▶ Vercel AI SDK
(Ch01-20)        (Ch21-43)        (Ch44-61)        (Ch62-75)        (Ch76-101)       (Ch102-115)      (Ch116-136)
   │                │                │                │                │                │                │
   │   AI 思维建立   │   原子能力     │   编排能力      │   工程化能力    │   部署能力      │   数据契约能力   │   交互协议 / UI / MCP
   │   架构认知      │   工具链掌握   │   状态管理      │   协作能力      │   全栈能力      │   结构化输出     │   端到端重构
   ▼                ▼                ▼                ▼                ▼                ▼                ▼
  基础             基础→进阶         进阶→高级         基础→进阶        基础→进阶         进阶            进阶→高级
```

---

## Phase 1: 理论基础与技术选型（Ch01-20）

**目标**：建立 AI Agent 开发的完整认知框架，理解"为什么这样做"

**难度**：🟢 基础 → 🟠 进阶

### 核心章节

| 章节 | 标题 | 难度 | 重点标记 |
|------|------|------|---------|
| Ch01 | AI 时代的学习心法 | 🟢 | 认知心态 |
| Ch02 | 什么是 AI 智能体开发 | 🟢 | **必读** - Agent 四大核心能力 |
| Ch03 | 从需求出发, 理解 AI 电子伴侣 | 🟢 | **必读** - 五道工程鸿沟 |
| Ch04 | 内存调度思考 | 🔴 | **⭐ 核心难点** - Memory Scheduler |
| Ch05 | LangChain/LangGraph 核心角色 | 🟠 | **必读** - 两者协作关系 |
| Ch06 | 向量化与语义检索 | 🟠 | **⭐ 重点** - Embedding 原理 |
| Ch07 | 情绪状态机设计 | 🔴 | **⭐ 核心难点** - FSM 设计 |
| Ch08 | Prompt 工程深度实践 | 🟠 | **⭐ 重点** - 动态 Prompt |
| Ch09 | 混合记忆架构设计 | 🔴 | **⭐ 核心难点** - 多记忆源协调 |
| Ch10 | LangGraph Agent 编排管线 | 🔴 | **⭐ 核心难点** - 管线设计 |
| Ch11 | 边缘部署与集群部署对比 | 🟠 | **重点** - 部署架构决策 |
| Ch12 | Hono.js vs FastAPI 技术选型 | 🟢 | 选型理由 |
| Ch13 | 三端架构与 Monorepo 决策 | 🟠 | **重点** - 架构决策 |
| Ch14 | Monorepo 落地与公共逻辑设计 | 🟠 | 共享代码设计 |
| Ch15 | Streaming | 🟠 | **重点** - 流式响应 |
| Ch16 | 可观测性 | 🟢 | 概念理解 |
| Ch17 | LangSmith vs Langfuse vs 自建 | 🟢 | 工具选型 |
| Ch18 | Workers 下的 Tracing 实现 | 🟠 | 边缘 Tracing |
| Ch19 | 指标体系与线上排障 | 🟠 | 生产运维 |
| Ch20 | 影子模式与灰度验证 | 🟠 | 上线策略 |

### Milestone 1 检查点

- [ ] 能画出四层架构图并解释每层职责
- [ ] 能说清五道工程鸿沟及其对应解决方案
- [ ] 理解 Memory Scheduler 的 OS 类比（CPU/RAM/硬盘/内核）
- [ ] 理解 LangChain（肢体）vs LangGraph（大脑）的分工
- [ ] 理解边缘部署 vs 集群部署的 trade-off

### ⚠️ 常见卡点

1. **Ch04 内存调度** —— 容易停留在概念层面。建议结合 Ch09 混合记忆架构一起理解，先画数据流图
2. **Ch07 情绪状态机** —— 需要有限状态机(FSM)基础知识。如果不熟悉，先学习 FSM 基本概念
3. **Ch10 Agent 编排** —— 与 Phase 3 的 LangGraph 深度关联，第一遍可以先理解概念，实战时回来精读

---

## Phase 2: LangChain 深度学习（Ch21-43）

**目标**：掌握 LangChain 的原子能力，能独立构建单 Agent 应用

**难度**：🟢 基础 → 🟠 进阶

**前置要求**：Phase 1 完成

### 架构总览（Ch21-24）

| 章节 | 标题 | 难度 | 重点标记 |
|------|------|------|---------|
| Ch21 | 从 Agent 开始 | 🟢 | 入门概念 |
| Ch22 | 从单 Agent 到多 Agent | 🟢 | 演进路径 |
| Ch23 | LangChain 与单 Agent | 🟢 | LangChain 定位 |
| Ch24 | LangGraph 与多步骤流程 | 🟢 | LangGraph 定位 |

### LangChain 核心（Ch25-43）

| 章节 | 标题 | 难度 | 重点标记 |
|------|------|------|---------|
| Ch25 | 概述 | 🟢 | |
| Ch26 | 环境搭建与第一次调用 | 🟢 | **动手** |
| Ch27 | ChatModel 与消息协议 | 🟢 | 基础概念 |
| Ch28 | Prompt Template 设计体系 | 🟠 | **⭐ 重点** |
| Ch29 | Few-Shot 与动态 Prompt | 🟠 | **⭐ 重点** |
| Ch30 | Output Parser：结构化数据 | 🟠 | **重点** |
| Ch31 | LCEL 与 Runnable 协议 | 🟠 | **⭐ 核心** - 链式调用基础 |
| Ch32 | LCEL 进阶：并行处理 | 🟠 | 并行能力 |
| Ch33 | LCEL 进阶：分支路由 | 🟠 | 条件分支 |
| Ch34 | LCEL 进阶：容错机制 | 🟠 | 生产必备 |
| Ch35 | Memory：让对话拥有记忆 | 🟠 | **⭐ 重点** |
| Ch36 | 记忆持久化与混合策略 | 🔴 | **⭐ 核心难点** |
| Ch37 | Document Loader 与文本分割 | 🟢 | RAG 前置 |
| Ch38 | Embedding 与向量存储 | 🟠 | **⭐ 重点** |
| Ch39 | RAG 管线：检索增强生成 | 🔴 | **⭐ 核心难点** |
| Ch40 | Tool 定义与函数调用 | 🟠 | **重点** |
| Ch41 | 单个 Agent 调用多个工具 | 🟠 | **重点** |
| Ch42 | Middleware：运行规则 | 🟠 | 安全层 |
| Ch43 | Tracing：运行过程可视化 | 🟢 | 调试能力 |

### Milestone 2 检查点

- [ ] 能独立搭建 LangChain 环境并完成第一次 LLM 调用
- [ ] 掌握 LCEL 链式调用（包含并行、分支、容错）
- [ ] 能构建一个带 Memory 的多轮对话 Agent
- [ ] 能完成一个完整的 RAG 管线（文档加载 → 分割 → Embedding → 检索 → 生成）
- [ ] 能给 Agent 定义工具并实现函数调用

### ⚠️ 常见卡点

1. **LCEL (Ch31-34)** —— Runnable 协议理解是关键。建议多写代码，理解 pipe、parallel、branch 的组合方式
2. **RAG 管线 (Ch37-39)** —— 文本分割策略直接影响检索质量。注意 chunk_size 和 overlap 的调参
3. **Memory 持久化 (Ch36)** —— 需要理解不同 Memory 类型的适用场景：BufferMemory / SummaryMemory / VectorStoreMemory

### 💡 推荐实践

> 构建一个"智能笔记助手"：导入 Markdown 文档 → 向量化 → 支持自然语言检索 → 多轮对话

---

## Phase 3: LangGraph 编排能力（Ch44-61）⭐ 最高难度阶段

**目标**：掌握有状态图编排，能设计多 Agent 协作系统

**难度**：🟠 进阶 → 🔴 高级

**前置要求**：Phase 2 完成（LCEL、Memory、Tool Calling）

| 章节 | 标题 | 难度 | 重点标记 |
|------|------|------|---------|
| Ch44 | 概述：从 Chain 到 Graph | 🟢 | 范式转换理解 |
| Ch45 | StateGraph 基础 | 🟠 | **⭐ 核心** - 节点、边、图 |
| Ch46 | 状态管理进阶：Reducer | 🟠 | **⭐ 重点** - 数据流 |
| Ch47 | 条件路由 | 🟠 | **⭐ 重点** - 动态决策 |
| Ch48 | Checkpointer：持久化 | 🔴 | **⭐ 核心难点** - 时间旅行 |
| Ch49 | 用 LangGraph 构建 ReAct Agent | 🟠 | **⭐ 重点** - 实战 |
| Ch50 | 流式输出 | 🟠 | 生产必备 |
| Ch51 | Command 与 Send | 🔴 | **难点** - 高级控制流 |
| Ch52 | interrupt：暂停与恢复 | 🔴 | **难点** |
| Ch53 | Human-in-the-Loop | 🟠 | **实战** - 审批工作流 |
| Ch54 | 子图 | 🟠 | 模块化复用 |
| Ch55 | 多 Agent：Supervisor 模式 | 🔴 | **⭐ 核心难点** |
| Ch56 | 多 Agent：Handoff 与 Swarm | 🔴 | **⭐ 核心难点** |
| Ch57 | 多 Agent：层级团队并行 | 🔴 | **⭐ 核心难点** |
| Ch58 | Store：跨会话长期记忆 | 🔴 | **⭐ 核心难点** |
| Ch59 | 错误处理与容错 | 🟠 | 生产必备 |
| Ch60 | **实战：重构 AI 伴侣管线** | 🔴 | **⭐⭐ 最关键实战章** |
| Ch61 | Graph 运行时上下文 | 🟠 | 进阶理解 |

### Milestone 3 检查点

- [ ] 能构建一个基本的 StateGraph（节点 + 条件路由 + 状态流转）
- [ ] 理解并实现 Checkpointer（状态持久化、断点恢复）
- [ ] 能构建 ReAct Agent（推理-行动循环）
- [ ] 理解三种多 Agent 模式的区别和适用场景
- [ ] **完成 Ch60 实战：用 LangGraph 重构完整的 AI 伴侣管线**

### ⚠️ 常见卡点

1. **StateGraph vs Chain 思维转换 (Ch44-45)** —— 从线性思维到图思维。建议先画状态图再写代码
2. **Checkpointer (Ch48)** —— 理解"时间旅行"概念。实际是状态快照 + 回溯
3. **多 Agent 模式选择 (Ch55-57)** —— 三种模式容易混淆：
   - **Supervisor**：中心调度者分配任务
   - **Handoff/Swarm**：Agent 间自主传递控制权
   - **层级团队**：多层 Supervisor + 并行执行
4. **Ch60 综合实战** —— 需要将前面所有知识融合，建议反复阅读

### 💡 推荐实践

> 构建一个"多角色对话系统"：一个 Supervisor Agent 调度"记忆检索 Agent"、"情绪分析 Agent"、"回复生成 Agent"协作完成对话

---

## Phase 4: Monorepo 工程化（Ch62-75）

**目标**：掌握大型项目的工程化组织，建立协作规范

**难度**：🟢 基础 → 🟠 进阶

**前置要求**：基本的 Node.js/TypeScript 项目经验

| 章节 | 标题 | 难度 | 重点标记 |
|------|------|------|---------|
| Ch62 | monorepo 是什么 | 🟢 | 概念 |
| Ch63 | 基础概念区分 | 🟢 | |
| Ch64 | AI 应用为啥适合 monorepo | 🟢 | 决策理由 |
| Ch65 | 搭一个最小 monorepo | 🟢 | **动手** |
| Ch66 | workspace | 🟢 | 基础配置 |
| Ch67 | 依赖管理 | 🟠 | **重点** - 版本一致性 |
| Ch68 | 共享代码怎么拆 | 🟠 | **⭐ 重点** - 架构设计 |
| Ch69 | 内部包要不要 build | 🟠 | 构建策略 |
| Ch70 | 多运行环境 | 🟠 | 环境差异 |
| Ch71 | Turborepo：任务编排 | 🟠 | **⭐ 重点** |
| Ch72 | turbo.json 进阶 | 🟠 | 进阶配置 |
| Ch73 | 构建缓存和远程缓存 | 🟠 | 性能优化 |
| Ch74 | CI/CD 集成 | 🟠 | **重点** - 部署流水线 |
| Ch75 | 最容易踩的坑 | 🟠 | **⭐ 必读** - 避坑指南 |

### Milestone 4 检查点

- [ ] 能从零搭建一个最小 Monorepo（apps + packages）
- [ ] 理解 workspace 和依赖管理机制
- [ ] 能合理拆分共享代码为 packages
- [ ] 掌握 Turborepo 任务编排和缓存策略
- [ ] 能配置 CI/CD 流水线

### ⚠️ 常见卡点

1. **依赖冲突 (Ch67)** —— Monorepo 下多包的依赖版本需要统一，否则会有"幽灵依赖"
2. **共享代码边界 (Ch68)** —— 拆分粒度：太粗导致耦合，太细导致管理成本高
3. **踩坑 (Ch75)** —— 建议提前阅读，避免在实操中浪费时间

---

## Phase 5: Hono.js 与 Cloudflare（Ch76-101）

**目标**：掌握 Hono.js 全栈开发与 CloudFlare Workers 部署

**难度**：🟢 基础 → 🟠 进阶

**前置要求**：基本的 Web API 开发经验

| 章节 | 标题 | 难度 | 重点标记 |
|------|------|------|---------|
| Ch76 | Hono 是什么 | 🟢 | |
| Ch77 | Cloudflare Workers | 🟢 | 平台理解 |
| Ch78 | 第一个 Hono 应用 | 🟢 | **动手** |
| Ch79 | 路由系统 | 🟢 | |
| Ch80 | Context 与请求响应 | 🟢 | |
| Ch81 | 中间件 | 🟠 | **重点** |
| Ch82 | 数据校验 | 🟠 | Zod 集成 |
| Ch83 | 错误处理 | 🟠 | |
| Ch84 | 认证 | 🟠 | **⭐ 重点** - 身份校验 |
| Ch85 | 鉴权 | 🟠 | **⭐ 重点** - 权限控制 |
| Ch86 | Cloudflare KV | 🟠 | **重点** - 边缘存储 |
| Ch87 | Cloudflare D1 | 🟠 | **重点** - 关系数据库 |
| Ch88 | D1 + Drizzle ORM | 🟠 | **⭐ 重点** - ORM 实战 |
| Ch89 | Cloudflare R2 | 🟢 | 对象存储 |
| Ch90 | RPC 客户端 | 🟠 | **⭐ 重点** - 端到端类型安全 |
| Ch91 | 流式响应与 SSE | 🟠 | **⭐ 重点** - AI 流式 |
| Ch92 | 项目结构与环境管理 | 🟠 | 工程实践 |
| Ch93 | **实战：用户系统 REST API** | 🟠 | **⭐ 实战** |
| Ch94 | **实战：AI API 网关** | 🔴 | **⭐⭐ 核心实战** |
| Ch95 | Workers AI 与 AI Gateway | 🟠 | **重点** - 边缘 AI |
| Ch96 | Vectorize 与 RAG 实战 | 🔴 | **⭐ 核心难点** - 边缘 RAG |
| Ch97 | Durable Objects 与 WebSocket | 🔴 | **难点** - 实时通信 |
| Ch98 | Queues 与 Cron 定时任务 | 🟠 | 异步任务 |
| Ch99 | 缓存策略 | 🟠 | 性能优化 |
| Ch100 | 日志与可观测性 | 🟠 | 生产运维 |
| Ch101 | Hono 与 Next.js 集成 | 🟠 | **⭐ 收官** - 前后端打通 |

### Milestone 5 检查点

- [ ] 能用 Hono.js 创建基本的 REST API
- [ ] 掌握 CloudFlare 存储三件套（KV + D1 + R2 / Vectorize）
- [ ] 实现 Hono RPC 端到端类型安全调用
- [ ] 能实现流式响应（SSE）
- [ ] 完成用户系统 REST API 实战
- [ ] 完成 AI API 网关实战
- [ ] 实现边缘 RAG 检索
- [ ] 理解 Hono 与 Next.js 的集成边界

### ⚠️ 常见卡点

1. **CF Workers 环境限制** —— 不支持 Node.js 所有 API，部分 npm 包不兼容
2. **D1 的 SQLite 方言差异** —— 和 MySQL/PostgreSQL 有语法差异
3. **Durable Objects (Ch97)** —— 概念较新，理解"有状态的边缘对象"需要时间
4. **Vectorize (Ch96)** —— 需要结合 Phase 2 的 RAG 知识
5. **Hono / Next.js 集成 (Ch101)** —— 需要同时理解 RPC、部署边界、类型共享

---

## Phase 6: Zod 数据契约与结构化输出（Ch102-115）

**目标**：掌握以 Zod 为中心的数据契约设计，把前端、服务端与 LLM 输出统一到一套 schema 上

**难度**：🟠 进阶

**前置要求**：Phase 4 Monorepo 与 Phase 5 Hono.js 基础；建议已理解 TypeScript 类型系统

| 章节 | 标题 | 难度 | 重点标记 |
|------|------|------|---------|
| Ch102 | Zod 是什么 | 🟢 | 概念建立 |
| Ch103 | 单一真实来源 | 🟠 | **⭐ 重点** - Single Source of Truth |
| Ch104 | parse 与 safeParse | 🟠 | **重点** - 校验方式差异 |
| Ch105 | 基础类型 | 🟢 | |
| Ch106 | 对象与数组 | 🟢 | |
| Ch107 | 可选、默认值与空值 | 🟠 | 常见边界 |
| Ch108 | 联合与字面量 | 🟠 | 类型收束 |
| Ch109 | 自定义校验 | 🟠 | **重点** - refine / superRefine |
| Ch110 | 数据变换 | 🟠 | **重点** - transform / pipe |
| Ch111 | 类型推导 | 🟠 | **⭐ 重点** - infer / input / output |
| Ch112 | Schema 组合 | 🟠 | **重点** - extend / merge / pick / omit |
| Ch113 | Zod + Hono | 🟠 | **⭐ 核心** - 接口契约落地 |
| Ch114 | Zod + LLM | 🔴 | **⭐ 核心难点** - 结构化输出 |
| Ch115 | 实战：端到端 AI Chat | 🔴 | **⭐⭐ 综合实战** |

### Milestone 6 检查点

- [ ] 能用 Zod 定义完整的数据 schema，并清楚区分 parse / safeParse
- [ ] 理解 single source of truth，知道为什么前后端要共享 schema
- [ ] 能通过 infer / input / output 衔接运行时校验与 TS 类型
- [ ] 能把 Zod 接入 Hono 请求校验
- [ ] 能用 Zod 约束 LLM 的结构化输出
- [ ] 能完成端到端 AI Chat 的 schema 设计与联调

### ⚠️ 常见卡点

1. **Zod 不是只有校验** —— 更重要的是把“运行时数据边界”与“类型系统”统一
2. **parse vs safeParse** —— 一个抛异常，一个返回结果对象，使用场景不同
3. **transform / pipe** —— 很容易和纯校验混淆，需要区分“验证”与“数据变换”
4. **Zod + LLM** —— 模型可能输出“看起来像 JSON”的错误结构，schema 约束是稳定性的关键
5. **端到端 AI Chat** —— 前端表单、API 响应、模型输出要共享同一套契约，任何一层脱节都会出问题

### 💡 推荐实践

> 构建一个“结构化 AI 表单助手”：前端提交表单 → Hono 校验 → LLM 按 Zod schema 输出结果 → 前端安全渲染。

---

## Phase 7: Vercel AI SDK 与端到端交互重构（Ch116-136）

**目标**：掌握 Vercel AI SDK 的消息协议、流式 UI、工具调用、MCP 与服务端集成，并完成端到端 AI Chat 重构

**难度**：🟠 进阶 → 🔴 高级

**前置要求**：Phase 5 Hono.js、Phase 6 Zod 契约层；建议已理解流式响应与 Tool Calling

| 章节 | 标题 | 难度 | 重点标记 |
|------|------|------|---------|
| Ch116 | Vercel AI SDK | 🟢 | 概念建立 |
| Ch117 | 三层架构 | 🟢 | 架构理解 |
| Ch118 | 第一次调用 | 🟢 | **动手** |
| Ch119 | 模型 Provider 生态 | 🟠 | 选型视角 |
| Ch120 | 消息协议 | 🟠 | **⭐ 重点** - 消息抽象 |
| Ch121 | Prompt 工程 × AI SDK | 🟠 | **重点** - Prompt 接入 |
| Ch122 | UIMessageStream | 🟠 | **⭐ 核心** - 流式消息协议 |
| Ch123 | 结构化输出 | 🟠 | **重点** - object 生成 |
| Ch124 | Tool Calling | 🟠 | **⭐ 重点** - 工具协议 |
| Ch125 | 多步推理 | 🔴 | **⭐ 核心难点** - 多轮决策 |
| Ch126 | 聊天 UI 标准实现 | 🟠 | **实战** - useChat |
| Ch127 | UI Message Parts | 🟠 | **重点** - 可组合消息片段 |
| Ch128 | 结构化输出流式 UI | 🔴 | **⭐ 核心难点** - 结构化流式渲染 |
| Ch129 | RSC 流式 UI | 🔴 | **难点** - React Server Components |
| Ch130 | AI SDK × Hono | 🟠 | **⭐ 核心** - 服务端集成 |
| Ch131 | 缓存、限流、Fallback | 🟠 | 生产能力 |
| Ch132 | 可观测性：Telemetry | 🟠 | **重点** - 调试与观测 |
| Ch133 | MCP 客户端 | 🔴 | **⭐ 重点** - 外部能力接入 |
| Ch134 | 自建 MCP 服务端 | 🔴 | **⭐ 核心难点** - MCP 服务实现 |
| Ch135 | 与 LangChain 协同 | 🟠 | **重点** - 双框架协作 |
| Ch136 | 重构端到端 AI Chat | 🔴 | **⭐⭐ 综合实战** |

### Milestone 7 检查点

- [ ] 理解 AI SDK 的消息协议与流式输出模型
- [ ] 能用 useChat 构建标准聊天 UI
- [ ] 能完成 Tool Calling 与多步推理链路
- [ ] 能把 AI SDK 接入 Hono 服务端
- [ ] 理解 MCP 客户端 / 服务端的职责边界
- [ ] 完成 Ch136：重构端到端 AI Chat

### ⚠️ 常见卡点

1. **消息协议抽象 (Ch120, Ch122)** —— 容易只看到 UI 表象，忽略底层消息流模型
2. **多步推理 (Ch125)** —— 需要把工具调用、状态推进、停止条件一起看
3. **结构化输出流式 UI (Ch128)** —— 既涉及 schema，又涉及增量渲染
4. **RSC 流式 UI (Ch129)** —— 需要同时理解 React Server Components 与流式交付
5. **MCP (Ch133-134)** —— 客户端与服务端职责、协议边界、能力暴露方式容易混淆
6. **AI SDK × LangChain 协同 (Ch135)** —— 需要分清谁负责协议/UI，谁负责编排/工具链

### 💡 推荐实践

> 构建一个“AI SDK 聊天工作台”：前端 useChat + 结构化输出卡片 + Hono 服务端 + MCP 工具接入，最后重构成完整端到端 AI Chat。

---

## Phase 8: 综合实战与回顾

**目标**：将所有知识整合，交付完整的 AI 伴侣产品

**难度**：🔴 高级

### 回顾整合路径

1. 回顾 Ch60（LangGraph 重构 AI 伴侣管线）
2. 搭建 Monorepo 项目结构（Phase 4）
3. 实现 Hono 服务端（Phase 5 的 Ch93-94）
4. 接入 LangChain + LangGraph 编排（Phase 2-3）
5. 用 Zod 统一前端 / 服务端 / LLM 数据契约（Phase 6）
6. 用 Vercel AI SDK 重构消息协议、UI 流式输出与端到端交互（Phase 7）
7. 完成 Next.js 客户端聊天界面
8. 实现记忆系统 + 情绪状态机
9. 部署到 CloudFlare Workers
10. 接入可观测性（LangSmith/Langfuse/Telemetry）
11. 影子模式验证 + 灰度上线

### 最终检查点

- [ ] 完整的 Monorepo 项目结构运行正常
- [ ] AI 伴侣能维持多轮对话并保持角色一致性
- [ ] 记忆系统支持跨会话长期记忆
- [ ] 情绪状态机正常工作（会"记仇"、会"害羞"）
- [ ] 流式响应体验流畅
- [ ] Zod schema 成为前后端与 AI 输出的统一契约
- [ ] AI SDK 消息协议与 UI 渲染链路稳定
- [ ] MCP 能力接入可控且可观测
- [ ] 可观测性面板可以看到完整调用链路
- [ ] 成功部署到 CloudFlare Workers 边缘

---

## 学习建议

### 时间规划参考

| 阶段 | 核心内容 | 建议节奏 |
|------|---------|---------|
| Phase 1 | 理论认知 20 章 | 精读为主，每章反复思考 |
| Phase 2 | LangChain 23 章 | 边学边练，每章写代码 |
| Phase 3 | LangGraph 18 章 | 画图 + 写代码，难度最高 |
| Phase 4 | Monorepo 14 章 | 跟着搭项目 |
| Phase 5 | Hono.js 26 章 | 边学边部署 |
| Phase 6 | Zod 14 章 | 多做 schema 设计与联调 |
| Phase 7 | Vercel AI SDK 21 章 | 多做协议、UI、工具链整合 |
| Phase 8 | 综合实战 | 整合交付 |

### 学习策略

1. **Phase 1 不要跳过** —— 理论章节是后续所有实践的认知基础
2. **Phase 2 和 Phase 3 是核心** —— 花最多时间在这里，尤其是 LangGraph
3. **Phase 4、Phase 5、Phase 6 构成工程落地三件套** —— Monorepo 管协作，Hono 管接口，Zod 管契约
4. **Phase 7 补交互协议与产品层实现** —— AI SDK、MCP、流式 UI 会把前面能力真正串到用户体验上
5. **每个 Phase 结束时检查 Milestone** —— 确保真正掌握再往下走
6. **Ch60、Ch115、Ch136 是三个关键节点** —— 分别对应编排整合、契约整合、端到端交互重构
7. **遇到难点先标记，后面回来** —— 有些概念需要更多上下文才能完全理解

### 难度递进曲线

```
难度
 ▲
 │                                    ┌─── Ch55-57 多Agent
 │                              ┌─────┤    Ch60 综合实战
 │                        ┌─────┘     ├─── Ch96-97 边缘实战
 │                  ┌─────┘           ├─── Ch114-115 Zod + LLM / 端到端 AI Chat
 │            ┌─────┘                 └─── Ch128-136 AI SDK / MCP / 端到端重构
 │      ┌─────┘     Ch39 RAG
 │ ┌────┘   Ch36 记忆持久化
 │─┘  Ch04 内存调度
 │ Ch01-03
 └──────────────────────────────────────────────────────────▶ 章节
   Phase1      Phase2      Phase3      Phase4   Phase5   Phase6   Phase7
```
