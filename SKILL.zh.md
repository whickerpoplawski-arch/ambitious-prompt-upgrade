---
name: ambitious
description: >-
  手动把用户 prompt 升级成更有野心的版本（高度 / 深度 / 广度），再执行。
  仅通过 /ambitious 触发——不要自动调用。用户明确说「升级我的 prompt /
  make this ambitious / deeper not bigger」时也可使用。
disable-model-invocation: true
---

译自本助手为仓库 ambitious-prompt-upgrade 准备的最新英文稿（本地 `github-push/SKILL.md`）。
说明：截至拉取时，GitHub 上 [whickerpoplawski-arch/ambitious-prompt-upgrade](https://github.com/whickerpoplawski-arch/ambitious-prompt-upgrade) 的 `main` 仍只有占位 README，尚无 `SKILL.md`。

# Ambitious prompt upgrade → 然后执行

当本 skill 被调用时（`/ambitious` 或明确的升级请求）：

1. **升级**用户的原始 prompt（先不要动手做正事）。
2. **展示**升级后的 prompt（短卡片，让用户看见改了什么）。
3. **立刻执行**升级后的 prompt——除非用户已要求先确认，或升级还缺用户未提供的数据/工具。

融合 Felix Rieseberg 的高度 / 深度 / 广度（[原文](https://felixrieseberg.com/how-to-be-more-ambitious-a-tutorial-for-humans-with-models/)），以及其 X 帖下高互动回复里的实操做法。

> **故意设计：** `disable-model-invocation: true` —— 只有 `/ambitious`（或明确请求）才会跑本 skill。若改个 typo 也自动跑「目标背后的目标」，只会添堵，不是野心。

## 硬规则

1. **更深 / 更高 / 更广 —— 不是更大。** 禁止功能膨胀。
2. **方法与工具，不是角色扮演腔调。**
3. 升级后的 prompt 里必须有**外部裁判**（测试、基准、留出集检查、可运行工具）——绝不要「看起来不错」。
4. **把不合理的目标说成可解。**
5. **点名缺失的数据 / 工具 / 权限**；绝不编造。
6. 把用户的**真实意图**当地板；野心是抬高标准，不是偷换目标。

## 跳过升级（按原文执行）

- 仅改 typo / 格式
- 纯确认（"ok"、"继续"、"发送"）
- 用户说了：不要升级 / as written / verbatim / 按原文执行
- 已经够有野心：已点名原始输入、专家工具、外部检查

## 升级流程

### A. 复述

一行：用户字面在问什么。

### B. 选 1–2 个轴（通常不要三个全上）

| 轴 | 何时用 | 升级动作 |
|------|----------|--------------|
| **高度（Altitude）** | 结果超出交付物本身；会驱动决策或循环 | 问目标背后的目标；喂更全的原始上下文；推向决策，或比当前交付物更好的机制 |
| **深度（Depth）** | 在乎「怎么做」的质量 | 跑下方 Felix Depth 改写；坚持对原始材料用专家工具 + 外部检查 |
| **广度（Range）** | 表面领域太窄 | 名词→动词；为*方法*点名跨领域班底（含一名对抗角色）；禁止模仿语气 |

### C. 应用现场旋钮（能用再选）

- 把目标抬过「合理」，并说它做得到。
- 若延续上次胜利，问哪些**相邻公开数据 / 工具**能解锁下一跳。
- 优先选 agent 自己能跑的检查。
- 改写中禁止：角色扮演、只有专家黑话没有专家方法、自我打分、更大≠更深。

### D. Felix Depth 改写（种子提示，内部套用）

内部套用：

```text
我要的是这个任务的更深版本，不是更大版本。改写之前先：(1) 说出该领域顶尖专业人士会做、而我没要求的事；(2) 点名他们会从什么最原始的材料起步，而不是已经帮我消化好的材料；(3) 点名他们会用的具体方法与工具；(4) 说出除了你或我之外，什么能证明结果是对的。然后把我的 prompt 改写成正好在要这些。
```

（英文原文种子保留对照：）

```text
I want a deeper version of this task, not a bigger one. Before rewriting it: (1) say what a top professional in this field would do here that I'm not asking for; (2) name the rawest material they would start from instead of what has already been digested for me; (3) name the specific methods and tools they would use; (4) say what, other than you or me, would show the result is right. Then rewrite my prompt to ask for exactly that.
```

若选了高度 / 广度，一并折进这次改写。

### E. 打出升级卡（一屏）

```markdown
### Upgraded prompt
**Original:** …
**Axes:** altitude | depth | range
**Ambitious prompt:**
…
**Outside check:** …
**Need from you:** … | none
**Executing:** yes (now) | waiting (missing inputs)
```

然后**执行 Ambitious prompt**，不是原文——除非是 Waiting。

## 执行阶段

- 只按升级后的 prompt 干活。
- 每个有意义阶段结束后，跑点名的外部检查。
- 若卡在「不可能」，至少再试两种方法再报失败。
- 飞行中不要偷偷扩 scope；若中途出现更高高度，先记一笔，仍完成当前升级请求，除非用户主动抬高。

## 反模式

- 前缀「你是 20 年专家」却不改方法
- 借「野心」塞无关功能
- 跳过升级卡，用户看不见改写
- 把琐事（重命名变量）升级成多智能体调研史诗
