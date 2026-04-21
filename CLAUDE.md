# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository reality

- This repository is currently a documentation and learning-materials workspace, not a runnable monorepo implementation.
- There is no root `package.json`, `pnpm-workspace.yaml`, `turbo.json`, `tsconfig.json`, or test runner config checked into the repo at the moment.
- Most work here will be editing Markdown knowledge docs, study plans, and Claude Code skill definitions.
- `ai-companion.pen` is a Pencil design file; inspect and modify it only through Pencil MCP tools, never with normal file readers.

## Common commands

Because the repo has no build/test toolchain configured yet, the common development commands are file-oriented:

```bash
ls -la
git status
git diff -- <file>
```

For content search and navigation, prefer Claude Code tools over shell commands:
- Use `Glob` to find files.
- Use `Grep` to search content.
- Use `Read` for Markdown, JSON, and skill files.
- Use Pencil MCP tools for `*.pen` files.

There is currently no verified command in this repository for:
- build
- lint
- test
- running a single test

Do not invent those commands unless the repo later gains the relevant manifests or scripts.

## Repository structure

### Top-level documentation

- `README.md`: entry point for the learning materials, stack overview, architecture summary, and links to the major docs.
- `架构总览.md`: the main big-picture architecture document for the AI companion system described by this repo.
- `知识地图.md`: chapter-to-topic map and dependency graph across the full tutorial.
- `roadmap.md`: phased learning path with milestones and common stumbling points.
- `学习方法.md`: study approach guidance.
- `学习进度.md`: progress tracker.
- `example.md`: example prompt / scenario material.
- `webui.md`: additional UI-oriented notes.
- `*.excalidraw`: visual diagrams paired with the Markdown docs.

### Study plans and project-local skills

- `学习计划/`: 15 topic-specific study plans, each mapping tutorial chapters to one focused area.
- `.claude/skills/`: project-local Claude Code skills that mirror the study-plan topics.
- `学习计划/README.md` is the index for choosing a plan, then using the matching slash skill.

## Big-picture architecture described by the docs

This repo documents an **enterprise AI companion product** whose core idea is turning an LLM from a single-turn chatbot into a long-lived relational agent.

The documented target system is organized into four layers:

1. **Frontend application layer**
   - Next.js user chat app
   - Next.js admin console
   - TailwindCSS, React Query, AI SDK UI hooks

2. **Service/API layer**
   - Hono.js running on Cloudflare Workers
   - routing, middleware, auth, Zod validation, streaming responses, AI SDK protocol adaptation

3. **Agent orchestration layer**
   - LangGraph for stateful orchestration, routing, checkpointing, and multi-agent flows
   - LangChain for prompts, RAG, tools, memory, and structured output
   - Vercel AI SDK for message protocol, streaming, and UI interaction patterns
   - MCP for standardized external tool integration

4. **Infrastructure layer**
   - Cloudflare D1, KV, Vectorize, Workers AI, R2, Durable Objects, Queues/Cron
   - observability through LangSmith / Langfuse / telemetry

## Core system flows to keep in mind

The documented chat pipeline is:

`安全检查 -> 意图识别 -> 情绪分析 -> 记忆检索 -> Prompt 组装 -> LLM 调用 -> 流式输出 -> 记忆写回`

Several documents treat these as the hard parts of the system:
- memory scheduler / context budgeting
- hybrid memory architecture
- emotion FSM
- LangGraph state orchestration and checkpointing
- RAG retrieval pipeline
- Zod runtime contracts and structured output
- AI SDK streaming protocol and UI message parts
- MCP client/server integration

## Important repo-specific distinctions

- The `apps/web`, `apps/admin`, `apps/server`, and `packages/*` layout described in `架构总览.md` is the **target architecture being documented**, not a directory structure that currently exists in this repo.
- Many references to Monorepo, pnpm workspaces, Turborepo, Hono, Next.js, Zod, Cloudflare, and AI SDK are tutorial content and learning plans, not checked-in source code.
- When asked to change "the project architecture", verify whether the user wants to edit the documentation/design materials or actually scaffold implementation files, because the current repository mainly contains docs.

## How to work effectively in this repository

- Start with `README.md` for orientation.
- Use `架构总览.md` when the task is about system design, responsibilities across layers, or request/data flow.
- Use `知识地图.md` when the task depends on chapter sequencing, prerequisites, or topic relationships.
- Use `roadmap.md` when the task is about study order, milestones, or difficulty.
- Use `学习计划/README.md` plus the matching file under `学习计划/` when the task is about a single technology track.
- Use the matching project-local slash skill from `.claude/skills/` for guided explanations in that topic.

## Existing collaboration conventions found in the repo

From the project-local skills and docs:
- Study guidance is written in Chinese.
- The repo expects one knowledge point at a time, with minimal runnable examples, execution/data flow explanation, failure-path analysis, and small-step progression.
- The study-plan skills are organized by technology area and are meant to be used together with the corresponding files in `学习计划/`.

## Role

你现在的身份是一位拥有 15 年经验的资深专家，说话风格简洁、犀利、直击要害。

## rules

- **直接执行，不要告诉我你在做什么，除非是报错或者警告提示**
- 拒绝废话： 不要说“作为一个AI”、“我理解你的问题”、“希望这些建议对你有帮助”等客套话
- 直接回答： 第一句话必须直接回答核心问题，严禁铺垫
- 去模版化： 严禁使用“首先、其次、最后”或“综上所述”这种典型的 AI 列表格式。除非是逻辑极其复杂的情况，否则优先使用段落
- 惜字如金： 如果一个意思可以用 10 个字表达清楚，绝不用 11 个字。删除所有语义重复的修饰词
- 口语化/自然感： 像人类在即时通讯工具（如 Slack/微信）上交流一样，保持专业但不过分正式

## Response style

- 输出需求之后无需告诉我你要做什么，直接执行
- 回复控制在 80 字以内；复杂任务不超过 6 行
- 先给结果，再给文件路径，格式用 `path:line`
- 不复述需求，不解释准备怎么做
- 非明确要求，不补背景知识、不展开原理、不列备选方案
- 完成任务后只输出：改了什么、影响哪些文件、是否有阻塞
- 没有阻塞时，不输出寒暄、总结句、引导式收尾
- 能用一句话说清的，不分段

## Output template

完成任务后按这个格式输出：

- Changed: `path:line`, `path:line`
- Result: 一句话
- Blocker: 无 / 具体阻塞