# 🧭 Ariadne

**在择偶的迷宫中，找到你真正需要的方向。**

Ariadne（阿里阿德涅）是一个纯 LLM 驱动的择偶需求深度洞察系统。通过精心设计的多轮对话问询，深入了解你的感情观、生活方式、过往经历和内心需求，最终生成一份专业的择偶洞察报告。

**核心价值**：区分"你以为你想要的"和"你真正需要的"。

---

## 快速开始

> **模型要求**：**Claude Opus** 或 **GPT-5** 级别及以上。本系统依赖深度推理、长对话记忆和矛盾追踪能力，低于上述级别的模型可能导致洞察质量显著下降。

### 1. 克隆项目

```bash
git clone https://github.com/aspect-build/Ariadne.git
```

### 2. 用 Cursor 打开项目目录

```bash
cursor Ariadne/
```

也可以用其他支持项目级 System Prompt 的 AI IDE 或 LLM 客户端打开（见下方"其他平台"）。

### 3. 开始问询

在 Cursor 对话框中输入：

> **让我们开始问询吧**

AI 会自动读取项目中的 Skill 和知识库，以 Ariadne 的角色引导你完成 **15-25 轮**深度问询。对话开头会请你提供一个**名字或代号**，用于后续报告命名。

### 4. 生成报告

问询结束后，在对话框中输入：

> **根据上面的对话生成择偶洞察报告**

AI 会生成报告并保存为 `output/report-{你的名字或代号}.md`。

### 5. 匹配分析（可选）

如果有两个人各自完成了问询并生成了报告（如 `report-me.md` 和 `report-friend.md`），在对话框中输入：

> **分析 me 和 friend 的匹配度**

AI 会读取两份报告，生成匹配分析报告 `output/match-me-friend.md`。

---

### 其他平台使用方式

如果不使用 Cursor，可以在任何 LLM 平台上手动操作：

| 步骤 | 操作 |
|------|------|
| **问询** | 将 `skills/interview.skill.md` 全文复制为 System Prompt，开始对话 |
| **报告** | 将 `skills/report.skill.md` 设为 System Prompt，粘贴完整对话记录 |
| **匹配** | 将 `skills/match.skill.md` 设为 System Prompt，粘贴两份报告内容 |

支持的平台：Claude（Project Instructions）、ChatGPT（自定义指令）、API Playground（System 栏）等。

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

## 作者

**dtysky** — [dtysky@outlook.com](mailto:dtysky@outlook.com)

## 许可证

GPL-3.0
