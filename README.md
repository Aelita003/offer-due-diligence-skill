# look-before-you-leap

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

> 签 offer 之前，像投资人一样把这家公司看清楚。
> *See the company clearly before you sign.*

一个面向求职者的企业背调 skill，基于 [Agent Skills](https://agentskills.io) 开放格式。
*An Agent Skill for job-seeker employer due diligence.*

---

## 这是什么 / What is this

把投资人投前尽调的方法论搬进求职场景。核心锚点是一句话：

**求职 = 用职业生涯做一次不可分散的投资。**

所以它不产出"公司介绍"，产出的是**证据驱动的尽调报告**——先把事情看真，再谈怎么用。所有结论都必须能追溯到证据行；查不到的就标"未公开"，绝不编造。

*Investor-grade due diligence methodology, applied to your career decision. Your next job is an undiversifiable investment — you cannot spread your career across ten companies. So this skill does not produce a company profile. It produces an evidence-driven due-diligence report where every conclusion traces back to a source, and every gap is marked as a gap rather than filled with a guess.*

## 产出什么 / What you get

一份单一自包含的 HTML 报告：

- **顶部红绿灯** + 一句话求职建议（附置信度）
- **结论摘要**：商业四问 + 求职者四问浓缩
- **详细分析**：各节结论先行，关键事实用内联脚注链到证据附录
- **证据附录**：完整证据表（来源 / 日期 / 原文要点 / 可信度 / 相反证据 / 待验证问题）
- **缺失板块清单**：信息不足时列出"没查到什么"，并给出面试时该重点核实什么

*A single self-contained HTML report: traffic-light verdict, one-line recommendation with a confidence level, conclusion-first analysis with inline footnotes, a full evidence appendix, and — when information is thin — an explicit list of what could not be found.*

## 怎么工作 / How it works

**4 个阶段，严格顺序：**

1. **明确问题** — 消歧目标公司，判定类型（上市公司 / 初创·融资期 / 外企中国区 / 小微企业），锁定 8 个待答问题
2. **收集证据** — 构建证据清单。**此阶段不下结论**，只记录"当前能说什么、有没有反证、还缺什么"
3. **质量检查** — 8 项交叉验证（营收与增长、客户真实性、合作背书含金量、产品发布节奏、组织变化、竞品优劣、财务健康信号、赛道周期）
4. **形成结论** — 红绿灯必须由证据推导，然后填充 HTML 报告模板

**四个阶段里最关键的是第 2 阶段的纪律**：收集证据时不下结论。这是尽调与"资料搜集"的分界线。

**8 个待答问题：**

| 商业四问 | 求职者四问 |
|---|---|
| ① 卖什么（产品与赛道成色） | ⑤ 风险红旗 |
| ② 客户是谁（盈利模式） | ⑥ 口碑文化 |
| ③ 凭什么胜出（竞争优势） | ⑦ 薪酬基准 |
| ④ 最近变化（近期动态） | ⑧ 成长发展 |

**五条纪律：**

- **downside-first 先证伪** — 优先排查能一票否决的硬风险（欠薪、被执行、大规模裁员、造假、违法），再谈优点
- **风险 ≠ 不确定性** — 风险是"有证据的坏结果"（可查证、可筛除）；不确定性是"无证据的未来"（只能定价、不能消除）
- **证据先行，结论在后** — 任何结论都要能追溯到证据行
- **营销稿仅作线索** — 公关通稿只作线索，须独立来源交叉印证后才当事实
- **红绿灯绑定证据** — 灯色由证据表的硬风险记录推导，不得主观发挥

*Four stages in strict order. The critical one is stage 2: collect evidence without drawing conclusions. Five disciplines govern the whole flow, the first being downside-first — hunt for the deal-breakers before you count the upsides.*

## 安装 / Installation

这是一个标准 Agent Skills 目录：`SKILL.md` + `references/` + `assets/`。

### 最省事：让你的 agent 自己装

把下面这句话直接发给你在用的 AI agent（Claude Code / WorkBuddy / Cursor / VS Code Copilot 等），它会自己下载并放到正确位置：

> 帮我安装这个 Agent Skill：https://github.com/Aelita003/look-before-you-leap
> 把它 clone 到你的 skills 目录，目录名保持 `look-before-you-leap`。

装完重启 agent 即可生效。

### 手动安装

clone 到你的 skills 目录，目录名保持 `look-before-you-leap`（SKILL.md 里的 `name` 字段须与目录名一致）：

```bash
git clone https://github.com/Aelita003/look-before-you-leap.git ~/.claude/skills/look-before-you-leap
```

常见 skills 目录：Claude Code `~/.claude/skills/`、WorkBuddy `~/.workbuddy/skills/`、VS Code Copilot `.agents/skills/`（项目内）。

### Quick install

Paste this into your agent:

> Install this Agent Skill: https://github.com/Aelita003/look-before-you-leap — clone it into your skills directory, keeping the folder name `look-before-you-leap`.

Or clone it manually into your agent's skills directory. Keep the directory name `look-before-you-leap` — the `name` field in SKILL.md must match its parent directory.

## 使用 / Usage

直接用自然语言触发，无需记命令：

- 「帮我背调一下 XX 公司」
- 「XX 公司值得去吗」
- 「了解一下 XX 这家公司」
- 「XX 靠不靠谱」

可以补充关注重点（如特别关心加班、薪酬、稳定性）和目标岗位，报告会更贴合你的情况。

*Just ask in plain language — no commands to memorize.*

## 目录结构 / Structure

```
look-before-you-leap/
├── SKILL.md                            # 技能主体：4 阶段工作流 + 5 条纪律
├── LICENSE                             # CC BY-NC 4.0
├── references/
│   ├── search-protocol.md              # 检索来源与策略（阶段 2 必读）
│   ├── evidence-table-spec.md          # 证据清单字段规范与冲突仲裁（阶段 2 必读）
│   └── company-type-adaptation.md      # 四类公司的调研侧重与专项检查（阶段 1、3 必读）
└── assets/
    └── report-template.html            # HTML 报告模板（阶段 4 填充）
```

## 许可 / License

本作品采用 **CC BY-NC 4.0**（署名—非商业性使用 4.0 国际）许可。

- ✅ **免费**：个人求职使用、学习、研究、修改、分享（须署名，并保留本许可声明）
- ❌ **需授权**：任何商业用途——包括用本 skill 或其产出报告提供付费服务、嵌入商业产品或企业内部系统、作为商业产品的一部分分发

商业授权咨询：通过 [@Aelita003](https://github.com/Aelita003) 联系。

*Free for personal, educational and non-commercial use with attribution. **Commercial use requires a separate license** — including using this skill or its output to provide paid services, embedding it in a commercial product or internal company system, or distributing it as part of one. For commercial licensing, reach out via [@Aelita003](https://github.com/Aelita003).*

> 说明：带"禁止商业使用"条款的许可**不属于开源许可**（不符合 OSI 开源定义第 6 条"不得歧视使用领域"）。本项目准确的说法是"免费开放给个人使用"或"源码可见（source-available）"。
>
> *Note: a non-commercial license is not an open-source license — it does not meet clause 6 of the OSI Open Source Definition. This project is "source-available" and free for personal use.*

## 免责 / Disclaimer

报告基于**公开信息**生成，不构成法律尽职调查、投资尽调或职业建议。

结论受**检索范围与截止日期**限制——绿灯只表示"在检索范围内未发现硬风险"，**不等于"确认安全"**，更不等于推荐入职。

*Output is based on public information and does not constitute legal, investment or career advice. A green light means no hard risk was found within the search scope — it does not mean the company is safe.*

---

## 背景 / Background

来自一个把"求职"当成"尽调"来做的人：十年科技制造业运营管理经验，长期在信息不全的情况下做判断，习惯先把证据摆齐再下结论。这个 skill 是把那套方法固化下来，给同样在挑公司的人用。

*Built by someone who has spent a decade making operational calls with incomplete information — and learned to line up the evidence before forming the conclusion.*
