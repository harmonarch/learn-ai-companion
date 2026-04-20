# AI 电子伴侣 · 学习笔记与知识地图

基于 [aicompanion.usehook.cn](https://aicompanion.usehook.cn/) 教程（"这波能反杀"出品）整理的学习资料。

该教程围绕一个**企业级 AI 电子伴侣产品**展开，从智能体认知、LangChain/LangGraph 编排、Monorepo 工程化、Hono.js 边缘部署、Zod 数据契约与结构化输出，继续扩展到 Vercel AI SDK、MCP 与端到端 AI Chat 重构，共 136 章。

## 文档说明

| 文件 | 内容 |
|------|------|
| [架构总览.md](架构总览.md) | 四层架构、三子系统、数据流链路、内存调度、Zod 契约层、AI SDK 交互层、技术栈与技术重难点 |
| [roadmap.md](roadmap.md) | 8 阶段学习路径、每阶段 Milestone 检查点、难度等级、常见卡点提醒 |
| [知识地图.md](知识地图.md) | 8 大领域知识结构树、136 章节映射、依赖关系、跨章节关联、最小学习路径 |

每个 `.md` 文件都有对应的 `.excalidraw` 可视化图表，可用 [Excalidraw](https://excalidraw.com/) 或 VS Code 插件打开。

## 专项学习计划与学习技能

- 专项计划总入口：[学习计划/README.md](学习计划/README.md)
- 通用方法论：[学习计划/00-学习方法与评估标准.md](学习计划/00-学习方法与评估标准.md)

| 领域 | 学习计划 | 对应 skill | 教程主章节 |
|---|---|---|---|
| LangChain | [01-LangChain-学习计划.md](学习计划/01-LangChain-学习计划.md) | `/langchain-study-plan` | Ch21-Ch43 |
| LangGraph | [02-LangGraph-学习计划.md](学习计划/02-LangGraph-学习计划.md) | `/langgraph-study-plan` | Ch44-Ch61 |
| Vercel AI SDK | [03-Vercel-AI-SDK-学习计划.md](学习计划/03-Vercel-AI-SDK-学习计划.md) | `/vercel-ai-sdk-study-plan` | Ch116-Ch132 |
| MCP | [04-MCP-学习计划.md](学习计划/04-MCP-学习计划.md) | `/mcp-study-plan` | Ch133-Ch134 |
| LangSmith | [05-LangSmith-学习计划.md](学习计划/05-LangSmith-学习计划.md) | `/langsmith-study-plan` | Ch17, Ch43 |
| Langfuse | [06-Langfuse-学习计划.md](学习计划/06-Langfuse-学习计划.md) | `/langfuse-study-plan` | Ch17, Ch43 |
| Next.js | [07-Next.js-学习计划.md](学习计划/07-Next.js-学习计划.md) | `/nextjs-study-plan` | Ch101, Ch126-Ch136 |
| React Query | [08-React-Query-学习计划.md](学习计划/08-React-Query-学习计划.md) | `/react-query-study-plan` | Ch90, Ch101, Ch115, Ch126 |
| Hono.js | [09-Hono.js-学习计划.md](学习计划/09-Hono.js-学习计划.md) | `/hono-study-plan` | Ch76-Ch101 |
| Zod | [10-Zod-学习计划.md](学习计划/10-Zod-学习计划.md) | `/zod-study-plan` | Ch102-Ch115 |
| Drizzle ORM | [11-Drizzle-ORM-学习计划.md](学习计划/11-Drizzle-ORM-学习计划.md) | `/drizzle-orm-study-plan` | Ch88, Ch93 |
| Cloudflare | [12-Cloudflare-学习计划.md](学习计划/12-Cloudflare-学习计划.md) | `/cloudflare-study-plan` | Ch11, Ch18, Ch77, Ch86-Ch100 |
| Turborepo | [13-Turborepo-学习计划.md](学习计划/13-Turborepo-学习计划.md) | `/turborepo-study-plan` | Ch71-Ch74 |
| Monorepo | [14-Monorepo-学习计划.md](学习计划/14-Monorepo-学习计划.md) | `/monorepo-study-plan` | Ch13-Ch14, Ch62-Ch75 |
| pnpm workspaces | [15-pnpm-workspaces-学习计划.md](学习计划/15-pnpm-workspaces-学习计划.md) | `/pnpm-workspaces-study-plan` | Ch63-Ch67 |

## 技术栈

```
AI 核心        LangChain · LangGraph · Vercel AI SDK · MCP · LangSmith · Langfuse
前端           Next.js · TailwindCSS · React Query · shadcn/ui
服务端         Hono.js · Bun · Zod · Drizzle ORM
基础设施       Cloudflare Workers · D1 · KV · Vectorize · Workers AI · R2 · Durable Objects
工程化         Turborepo · Monorepo · pnpm workspaces
```

## 架构概览

```
前端应用层     Next.js 客户端 (聊天)  ·  Next.js 后台管理 (运营)
                          │ Hono RPC / AI SDK Stream
服务接口层     Hono.js on Cloudflare Workers
                          │
Agent 编排层   LangGraph (状态图编排/多Agent)  +  LangChain / AI SDK (RAG/工具/Memory/协议)
                          │
基础设施层     CF D1 · KV · Vectorize · Workers AI · R2 · Durable Objects · MCP 服务
```

## 核心难点速查

| 难度 | 知识点 | 章节 |
|------|--------|------|
| 🔴 | LangGraph 多 Agent 编排 (Supervisor/Handoff/Swarm) | Ch55-57, 60 |
| 🔴 | 混合记忆架构 (多记忆源协调 + Token 预算) | Ch04, 09, 36, 58 |
| 🔴 | 内存调度器 Memory Scheduler | Ch04 |
| 🔴 | 情绪状态机 FSM | Ch07, 47 |
| 🔴 | RAG 管线优化 | Ch39, 96 |
| 🔴 | Checkpointer 状态持久化 | Ch48, 52 |
| 🔴 | Zod + LLM 结构化输出契约 | Ch114-115 |
| 🔴 | AI SDK 流式协议与 UI 渲染 | Ch122, 127-129 |
| 🔴 | MCP 客户端 / 服务端 | Ch133-134 |
| 🔴 | 端到端 AI Chat 重构 | Ch136 |
| 🟠 | LCEL 链式调用 | Ch31-34 |
| 🟠 | Hono RPC 端到端类型安全 | Ch90, 101 |
| 🟠 | 边缘存储三件套 D1+KV+Vectorize | Ch86-88, 96 |
| 🟠 | 流式响应 SSE / UIMessageStream | Ch15, 50, 91, 122 |

## 学习路径

```
Phase 1 理论认知 (Ch01-20)
  → Phase 2 LangChain (Ch21-43)
    → Phase 3 LangGraph (Ch44-61)  ← 最难阶段
      → Phase 4 Monorepo (Ch62-75)
        → Phase 5 Hono.js (Ch76-101)
          → Phase 6 Zod 契约层 (Ch102-115)
            → Phase 7 Vercel AI SDK (Ch116-136)
              → Phase 8 综合实战与回顾
```

> 最小路径：约 40 章覆盖当前主线核心知识点，详见 [知识地图.md](知识地图.md) 第六节。

## 教程信息

- 网站：https://aicompanion.usehook.cn/
- 作者：这波能反杀
- 状态：共 136 章，已覆盖 Vercel AI SDK、MCP 与端到端 AI Chat 重构
