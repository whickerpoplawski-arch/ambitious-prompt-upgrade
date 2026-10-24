---
name: ambitious
description: >-
  Manually upgrade a user prompt into a more ambitious version (altitude /
  depth / range), then execute it. Trigger with /ambitious only — do not
  auto-invoke. Also when the user explicitly says upgrade my prompt, make
  this ambitious, or deeper not bigger.
disable-model-invocation: true
---

# Ambitious prompt upgrade → then execute

When this skill is invoked (`/ambitious` or an explicit upgrade ask):

1. **Upgrade** the user's raw prompt (do not start the real work yet).
2. **Show** the upgraded prompt in a short card (so the user sees what changed).
3. **Execute** the upgraded prompt immediately unless they already said to wait for confirm, or the upgrade needs data/tools they have not given.

Combines Felix Rieseberg's altitude / depth / range ([essay](https://felixrieseberg.com/how-to-be-more-ambitious-a-tutorial-for-humans-with-models/)) with field practices from high-engagement replies under his X post.

> **Intentional:** `disable-model-invocation: true` — only `/ambitious` (or an explicit ask) runs this skill. Auto-invoking on every chore (e.g. a typo fix) would add friction, not ambition.

## Hard rules

1. **Deeper / higher / wider — not bigger.** No feature sprawl.
2. **Methods and instruments, not role-play voices.**
3. **Outside judge** in the upgraded prompt (test, benchmark, held-out check, runnable tool) — never "looks good".
4. **Unreasonable target stated as solvable.**
5. **Name missing data / tools / access**; never invent them.
6. Keep the user's **true intent** as the floor; ambition raises the bar, it does not swap the goal.

## Skip upgrade (run original as-is)

- Typo / formatting-only edits
- Pure acknowledgements ("ok", "继续", "发送")
- User said: 不要升级 / as written / verbatim / 按原文执行
- Already-ambitious prompts that already name raw inputs, expert tools, and an outside check

## Upgrade procedure

### A. Restate

One line: what the user literally asked.

### B. Choose 1–2 axes (usually not all three)

| Axis | Use when | Upgrade move |
|------|----------|--------------|
| **Altitude** | Outcome beyond the artifact; will drive decisions or a recurring loop | Ask goal-beyond-goal; feed fuller raw context; push decisions or a better mechanism than the current deliverable |
| **Depth** | Quality of how the work is done | Run Felix Depth rewrite (below); insist on expert tools on raw material + outside check |
| **Range** | Surface domain is too narrow | Nouns→verbs; name a multi-field crew for *methods* (include one adversarial); no mimicry of tone |

### C. Apply field knobs (pick what fits)

- Raise the target past "reasonable" and say it is achievable.
- If this continues a prior win, ask which **adjacent public datasets / instruments** unlock the next leap.
- Prefer checks the agent can run itself.
- Forbid in the rewrite: role-play, expert jargon without expert methods, self-grading, bigger≠deeper.

### D. Felix Depth rewrite (verbatim seed)

Internally apply:

```text
I want a deeper version of this task, not a bigger one. Before rewriting it: (1) say what a top professional in this field would do here that I'm not asking for; (2) name the rawest material they would start from instead of what has already been digested for me; (3) name the specific methods and tools they would use; (4) say what, other than you or me, would show the result is right. Then rewrite my prompt to ask for exactly that.
```

Fold altitude / range into that rewrite when those axes were selected.

### E. Emit the upgrade card (one screen)

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

Then **execute the Ambitious prompt**, not the original — unless Waiting.

## Execution phase

- Work only from the upgraded prompt.
- After each meaningful phase, run the named outside check.
- If stuck on "impossible", try at least two other methods before reporting failure.
- Do not silently re-expand scope mid-flight; if a higher altitude appears mid-work, note it and finish the current upgraded ask unless the user raises it.

## Anti-patterns

- Prefixing "you are a 20-year expert" with no method change
- Adding unrelated features under "ambition"
- Skipping the upgrade card so the user cannot see the rewrite
- Upgrading chores (rename a variable) into multi-agent research epics
