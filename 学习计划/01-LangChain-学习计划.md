# LangChain 学习计划

## 这个领域解决什么问题

LangChain 负责把模型调用、Prompt、结构化输出、工具调用、RAG、链式组合等原子能力组织起来，适合搭建单 Agent 能力链和可复用的 AI 组件。

## 学习目标

- 理解 LangChain 在 Agent 系统中的位置
- 能写出最小模型调用、Prompt、Tool、RAG 示例
- 能说清 Runnable / LCEL 的执行流
- 能判断什么时候只用 LangChain 就够
- 能把 LangChain 能力接到 AI 伴侣项目里

## 前置知识

- Ch02-Ch05：Agent 基本认知
- Ch08：Prompt 基础
- TypeScript / Python 基础语法

## 章节映射

- 主章节：Ch21-Ch43
- 关联章节：Ch05、Ch114、Ch124、Ch135

## 四阶段路径

### 阶段 1：入门理解
- Ch21-Ch27
- 重点：模型调用、消息协议、LangChain 定位
- 产出：能写出一次最小调用，并解释 message 结构

### 阶段 2：核心能力
- Ch28-Ch36
- 重点：Prompt、Output Parser、LCEL、Memory
- 产出：能写链式调用，能比较不同 memory 方案

### 阶段 3：实战落地
- Ch37-Ch43
- 重点：RAG、Tools、Middleware、Tracing
- 产出：能做一个最小工具型 Agent 或 RAG 助手

### 阶段 4：巩固与排障
- 回看 Ch31、Ch36、Ch39、Ch40、Ch43
- 重点：执行流、失败路径、Tracing 观察
- 产出：能独立定位链式组合、检索、工具调用中的问题

## 核心易混点

- LangChain 负责原子能力组织，LangGraph 负责工作流编排。
- Runnable / LCEL 是执行组合，不只是语法糖。
- Output Parser、Zod 契约、模型输出约束不是同一层。
- 会话 memory 和业务 state 的边界要分清。

## 各阶段过关标准

- 阶段 1：能解释它解决的问题，并写出或画出一个最小结构。
- 阶段 2：能独立完成核心能力的小例子，并说清执行流。
- 阶段 3：能把它接到当前 AI 伴侣项目的上下游，并解释边界。
- 阶段 4：能围绕典型错误定位根因，给出最小修复和复盘。

## 必做失败演练

- 故意把 tool 描述写得过弱，观察模型为什么不调用或乱调用工具。
- 故意让 parser 或 structured output 失败，练习定位失败发生在哪一层。
- 故意做一个低质量 RAG 切分或检索，比较回答为什么失真。

## 改造练习

- 把单轮工具调用示例改造成可复用的能力链，再判断什么时候该升级到 LangGraph。

## 系统连接

- 上游连接 Prompt、模型和消息协议。
- 下游常接 LangGraph、LangSmith、Langfuse 等调试与编排层。
- 在 AI 伴侣里常落在原子能力层和工具/RAG 接入层。

## 常见误区

1. 把 LangChain 当成完整工作流框架，结果在多步状态控制上越写越乱
2. 只会堆 Prompt，不理解 Runnable 输入输出边界
3. 把类型安全和运行时校验混为一谈
4. RAG 只盯模型，不看分块、检索和上下文注入质量

## 练习清单

- [ ] 写一个最小 ChatModel + PromptTemplate 示例
- [ ] 用 LCEL 拼一个“摘要 + 分类”链
- [ ] 做一个最小 Tool Calling 示例，并故意制造参数错误再修复
- [ ] 做一个最小 RAG 管线，比较不同 chunk 策略的效果

## 对应 skill 与相关专项

- 对应 skill：`/langchain-study-plan`
- 相关专项：`02-LangGraph-学习计划.md`、`05-LangSmith-学习计划.md`、`06-Langfuse-学习计划.md`
