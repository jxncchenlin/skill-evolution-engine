# 扩散日志

跨Skill改进模式传播记录。

## 扩散索引

| 编号 | 源Skill | 目标Skill | 抽象模式 | 状态 |
|------|---------|----------|---------|------|
| DIF-20260322-001 | product-mastery | idol-roundtable | FP-002 按需加载 | 已执行 |
| DIF-20260322-002 | multi-agent-research | — | FP-006 子Agent能力边界 | 待扩散（当前仅1个Skill使用task工具） |

---

## DIF-20260322-001 product-mastery → idol-roundtable（FP-002 按需加载）

**源改进**：将 frameworks.md 拆分为6个独立文件，训练时按主题只加载相关的1-2个
**抽象模式**：当知识库包含多个模块但每次只需部分时，按场景/主题建立索引表，只加载匹配的文件，避免无关知识干扰+token浪费
**目标Skill**：idol-roundtable（9位偶像知识库全量加载）
**适配方案**：根据议题类别建立"类别→推荐偶像"匹配表，每次只加载3-5位相关偶像的知识库文件
**执行状态**：自动执行 ✅（Low风险，SKILL.md纯文本修改）
**效果**：从每次加载9个文件减少到3-5个，token节省约40-60%

---

## DIF-20260322-002 multi-agent-research → 待扩散（FP-006 子Agent能力边界）

**源改进**：明确主Agent拥有完整工具链，子Agent（code-explorer）只有搜索和读取能力；数据收集由主Agent执行，分析可委托子Agent
**抽象模式**：区分主Agent和子Agent的能力边界，不在子Agent的prompt中要求使用它不拥有的工具
**目标Skill**：当前仅 multi-agent-research 使用 task 工具，暂无其他Skill可扩散
**执行状态**：待扩散
**后续**：当新Skill使用 task 工具时，自动提醒应用此模式
