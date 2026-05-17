## CL - twofold

Compaction Lines - twofold (2F, sl).

Inspired by [linecount-maven-plugin](https://github.com/ducquoc-gft/linecount-maven-plugin), [understand-anything](https://github.com/Lum1104/Understand-Anything).

---

## What It Does

Switches Claude's response style to terse, caveman-like communication. Articles gone. Filler gone. Hedging gone. Technical substance stays intact. Code blocks and error messages always quoted exactly.

--- 

## Skill Installation

Copy the whole "twofold" folder which contains "SKILL.md" to your LLM CLI config `skills` folder.

- Claude Code (project): `.claude/skills` , e.g. ```cp -r skills/twofold .claude/skills/```
- Claude Code (user): `~/.claude/skills` , e.g. ```cp -r skills/twofold ~/.claude/skills/```

Then /reload-plugins , or restart the session.

Alternatively: 

- (Experimenting) NPX: ```npx skills add ducquoc-gft/twofold```

---

## Trigger Phrases

- `twofold mode`
- `use twofold`
- `talk like twofold`
- `2f mode`
- `use 2f`
- `talk like 2f`
- `sl mode`
- `use sl`
- `talk like sl`
- `/twofold`
- `/2f`
- `/sl`
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
| `long` | Drop articles. Fragments OK. Short synonyms. Classic caveman. |
| `v-short` | Semi-classical Vietnamese. Drop filler, keep grammar structure. |
| `v-long` | Maximum classical Vietnamese compression. Extreme terseness. |

---

## Quick Example

**Prompt:** "Explain database connection pooling."

| Level | Response |
|-------|----------|
| short | "Connection pooling reuses open connections instead of creating new ones per request. Avoids repeated handshake overhead." |
| long | "Pool reuse open DB connections. No new connection per request. Skip handshake overhead." |
| v-short | "Pool = reuse DB conn. Skip handshake → fast under load." |
| v-long | "Tái sử dụng kết nối mở. Bỏ qua bước bắt tay." |

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
