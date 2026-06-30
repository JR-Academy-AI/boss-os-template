# Boss OS — 多公司老板 OS 模板

一个可"盖章复制"的 Markdown 操作系统骨架，给**同时管理多家公司的老板**直接使用。
纯 Markdown，无 build/test/run。继承 Lightman AI OS 的三层信任模型，新增**公司间强隔离**。

## 它解决的核心矛盾

老板管 N 家公司，OS 必须同时满足两个相反的力：

```
每家公司：强隔离 ────────► Companies/<company>/   财务·团队·决策 绝不串到别家
跨公司：统一视图 ──────► Agenda/ Tasks/ Decisions/ Cashflow/   只读汇总各公司
```

## 目录结构

```
{boss}-os/
├── PROFILE.md            老板是谁、管哪几家公司、决策风格
├── Rules/               铁律（含"公司间 context 不得串味"）
│  ── 老板本人的（Personal，跟公司无关）──
├── Personal/
│   ├── Agenda/          自己的工作议程：要开的会/deadline/要拍的决策 (upcoming.md + archive/)
│   └── Events/          自己的生活事件：约见/差旅/应酬/私人 (upcoming.md + archive/)
│  ── 跨公司汇总区（每个都是文件夹，不是单文件）──
├── Tasks/               跨公司任务  (open.md + archive/)
├── Decisions/           决策  (pending.md + log/)
├── Cashflow/            现金流汇总  (latest.md + archive/)
├── Weekly/              周报  (每周一个文件 YYYY-Www.md)
│  ── 各公司 ──
├── Companies/
│   ├── _template/       ← 开新公司就复制这个填空
│   └── <company>/       overview/team/projects + Finance/ + Meetings/
├── Workflow/            SOP：建 OS、整理会议记录
└── Inbox/               杂项原始件中转站（邮件/截图/随手记），AI 归档后清走
```

## 核心规则：会累积的都是文件夹，不是单文件

agenda / tasks / decisions / cashflow / 会议……都会**随时间无限增长**。
所以每个都是**文件夹**，统一用「live 文件 + archive 归档」模式，单文件永远只剩当前活跃的，扫起来快、也不会撑爆：

| 区 | live（只看这个） | 归档去哪 |
|----|------------------|----------|
| Personal/Agenda/ | `upcoming.md`（只剩未来的） | 过期 → `archive/YYYY-MM.md` |
| Personal/Events/ | `upcoming.md`（只剩未来的） | 过期 → `archive/YYYY-MM.md` |
| Tasks/ | `open.md`（只剩没完成的） | 完成 → `archive/YYYY-MM-done.md` |
| Decisions/ | `pending.md`（只剩没拍板的） | 拍板 → `log/YYYY-Qn.md` |
| Cashflow/ | `latest.md`（最新快照） | 旧快照 → `archive/YYYY-MM.md` |
| Weekly/ | 当周文件 | 天然每周一个文件 |
| Companies/<x>/Meetings/ | — | 天然每场会一个文件 |

## 三条不混的通道

| 通道 | 时态 | 放什么 | 位置 |
|------|------|--------|------|
| **Agenda / Events** | 未来 | 老板自己的：工作议程 / 生活事件 | `Personal/` |
| **Meetings** | 过去 | 已开完的会的记录 → 产出决策+任务 | `Companies/<x>/Meetings/` |
| **Inbox** | 当下杂项 | 待归档的零散原始件，与会议无关 | `Inbox/` |

会议的生命线：**Personal/Agenda 排期 → 开会 → 直接进公司 Meetings/** —— 不经过 Inbox。

## 怎么"快速做出来给一个老板用"

1. 整包复制本目录 → 改名为 `{boss}-os/`
2. 跑 `Workflow/init-boss-os.md` 这个 SOP：回答几个问题（管几家公司、要不要财务、决策风格）
3. 每家公司：复制 `Companies/_template/` 填空
4. 老板开始往 `Inbox/` 丢东西，AI 按规则整理进对应公司，汇总区自动更新

## 数据流（继承自 Lightman AI OS）

```
Raw 进来 → Inbox/ 或 各公司 Raw 区  (原样存，不动)
              │  AI 审计/整理（保留原始，distilled 写 Structured 并引用来源）
              ▼
   各公司 overview/projects/team + 跨公司汇总区   (结构化、可信)
   各公司 Finance/                                (私有，最敏感)
```

进入任何 `{boss}-os/` 时，AI 的阅读顺序：`PROFILE.md` → `Rules/` → 任务相关的公司目录。
