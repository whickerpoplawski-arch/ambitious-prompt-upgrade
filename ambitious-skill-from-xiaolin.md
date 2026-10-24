# ambitious skill（来自微信文「小林coding」）

- **来源文章**：https://mp.weixin.qq.com/s/t8kiWE9xXq7aP4u29L_Ydw
- **思想来源**：Felix Rieseberg — [How to be more ambitious](https://felixrieseberg.com/how-to-be-more-ambitious-a-tutorial-for-humans-with-models/)（2026-10-13）
- **说明**：下方 `SKILL.md` 正文按微信文「06｜怎么把这套思路做成 Skill？」全文照录，便于本地安装；非 Felix 本人仓库发布。
- **抓取日期**：2026-10-24（合并入 whickerpoplawski-arch/ambitious-prompt-upgrade）

---

建议安装路径：`~/.claude/skills/ambitious/SKILL.md`

有两个地方是原文故意这么写的：

1. `disable-model-invocation: true` — 只能手动 `/ambitious` 触发，AI 不会自己调用。这个 Skill 会让任务变重，改个错别字也来一套「目标背后的目标」，只会添堵。
2. 最后一条「不扩大任务范围」— 对应 Felix「更深，不是更大」。

```markdown
---
name: ambitious
description: 按 Felix Rieseberg 的「高度、深度、广度」三种野心，把一个普通任务改写成更有野心的版本，先出方案、等确认再动手。用户输入 /ambitious 时使用。
argument-hint: [你的任务]
disable-model-invocation: true
---

# 更有野心地完成任务

用户的任务：$ARGUMENTS

先别开工。按下面四步把任务想高、想深、想宽，输出方案，等用户确认后再执行。

## 第一步：高度，找到目标背后的目标

- 问自己：用户做完这件事之后，希望发生什么？谁会看这个结果，看完要做什么决定？
- 如果更高一层的目标更值得做，就把任务往上抬一层，写清楚抬升后的任务是什么。
- 做完还要开会讨论、还要有人接着跟进的任务，适合往上抬；纯创作或一次性的小任务，保持原来的层级。
- 不要抬到空泛（比如「帮我赚钱」）。抬升后的目标必须能在当前环境里验证。

## 第二步：深度，像顶尖从业者那样做

我要的是更深的版本，不是更大的版本。先回答四个问题：

1. 这个领域的顶尖从业者，会做哪些用户没提的工作？
2. 他们会从哪些最原始的材料入手，而不是用别人整理好的东西？
3. 他们具体用什么方法和工具？写出名字，不要只写「专业地」。
4. 除了你和用户的判断，还有什么能证明结果是对的？比如测试、基准数据、截图比对、真实数据。

然后定一个「野心目标」：比用户原本的期望高出一个量级，并且明确告诉自己这个目标是能做到的。

## 第三步：广度，借其他领域的方法

1. 名词换动词：把要交付的东西（「一个页面」「一份 PPT」）改写成它要完成的动作（「让第一次来的人 10 秒内记住我是谁」）。
2. 组队：假设这件事极其重要，列出 3～5 个你会请来的专业角色，其中至少一个专门挑错。
3. 每个角色只写一句：他会用什么方法。禁止角色扮演，不要模仿任何人的口吻。

## 第四步：输出方案，等用户确认

按这个格式输出，控制在一屏以内：

- **改写后的任务**：一段话
- **要用的方法和工具**：列表
- **野心目标**：一句话
- **外部验证**：怎么证明做好了，必须是你自己能运行的检查
- **需要用户提供的**：数据、权限、环境，没有就写「无」

最后问用户：按这个方案执行，还是要调整？

## 执行阶段的规则

- 用户确认后再动手。
- 每完成一个阶段，就用第二步定下的外部验证检查一次。不能自己觉得「看起来不错」就算完成。
- 遇到看起来做不到的地方，至少换两种方法试过，再向用户报告。
- 不扩大任务范围：做得更深、更高，不等于加一堆无关的功能。
```

## 相关社区实现（非原文，备查）

- [robonuggets/be-ambitious](https://github.com/robonuggets/be-ambitious)（英文，较完整）
- [latour-ai/skills · ambition-upgrade](https://github.com/latour-ai/skills/blob/main/ambition-upgrade/SKILL.md)
- [wanderingspirit03/ambition-skill](https://github.com/wanderingspirit03/ambition-skill)
