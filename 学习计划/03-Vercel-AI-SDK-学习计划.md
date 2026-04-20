# Vercel AI SDK 学习计划

## 这个领域解决什么问题

Vercel AI SDK 负责 AI 交互协议、消息抽象、流式输出、工具调用和 UI 集成，适合把模型能力稳定地接进前后端交互层。

## 学习目标

- 理解 Model / Server / UI 三层职责
- 能写最小消息流和 useChat 交互
- 能解释 Tool Calling 和多步推理的服务端链路
- 能区分 AI SDK 和 LangChain / LangGraph 的分工
- 能把 AI SDK 接到 Next.js 或 Hono 服务中

## 前置知识

- Ch15：Streaming
- `09-Hono.js-学习计划.md`
- `10-Zod-学习计划.md`

## 章节映射

- 主章节：Ch116-Ch132
- 关联章节：Ch115、Ch130、Ch135-Ch136

## 四阶段路径

### 阶段 1：入门理解
- Ch116-Ch120
- 重点：三层架构、provider、消息协议
- 产出：能解释消息为什么要统一抽象

### 阶段 2：核心能力
- Ch121-Ch125
- 重点：Prompt 接入、UIMessageStream、结构化输出、Tool Calling、多步推理
- 产出：能写最小流式和工具调用示例

### 阶段 3：实战落地
- Ch126-Ch132
- 重点：useChat、message parts、RSC、AI SDK × Hono、Telemetry
- 产出：能做一个最小 AI Chat 页面与服务端接口

### 阶段 4：巩固与排障
- 回看 Ch120、Ch122、Ch124、Ch128、Ch130、Ch132
- 重点：消息协议、流式 UI、工具回流、观测信号
- 产出：能定位前后端流式不一致的问题

## 核心易混点

- AI SDK 是交互协议与流式 UI 层，不是完整编排框架。
- 服务端工具调用成功，不代表结果已经正确回流到 UI。
- 文本流、对象流、message parts 的使用场景不同。
- AI SDK 与 LangChain / LangGraph 的职责边界要分清。

## 各阶段过关标准

- 阶段 1：能解释它解决的问题，并写出或画出一个最小结构。
- 阶段 2：能独立完成核心能力的小例子，并说清执行流。
- 阶段 3：能把它接到当前 AI 伴侣项目的上下游，并解释边界。
- 阶段 4：能围绕典型错误定位根因，给出最小修复和复盘。

## 必做失败演练

- 故意让服务端只返回文本，不返回工具结果片段，观察前端为什么看不到工具输出。
- 故意制造前后端消息协议不一致，练习定位是服务端、客户端还是渲染层问题。
- 故意让 useChat 状态管理和服务端多步推理脱节，观察交互错位。

## 改造练习

- 把最小文本聊天示例改造成带 tool result 展示和流式更新的聊天界面。

## 系统连接

- 上游常接 Hono、Next.js、模型 provider。
- 下游常与 MCP、LangGraph、观测系统一起工作。
- 在 AI 伴侣里常落在交互协议层和前后端消息桥接层。

## 常见误区

1. 把 AI SDK 当成编排框架，导致工作流控制变得混乱
2. 不理解消息协议，只会照抄 useChat 示例
3. 前端只渲染文本，忽略对象流和 message parts
4. 工具调用成功了，但没有把结果正确回流给 UI

## 练习清单

- [ ] 写一个最小 `generateText` / `streamText` 示例
- [ ] 用 useChat 做一个最小聊天界面
- [ ] 增加一个 tool，并显示工具结果片段
- [ ] 把 AI SDK 服务端接到 Hono 路由中

## 对应 skill 与相关专项

- 对应 skill：`/vercel-ai-sdk-study-plan`
- 相关专项：`04-MCP-学习计划.md`、`07-Next.js-学习计划.md`、`09-Hono.js-学习计划.md`
