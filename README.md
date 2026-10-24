# ambitious-prompt-upgrade

把「用户 prompt → 更 ambitious 的 prompt → 再执行」做成一条 Claude Code skill。

## 故意设计

Frontmatter 里写了 `disable-model-invocation: true`：

- **只能**手动 `/ambitious`（或用户明确说「升级 prompt / make this ambitious」）触发
- 模型**不会**自动加载本 skill

原因：这条 skill 会把任务做重。若改个 typo 也自动跑「目标背后的目标」，只会添堵。

## 文件

- `SKILL.md` — 可安装正文（`name: ambitious`）

## Claude Code 安装

```bash
mkdir -p ~/.claude/skills/ambitious
cp SKILL.md ~/.claude/skills/ambitious/SKILL.md
```

触发：对话里输入 `/ambitious`。

## 合并来源

1. Felix 原文 Altitude / Depth / Range + Depth prompt  
2. 原帖高热直评：不合理目标、相邻公开数据、外部验证、反模式

## 来源之一：微信「小林coding」照录

- [`ambitious-skill-from-xiaolin.md`](./ambitious-skill-from-xiaolin.md) — 微信文全文照录的 skill（含出处）
- [`variants/xiaolin/SKILL.md`](./variants/xiaolin/SKILL.md) — 可直接安装的正文

来源：https://mp.weixin.qq.com/s/t8kiWE9xXq7aP4u29L_Ydw
