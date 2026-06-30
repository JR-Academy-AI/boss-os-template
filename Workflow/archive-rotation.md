# SOP — 归档滚动（live → archive）

## 触发条件
定期（每周/每月）保持各 live 文件只剩当前活跃，防止越长越大。

## 前置
- 永不删，只移动（铁律 #2）

## 步骤
按区逐个滚动：
| 区 | 把什么移走 | 移到哪 |
|----|-----------|--------|
| `Personal/Agenda/upcoming.md` | 已过期/已办 | `Personal/Agenda/archive/YYYY-MM.md` |
| `Personal/Events/upcoming.md` | 已过期 | `Personal/Events/archive/YYYY-MM.md` |
| `Tasks/open.md` | 状态=完成 | `Tasks/archive/YYYY-MM-done.md` |
| `Decisions/pending.md` | 已拍板 | `Decisions/log/YYYY-Qn.md`（记日期/决策/理由/来源） |
| `Cashflow/latest.md` | 被新快照取代的旧版 | `Cashflow/archive/YYYY-MM.md` |

## 产出
- 各 live 文件精简到只剩当前活跃；历史完整留在 archive。

## 检查清单
- [ ] 没有任何内容被删除，只是移动
- [ ] archive 文件按 年-月/季 命名
- [ ] live 文件现在一屏能看完
