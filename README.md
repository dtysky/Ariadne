# 🧭 Ariadne

**在择偶的迷宫中，找到你真正需要的方向。**

Ariadne（阿里阿德涅）是一个纯 LLM 驱动的择偶需求深度洞察系统。通过精心设计的多轮对话问询，深入了解你的感情观、生活方式、过往经历和内心需求，最终生成一份专业的择偶洞察报告。

**核心价值**：区分"你以为你想要的"和"你真正需要的"。

---

## 使用方式

> **推荐模型**：**Claude Opus** 或 **GPT-5** 级别及以上。本系统依赖模型的深度推理、长对话记忆和矛盾追踪能力，低于上述级别的模型可能导致洞察质量显著下降。

### 第一步：问询对话

1. 将 `skills/interview.skill.md` 的内容设为 LLM 的 System Prompt
2. 开始对话，AI 会以 Ariadne 的角色引导你完成 15-25 轮深度问询
3. 对话开头会请你提供一个**名字或代号**，用于后续报告命名
4. 对话结束后，保存完整的对话记录

### 第二步：生成报告

1. 将 `skills/report.skill.md` 的内容设为 LLM 的 System Prompt
2. 在用户消息中粘贴第一步的完整对话记录
3. AI 会生成一份结构化的择偶洞察报告，文件名为 `report-{你的名字或代号}.md`

### 第三步（可选）：匹配分析

如果有两个人分别完成了问询并生成了各自的报告，可以进行匹配分析：

1. 将 `skills/match.skill.md` 的内容设为 LLM 的 System Prompt
2. 提供两个来访者的名字或代号，AI 会读取 `output/report-{A}.md` 和 `output/report-{B}.md`
3. 生成匹配分析报告 `match-{A}-{B}.md`，评估两人在恋爱、友谊、协作等关系类型中的匹配度

---

## 项目结构

```
Ariadne/
├── skills/                     # Skill 文件（作为 LLM System Prompt 使用）
│   ├── interview.skill.md      # 问询对话 Skill —— 驱动深度问询对话
│   ├── report.skill.md         # 报告生成 Skill —— 基于对话生成洞察报告
│   └── match.skill.md          # 匹配分析 Skill —— 基于两份报告分析匹配度
├── knowledge/                  # 知识库（分析框架与参考资料）
│   ├── framework.md            # 择偶心理分析框架
│   ├── dimensions.md           # 问询维度与问题库
│   └── report-template.md      # 报告结构模板
├── output/                     # 报告输出目录
│   ├── report-{name}.md        # 个人择偶洞察报告
│   └── match-{A}-{B}.md        # 双人匹配分析报告
└── examples/                   # 示例
    └── sample-report.md        # 示例报告（虚构案例）
```

## 分析框架

系统基于以下心理学理论进行分析：

- **依恋理论**：安全型、焦虑型、回避型、混乱型四种依恋风格
- **关系需求层次**：基础→安全→归属→尊重→成长五层模型
- **常见择偶认知偏差**：光环效应、补偿心理、投射效应等九类偏差
- **表层-深层映射**：一致型、偏移型、矛盾型、补偿型四种偏好-需求关系

详见 `knowledge/framework.md`。

## 报告示例

查看 `examples/sample-report.md` 了解报告的完整格式和分析深度。

## 许可证

MIT
