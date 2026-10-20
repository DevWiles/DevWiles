<h1 align="center">Hi, 我是邓维 (Wiles) 👋</h1>

<p align="center">
  <b>AI 应用 / 解决方案工程师</b> · 广东工业大学 自动化 2027 届<br>
  做 RAG 知识库和 Coding Agent，从需求分析、方案选型、原型落地一路做到量化验收。
</p>

<p align="center">
  <a href="mailto:nathan.demon66@gmail.com"><img src="https://img.shields.io/badge/Email-nathan.demon66%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
  <img src="https://img.shields.io/badge/Open%20to-AI%20售前%20%2F%20解决方案%20%2F%20应用开发-2ea44f?style=flat-square" alt="Open to work">
</p>

---

### 🧭 关于我

- 🧩 **能写代码，也能做方案**：Java / Python 都写，熟悉 RAG、Agent、MCP 这些主流 AI 应用架构，能很快搭出 PoC 给人验证。
- 📏 **用数据说话**：每套方案都自建评测集，把「答得准不准、跑得快不快、花多少钱」变成可对比的数字。
- 💸 **效果和成本一起算**：自研 Coding Agent 与 Claude Code 同模型对标，成功率基本持平，推理成本低约 75%。
- 🤖 **重度 AI 工具用户**：原型、测试、文档日常都和 AI 编程工具一起完成。

### 🚀 代表项目

#### [myagent](https://github.com/DevWiles/myagent) — 从零手写的命令行 Coding Agent

参照 Claude Code 做的终端编程智能体，能读写代码、执行命令、搜索代码库、操作浏览器。**不依赖任何 Agent 框架**，ReAct 循环、工具调用、上下文管理、多 Agent 编排全部自己实现。
`Java 17` `OkHttp` `Function Calling` `MCP` `WebSocket` `JUnit 5` `OpenTUI / SolidJS`

| 指标 | 结果 |
| --- | --- |
| 66 题沙盒评测，与同模型 Claude Code 对比 | 成功率 **92.4%** vs 95.5%，单题输入 token **21.8k vs 87.4k**（约 1/4） |
| 真实仓库基准 AsynCodeBench · cachetools | **215 / 215** 测试、5 / 5 依赖契约全部通过 |
| 「规划 → 并行施工 → 验收」多 Agent 流水线 | 复杂任务成功率 68.8% → **81.2%** |
| 三档分级上下文压缩 | token −73%，连续 6 次压缩后目标保持率 **100%** |
| MCP 工具清单按需加载 | 单次请求开销 7.3k → 4.7k（−35%） |
| 检查点回退 | 影子 git 仓库按轮次快照，`/rewind` 一条命令撤回文件或对话 |
| 质量保障 | Docker 隔离沙盒 + 隐藏测试评测框架；全程 TDD，**1500+** 自动化测试 |

#### 企业私有知识库问答平台 · 实习项目（广州觅道信息技术咨询，2026.04 – 2026.08）

用户上传文档构建专属知识空间，用自然语言查询知识。我负责检索方案选型、异步架构和评测体系。
`Kafka` `Redis` `MinIO` `ElasticSearch` `LLM`

- 🔍 **混合检索**：对比纯关键词 / 纯向量 / 混合三条路线后，选定 BM25 + 向量双路召回 + RRF 融合 + rerank 精排；语义改写类问题召回率 87.1% → **95.7%**
- 📊 **可量化验收**：自建 213 题评测集，Recall@5 **98.6%**，端到端问答准确率 **94.8%**；用 chunk 级指标定位并修复 rerank 阈值问题
- ⚡ **异步解耦**：Kafka 拆开上传、解析、向量化流水线，上传响应 7.6 s → **157 ms**，20 并发 P50 21.9 s → **473 ms**；下游故障用户无感知，死信任务一键恢复
- 📈 **容量与扩容**：压测摸清单分区吞吐 4.6 篇/分钟，扩到 4 分区 4 消费者后 **15.2 篇/分钟（3.3×）**，并修复扩分区时的静默丢消息缺陷
- 🧮 **Redis BitMap**：1000 分片状态查询 176 ms → **0.26 ms**，存储约为 Set 方案的 1/100

#### 智能项目管理平台 · 后端（2025.11 – 2026.05）

项目创建、任务分配、角色权限、审批流程配置的微服务平台。
`Spring Cloud` `Flowable` `RocketMQ` `Seata` `Redis` `MySQL` `Nacos`

- RocketMQ 异步化任务指派与审批通知，接口 p50 209 ms → **100 ms**
- 自定义 `@DistributedLock` + AOP 幂等，50 并发重复提交从 8 行重复 / 42 次报错降到 **1 行 / 0 报错**；Seata AT 保证跨库一致
- GitHub Actions + Docker Compose 自动化部署，原子换入、可回滚，部署中位 **5.4 分钟**，14 容器一键拉起

### 🛠️ 技术栈

**AI 应用**
![RAG](https://img.shields.io/badge/RAG-混合检索%20%7C%20RRF%20%7C%20Rerank-6f42c1?style=flat-square)
![Agent](https://img.shields.io/badge/Agent-ReAct%20%7C%20Function%20Calling%20%7C%20MCP-6f42c1?style=flat-square)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![Milvus](https://img.shields.io/badge/Milvus%20%2F%20Chroma-00A1EA?style=flat-square&logo=milvus&logoColor=white)

**语言与后端**
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Spring Cloud](https://img.shields.io/badge/Spring%20Cloud-6DB33F?style=flat-square&logo=spring&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![RocketMQ](https://img.shields.io/badge/RocketMQ-D77310?style=flat-square&logo=apacherocketmq&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)

**部署交付**
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker%20Compose-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

### 📦 其他开源

| 仓库 | 简介 |
| --- | --- |
| [wechat-mp-archiver](https://github.com/DevWiles/wechat-mp-archiver) | 把微信公众号全部历史文章批量保存成 Markdown 笔记（Java） |
| [LingChat](https://github.com/DevWiles/LingChat) · [lingchat-web](https://github.com/DevWiles/lingchat-web) | 灵雀轻聊：Spring Cloud + Netty + Kafka 的微服务即时通讯系统，React 前端 |
| [MyNote](https://github.com/DevWiles/MyNote) | 记录日常、计划 Todo、AI 总结每日内容 |
| [base-of-wiles](https://github.com/DevWiles/base-of-wiles) | Wiles 的个人基地 |

### 🎓 教育

**广东工业大学** · 自动化（本科）· 2023.09 – 2027.06
院级优秀工作者、校级奖学金 · 参与发表深度学习领域论文、专利若干

---

<p align="center"><i>Keep learning.</i></p>
