# RCP Agent

**Reviewer Cognition & Persuasion Agent｜审稿人认知说服与论文重构 Agent**

从审稿人的阅读路径出发，检查论文的问题定义、研究缺口、机制、方法、证据和结论边界，输出可以直接替换的学术文本。

核心结构：

> Problem → Gap → Mechanism → Method → Prediction → Evidence → Boundary

## 这是之前的哪个 Agent？

- **LCB Agent（Language–Cognition–Behavior，语言—认知—行为）**：原始通用版本，用于论文、聊天和日常情绪梳理；分析链为事件 E → 表征 R → 意义解释 M → 状态 S → 行为 B → 结果 O。
- **RCP Agent**：从 LCB 的论文模式发展出的专用版本，围绕审稿人的理解、疑问和证据需求重构论文。这是本仓库的主项目。

这些名称来自原有“语言—认知—行为”课程和 Agent 定义；本项目定位为语言与论证分析工具，不声称是一套经过神经科学实验验证的干预系统。

## 使用方法

### 复制 Prompt 使用

打开 [SYSTEM_PROMPT.md](SYSTEM_PROMPT.md)，复制完整内容到对话中，再提供论文段落和已有证据。例如：

> 启动 RCP Agent，重构下面的摘要。先检查主张与证据是否匹配，再给出可直接替换版本。不能新增数据、文献或未经证明的因果结论。

仅说名称不会让一个未加载本项目的对话自动获得这些规则，需要先提供 Prompt 或加载 Skill。

### 作为 Skill 使用

将整个 `rcp-agent` 文件夹放入所用工具支持的技能目录，保留 [SKILL.md](SKILL.md)、[SYSTEM_PROMPT.md](SYSTEM_PROMPT.md) 及其相对路径资源。Skill 名称为 `rcp-agent`。

## 默认交付

1. 审稿人当前可能形成的理解。
2. 主要问题：模糊表述、过度概括、未验证因果、错误预设、过大主张。
3. 应建立的核心命题。
4. 正确机制链及其证据状态。
5. 缺失证据与最有价值的验证。
6. 逐句修改及理由。
7. 可直接替换的完整版本。

简短请求可以合并以上项目；若用户只要修改结果，优先满足所需格式。

## 文件

| 文件 | 用途 |
| --- | --- |
| [SKILL.md](SKILL.md) | 技能发现与执行入口 |
| [SYSTEM_PROMPT.md](SYSTEM_PROMPT.md) | 可独立复制使用的完整 RCP 规则 |
| [摘要示例](examples/abstract-rewrite.md) | 将宽泛效果主张改成可核查表述 |
| [引言示例](examples/introduction-rewrite.md) | 准确界定已有能力和研究缺口 |
| [审稿回复示例](examples/reviewer-response.md) | 区分已完成修改与待补证据 |
| [LCB Agent](references/lcb-agent.md) | 通用版 Agent 的整理稿 |
| [来源说明](references/origin.md) | 原始定义来源及本次整理范围 |

三个示例是为分享包新增的教学示例，不包含真实论文结果。`[待补：…]` 表示必须由使用者补齐的内容。

## 证据原则

不编造数据、引用、实验、修改记录或录用概率；不把相关性写成因果性。审稿人反驳模拟是检查工具，不是对真实审稿人心理的判断。负面结果和适用限制应如实呈现，不能仅通过换措辞掩盖方法缺陷。
