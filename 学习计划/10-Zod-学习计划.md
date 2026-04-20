# Zod 学习计划

## 这个领域解决什么问题

Zod 负责运行时数据校验、schema 组合、类型推导和接口契约统一，是前后端边界、服务接口和 LLM 结构化输出的重要基础。

## 学习目标

- 理解 Zod 为何不能被 TypeScript 类型替代
- 能写常见 schema、组合 schema 和自定义校验
- 能说清 parse / safeParse / transform / infer 的边界
- 能把 Zod 接到 Hono 接口和 AI 输出中
- 能围绕契约设计前后端共享数据结构

## 前置知识

- TypeScript 基础
- `09-Hono.js-学习计划.md`
- 基本 JSON 数据结构建模

## 章节映射

- 主章节：Ch102-Ch115
- 关联章节：Ch82、Ch90、Ch114、Ch123

## 四阶段路径

### 阶段 1：入门理解
- Ch102-Ch108
- 重点：基础类型、对象、数组、联合
- 产出：能写出常见请求体 schema

### 阶段 2：核心能力
- Ch109-Ch112
- 重点：refine、transform、infer、schema 组合
- 产出：能设计复用型 schema

### 阶段 3：实战落地
- Ch113-Ch115
- 重点：Zod + Hono、Zod + LLM、端到端 AI Chat
- 产出：能统一前端输入、接口和 AI 输出契约

### 阶段 4：巩固与排障
- 回看 Ch103、Ch104、Ch111、Ch113、Ch114
- 重点：运行时边界、类型推导、结构化输出稳定性
- 产出：能定位到底是 schema、类型还是模型输出出了问题

## 核心易混点

- TypeScript 类型和运行时校验不是同一层保障。
- parse、safeParse、refine、transform 的职责边界要分清。
- 输入契约、内部结构、输出契约不该共用同一心智。
- LLM 输出只做 JSON.parse 远远不够。

## 各阶段过关标准

- 阶段 1：能解释它解决的问题，并写出或画出一个最小结构。
- 阶段 2：能独立完成核心能力的小例子，并说清执行流。
- 阶段 3：能把它接到当前 AI 伴侣项目的上下游，并解释边界。
- 阶段 4：能围绕典型错误定位根因，给出最小修复和复盘。

## 必做失败演练

- 故意让 schema 和真实输入字段不匹配，观察错误路径怎样暴露。
- 故意把该用 safeParse 的地方写成 parse，比较边界处理差异。
- 故意给结构化 AI 输出省掉契约校验，练习定位不稳定输出。

## 改造练习

- 把分散在接口、前端和 AI 输出里的零散校验整理成一套共享契约层。

## 系统连接

- 上游常接表单输入、接口请求体、模型结构化输出。
- 下游常接 Hono、React Query、Drizzle、AI SDK。
- 在 AI 伴侣里常落在契约层和运行时边界保护层。

## 常见误区

1. 以为有 TypeScript 就不需要运行时校验
2. 不区分 parse 和 safeParse 的使用时机
3. schema 复用随意，导致边界不清
4. 对 LLM 输出只做 JSON.parse，不做真正契约约束

## 练习清单

- [ ] 写一个用户表单 schema，并推导类型
- [ ] 对同一个 schema 做 parse 和 safeParse 对比
- [ ] 给 Hono 接口加请求校验与响应契约
- [ ] 用 Zod 约束一次结构化 AI 输出

## 对应 skill 与相关专项

- 对应 skill：`/zod-study-plan`
- 相关专项：`09-Hono.js-学习计划.md`、`03-Vercel-AI-SDK-学习计划.md`、`11-Drizzle-ORM-学习计划.md`
