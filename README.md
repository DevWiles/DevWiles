# 邓维 Wiles

### AI 应用 / 解决方案工程师

广东工业大学 · 自动化 · 2027 届
<br>
[Email](mailto:nathan.demon66@gmail.com) &nbsp;/&nbsp; [个人主页](https://devwiles.vercel.app/) &nbsp;/&nbsp; [myagent](https://github.com/DevWiles/myagent)

> **Open to work** — AI 售前、解决方案、应用开发

主要做 Agent 和 RAG 应用。Java、Python 都写，习惯先搭一个能跑的原型，再自建评测集，把准确率、延迟和成本量化成能横向比较的数字。日常写代码、测试和文档都离不开 AI 编程工具。

---

### 项目

**[myagent](https://github.com/DevWiles/myagent)**：从零手写的命令行 Coding Agent

参照 Claude Code 实现，能读写代码、执行命令、搜索代码库、操作浏览器。没有用任何 Agent 框架，ReAct 循环、工具调用、上下文管理和多 Agent 编排都是自己写的。

Java 17 · OkHttp · Function Calling · MCP · WebSocket · JUnit 5 · OpenTUI / SolidJS

| 指标 | 结果 |
| --- | --- |
| 66 题沙盒评测，与同模型 Claude Code 对比 | 成功率 92.4% vs 95.5%，单题输入 token 21.8k vs 87.4k |
| 真实仓库基准 AsynCodeBench · cachetools | 215 / 215 测试、5 / 5 依赖契约通过 |
| 规划、并行施工、验收的多 Agent 流水线 | 复杂任务成功率 68.8% → 81.2% |
| 三档分级上下文压缩 | token 减少 73%，连续 6 次压缩后目标保持率 100% |
| MCP 工具清单按需加载 | 单次请求开销 7.3k → 4.7k |
| 检查点回退 | 影子 git 仓库按轮次快照，`/rewind` 撤回文件或对话 |
| 测试 | Docker 隔离沙盒 + 隐藏测试评测框架，TDD，1500+ 自动化测试 |

**智能项目管理平台 · 后端**（2025.11 – 2026.05）

项目创建、任务分配、角色权限、审批流配置的微服务平台。

Spring Cloud · Flowable · RocketMQ · Seata · Redis · MySQL · Nacos

- 任务指派和审批通知改为 RocketMQ 异步，接口 p50 从 209 ms 降到 100 ms
- 自定义 `@DistributedLock` + AOP 做幂等，50 并发重复提交从 8 行重复、42 次报错降到 1 行、0 报错；跨库一致性用 Seata AT
- GitHub Actions + Docker Compose 部署，原子换入、可回滚，部署中位耗时 5.4 分钟，14 个容器一键拉起

### 其他仓库

| 仓库 | 简介 |
| --- | --- |
| [wechat-mp-archiver](https://github.com/DevWiles/wechat-mp-archiver) | 把公众号历史文章批量存成 Markdown（Java） |
| [LingChat](https://github.com/DevWiles/LingChat) · [lingchat-web](https://github.com/DevWiles/lingchat-web) | 即时通讯系统，Spring Cloud + Netty + Kafka，React 前端 |
| [MyNote](https://github.com/DevWiles/MyNote) | 日常记录、Todo，AI 总结每日内容 |
| [base-of-wiles](https://github.com/DevWiles/base-of-wiles) | 个人主页 |

### 技术栈

- AI 应用：RAG（混合检索、RRF、Rerank）、Agent（ReAct、Function Calling、MCP）、LangChain、PyTorch、Milvus / Chroma
- 后端：Java、Python、Spring Cloud、Kafka、RocketMQ、Redis、Elasticsearch、MySQL
- 部署：Linux、Docker Compose、GitHub Actions、Git

### 教育

广东工业大学 · 自动化本科 · 2023.09 – 2027.06
院级优秀工作者、校级奖学金，参与发表深度学习方向论文和专利若干
