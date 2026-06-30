# SKILLS — 给老板 OS 配的 skills

老板 OS 的每个环节，配一个能干活的 skill。分两类：**本地已有**（直接用）、**网上现成**（按需装）。
装外部 skill 前先看一眼 SKILL.md 内容再决定（铁律 #3/#4：涉及财务/对外要谨慎）。

## 本地已有（你账号里已经有，直接用）
| Skill | 接哪条流 | 说明 |
|-------|---------|------|
| `invoice-extract-au` | `Finance/` · `monthly-finance.md` | 澳洲发票/账单抽取，GST/ABN/ATO 校验，输出 JSON+CSV。AUD 默认与 OS 铁律一致，**财务流首选** |

## 网上现成（按需安装，已筛过对口的）

### 会议（Meetings/ · meeting-notes.md）
- **meeting-insights-analyzer**（ComposioHQ/awesome-claude-skills）— 分析会议转写：发言占比、领导风格、冲突回避等。补足我们 SOP 只做"拆决策+任务"之外的洞察。

### 财务 / 决策（Cashflow/ · Decisions/）
- **financial-analyst**（alirezarezvani/claude-skills）— DCF、预算、预测建模，跨公司现金流分析。
- **saas-metrics-coach**（同上）— 收入/单位经济模型，适合 SaaS 类子公司。
- **c-level-advisor**（同上）— 全 C-suite 视角（CEO/CFO/COO…），辅助 `Decisions/pending.md` 拍板。

### 收件箱 / 沟通（Inbox/ · inbox-triage.md）
- **capture**（alirezarezvani/claude-skills）— 把零散输入转成结构化待办，正好接 Inbox 分拣。
- **email pair**（同上）— 收件箱整理 + 邮件优先级（对外发信仍守铁律 #4：先确认）。

### 业务运营（Companies/ · projects.md）
- **vendor-management** / **process-mapper**（alirezarezvani/claude-skills）— 供应商关系、流程文档化。

## 来源仓库
- alirezarezvani/claude-skills — C-level / 业务运营 / 财务，最对口老板
  https://github.com/alirezarezvani/claude-skills
- ComposioHQ/awesome-claude-skills — 含 meeting-insights-analyzer
  https://github.com/ComposioHQ/awesome-claude-skills
- VoltAgent/awesome-agent-skills — 1000+ 跨平台 skills 总目录
  https://github.com/VoltAgent/awesome-agent-skills
- claudemarketplaces.com — 每日更新的 skills/插件目录

## 不放进来的（老板 OS 用不上）
- `ai-engineer-jd-analyzer` / `ai-engineer-resume-tailor` — 那是**打工人版**（求职）的，不属于老板 OS。
- `course-outline-auditor` — JR Academy 课程审查用，与老板 OS 无关。
