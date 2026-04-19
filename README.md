# AI 电子伴侣 · 学习笔记与知识地图

基于 [aicompanion.usehook.cn](https://aicompanion.usehook.cn/) 教程（"这波能反杀"出品）整理的学习资料。

该教程围绕一个**企业级 AI 电子伴侣产品**展开，从智能体认知、LangChain/LangGraph 编排、Monorepo 工程化、Hono.js 边缘部署到 Zod 数据契约与结构化输出，共 115 章，持续更新中。

## 文档说明

| 文件 | 内容 |
|------|------|
| [架构总览.md](架构总览.md) | 四层架构、三子系统、数据流链路、内存调度、技术栈一览、技术重难点标注 |
| [roadmap.md](roadmap.md) | 7 阶段学习路径、每阶段 Milestone 检查点、难度等级、常见卡点提醒 |
| [知识地图.md](知识地图.md) | 7 大领域知识结构树、115 章节映射、依赖关系、跨章节关联、最小学习路径 |

每个 `.md` 文件都有对应的 `.excalidraw` 可视化图表，可用 [Excalidraw](https://excalidraw.com/) 或 VS Code 插件打开。

## 技术栈

```
AI 核心        LangChain · LangGraph · LangSmith · RAG · Vectorize
前端           Next.js · TailwindCSS · React Query · shadcn/ui
服务端         Hono.js · Bun · Zod · Drizzle ORM
基础设施       Cloudflare Workers · D1 · KV · Vectorize · Workers AI · R2
工程化         Turborepo · Monorepo · pnpm workspaces
```

## 架构概览

```
前端应用层     Next.js 客户端 (聊天)  ·  Next.js 后台管理 (运营)
                          │ Hono RPC 端到端类型安全
服务接口层     Hono.js on Cloudflare Workers
                          │
Agent 编排层   LangGraph (状态图编排/多Agent)  +  LangChain (RAG/工具/Memory)
                          │
基础设施层     CF D1 · KV · Vectorize · Workers AI · R2 · Durable Objects
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
| 🟠 | LCEL 链式调用 | Ch31-34 |
| 🟠 | Hono RPC 端到端类型安全 | Ch90, 101 |
| 🟠 | 边缘存储三件套 D1+KV+Vectorize | Ch86-88, 96 |
| 🟠 | 流式响应 SSE | Ch15, 50, 91 |

## 学习路径

```
Phase 1 理论认知 (Ch01-20)
  → Phase 2 LangChain (Ch21-43)
    → Phase 3 LangGraph (Ch44-61)  ← 最难阶段
      → Phase 4 Monorepo (Ch62-75)
        → Phase 5 Hono.js (Ch76-101)
          → Phase 6 Zod 契约层 (Ch102-115)
            → Phase 7 综合实战与回顾
```

> 最小路径：约 30 章覆盖所有核心知识点，详见 [知识地图.md](知识地图.md) 第六节。

## 教程信息

- 网站：https://aicompanion.usehook.cn/
- 作者：这波能反杀
- 状态：共 115 章，持续更新中
