# Official Source Map

last_reviewed: `2026-04-15`

이 문서는 `agent-skills` 주제의 1차 출처만 모아 둔 맵입니다.

## OpenAI Codex

| source | topic | why it matters |
|---|---|---|
| [Codex Skills](https://developers.openai.com/codex/skills) | Codex의 skill 개념, 구조, 사용 맥락 | lesson 2에서 Codex가 skill을 reusable workflow로 다루는 근거 |
| [Codex Subagents](https://developers.openai.com/codex/subagents) | Codex의 subagent 개념 | skill과 subagent를 분리해 설명할 공식 근거 |

## Anthropic Claude Code

| source | topic | why it matters |
|---|---|---|
| [Claude Code Skills](https://code.claude.com/docs/en/skills) | Claude Code skill 구조와 open standard 연결 | Claude가 skill을 지원하지만 subagent와 다르게 설명한다는 근거 |
| [Claude Code Sub-agents](https://code.claude.com/docs/en/sub-agents) | Claude의 subagent 구조 | `skill != subagent` 구분을 lesson에서 명시할 근거 |

## Google Gemini CLI

| source | topic | why it matters |
|---|---|---|
| [Gemini CLI Skills](https://geminicli.com/docs/cli/skills/) | Gemini CLI의 skill 개념과 activation 흐름 | lesson 2에서 Gemini skill의 self-contained 구조를 설명하는 근거 |
| [Creating Skills](https://geminicli.com/docs/cli/creating-skills/) | skill 작성 최소 요건과 `SKILL.md` | skill 구조를 학생이 직접 작성할 때의 기준 |

## Agent Skills Open Standard

| source | topic | why it matters |
|---|---|---|
| [Agent Skills Home](https://agentskills.io/home) | open standard 개요 | 벤더 중립 기준점 |
| [What Are Skills](https://agentskills.io/what-are-skills) | skill 개념 정의 | skill을 capability 단위로 설명하는 공통 근거 |
| [Skill Specification](https://agentskills.io/specification) | 최소 필드와 형식 | `name`, `description` 등 핵심 메타데이터 기준 |
| [Skill Creation Best Practices](https://agentskills.io/skill-creation/best-practices) | 작성 원칙 | lesson용 설계 체크리스트 근거 |
