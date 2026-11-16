### **Astronaut AI Agent：从零实现的 LLM 编程智能体框架**
**2026.06 – 2026.07 | 个人项目 · 独立开发**

从零实现的 LLM Agent 编程框架，覆盖流式对话、工具编排、技能自进化、代码检索（RAG）与文件沙箱，支持多 API Provider，全栈仅依赖 Python 标准库 + Rich + OpenAI SDK。

- 设计四层上下文压缩管道与并行工具编排系统（ThreadPool + 熔断 + 自动纠错），支撑长任务稳定执行。
- 实现 Skill 自进化机制：基于滑动窗口的成功率检测与退化自动回滚。
- 实现零外部依赖的轻量 RAG 引擎，支持中英混合检索；实现文件系统与代码执行双层沙箱。
- Session、Memory、Skill 自动持久化至 MySQL；集成 GitHub API 构建社区技能市场，支持多 Agent 并行协作与安全权限继承。

`Python` `OpenAI SDK` `RAG` `MySQL` `Docker`

---

### **面向嵌入式操作系统的 AI 辅助驱动移植**
**2026.03 – 2026.11 | 校内项目 · 核心开发**

在国产算力环境搭建大模型训练与部署全链路，并通过多智能体框架实现驱动迁移流程自动化。

- 于 Ascend 910B（Atlas 300I A2）搭建 ms-swift 训练链路，结合硬件文档构建 Next-Token-Prediction 预训练语料，并基于自研 APIKG4SYN 框架（ESEC/FSE 2026 一作论文）聚合双方 API 文档合成大规模代码语料。
- 采集 DeepSeek-V4-Pro 等强模型的成功训练轨迹，修正负面轨迹后构建 SFT 数据，采用 SFT（LoRA）+ DPO 训练 Qwen3.8-27B。
- 使用 ModelSlim 将 DeepSeek-V4.1-Flash-1017 量化为 W8A8，基于 vllm-ascend 在双机 Atlas 300I A2 上分布式部署；迁移全程由该模型执行，Qwen3.8-27B 实时修正轨迹，规避重复对话、遗忘、反复查看文件与重复调用工具等冗余行为。
- 将部署的模型接入多智能体框架，实现驱动迁移自动化：以 Vendor/Base 源码仓库、开发板信息与目标驱动为输入，经文件定位、静态分析、编译反馈修复、上板验证修复等阶段，交付可运行镜像与迁移报告。
- 远程接入协作方开发板平台完成烧录验证；在 OEE、UniProton 上完成 TL3588、RK3568 等多块板卡驱动移植并测试通过。

`Ascend NPU` `ms-swift` `LoRA` `DPO` `W8A8` `vLLM-Ascend` `Multi-Agent`
