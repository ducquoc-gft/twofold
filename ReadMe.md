## CL - twofold

Compaction Lines - [twofold](https://github.com/ducquoc-gft/twofold) (2F, sl).

Inspired by [cc-sl](https://github.com/ducquoc-gft/cc-sl), [gemma4-fast-sonnet](https://ollama.com/ducquoc/gemma4-fast-sonnet).

---

## What It Does

Switches LLM's response style to brief, concise communication. Articles gone. Filler gone. Hedging gone. Technical substance stays intact. Code blocks and error messages always quoted exactly.
<details>
<summary>Usefulness: cuts collectively tokens out 50%-90%</summary>
 kind of x2 your session time until reaching compaction/limitation, not to mention concentration time.</details>

--- 

## Skill Installation

Copy the whole "twofold" folder which contains "SKILL.md" to your LLM CLI config `skills` folder.

- Claude Code (project): `.claude/skills` , e.g. ```cp -r skills/twofold .claude/skills/```
- Claude Code (user): `~/.claude/skills` , e.g. ```cp -r skills/twofold ~/.claude/skills/```

Then /reload-plugins , or restart the session.

Alternatively: 

- (ClaudeCode et al) NPX: ```npx skills add ducquoc-gft/twofold```

---

## Trigger Phrases

- `/twofold`
- `twofold mode`
- `use twofold`
- `/2f`
- `2f mode`
- `use 2f`
- `/sl`
- `sl mode`
- `use sl`
- `be brief`
- `trả lời ngắn`
- `shorthand longform`
- `simple lengthy`

---

## Intensity Levels

Switch anytime with `/twofold <level>`. Default is **long**.

| Level | Style |
|-------|-------|
| `short` | No filler or hedging. Articles and full sentences kept. Professional but tight. |
| `long` | Drop articles. Fragments OK. Short synonyms. Classic brief. |
| `cc` | ConCise frugal. Abbreviate everything (DB/auth/fn/req/res). Arrows for causality. One word when one word enough. |

---

## Quick Example

**Prompt:** "What is frugal?"

<details>
<summary>Normal response:</summary>

```text
Frugal means being careful and economical with resources — spending or using as little as possible without waste.

In everyday usage: avoiding unnecessary expense, getting good value, not being extravagant.

Distinct from cheap: frugal is deliberate and principled; cheap implies low quality or unwillingness to spend even when warranted.
```
</details>

| Level | Response | Words | Tokens | % shorter |
|-------|----------| ----- | ------ | --------- |
| short | "Frugal means using the minimum resources needed to achieve a goal, with no waste." | 15 | 17 | 79% |
| long  | "Min resources, max output. No waste." | 6 | 9 | 89% |
| cc    | "Min res → max output. No waste." | 6 | 8 | 90% |


<details><summary>"What is Kakeibo?"</summary>

| Level | Response |
|------|----------|
| short | "Kakeibo is a Japanese budgeting method focused on mindful spending. You write down income, expenses, and savings goals by hand, then reflect on your habits each month. The act of writing — not apps — is the point." |
| long | "Japanese budgeting method. Write income/expenses by hand, reflect monthly. Idea: mindfulness through pen-and-paper. 4 questions each month: how much earned, how much spent, how much saved, how to improve." |
| cc | "JP budgeting. Hand-write income/expenses. Monthly reflect. Mindfulness > apps. 4Q: earned? spent? saved? improve?" |

([link](https://ducquoc.wordpress.com/2026/01/04/kakeibo-con-duong-tiet-kiem/))
</details>

---

## Auto-Clarity Exceptions

twofold mode pauses automatically for:

- Security warnings
- Irreversible or destructive action confirmations
- Multi-step sequences where fragment order risks misread
- Situations where the user is confused

Normal twofold resumes immediately after the critical part.

---

## Boundaries

- Code, commits, and PRs: always written normally regardless of level.
- Level persists across the session until changed.
- `stop twofold` or `stop 2f` or `stop sl` or `normal mode` exits twofold entirely.

