# Official Source Map

last_reviewed: `2026-04-15`

이 문서는 `agent-skills` 주제의 1차 출처와, 각 런타임이 공식적으로 요구하는 최소 구조를 함께 정리한 맵입니다.

## How To Use This Map

- `공식 최소 구조`
  - 각 런타임이 실제로 요구하거나 권장하는 파일/필드/디렉터리 구조
- `공식 요구사항`
  - 필수 메타데이터, 호출 경계, supporting files, subagent 분리 여부
- `teaching schema`
  - lesson 2에서 학생 이해를 돕기 위해 덧붙인 `8개 블록` 설명 프레임

주의:
- 아래 표의 `official minimum`은 공식 문서 기준이다.
- lesson 2의 `Identity / Trigger / Input Contract / ...` 8블록은 공식 최소 요구사항이 아니라, 이 프로젝트의 teaching schema다.

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

## Official Minimum Structure And Requirements

| runtime | official minimum | official requirements | official note |
|---|---|---|---|
| OpenAI Codex | skill은 디렉터리이며 `SKILL.md`가 entrypoint다. 공식 예시는 `scripts/`, `references/`, `assets/`, `agents/openai.yaml`를 optional로 둔다. | `SKILL.md`에는 `name`, `description`이 필요하다. Codex는 먼저 metadata만 읽고, skill을 쓰기로 결정했을 때 본문을 로드한다. implicit invocation은 `description`에 의존한다. | [Codex Skills](https://developers.openai.com/codex/skills) |
| Claude Code | skill은 `.claude/skills/<skill-name>/SKILL.md` 형태로 저장한다. supporting files를 같은 skill 디렉터리에 둘 수 있다. | `SKILL.md`는 YAML frontmatter + Markdown body 구조다. `description`은 권장 필드이며 자동 호출 판단에 쓰인다. `name`은 slash command가 되며, 생략 시 디렉터리명을 쓸 수 있다. | [Claude Code Skills](https://code.claude.com/docs/en/skills) |
| Gemini CLI | skill은 디렉터리이며 `SKILL.md`가 유일한 required file이다. 공식 권장 구조는 `scripts/`, `references/`, `assets/`다. | `SKILL.md`는 YAML frontmatter + Markdown body 구조다. `name`은 디렉터리명과 맞는 고유 식별자여야 하고, `description`은 skill이 무엇을 하며 언제 써야 하는지 설명해야 한다. | [Creating Skills](https://geminicli.com/docs/cli/creating-skills/) |
| Agent Skills Open Standard | skill은 최소한 `SKILL.md`를 가진 디렉터리다. optional 디렉터리는 `scripts/`, `references/`, `assets/`다. | `name`, `description`은 required다. optional 필드는 `license`, `compatibility`, `metadata`, `allowed-tools`다. body는 자유로운 Markdown instructions다. | [Skill Specification](https://agentskills.io/specification) |

## Skill And Subagent Boundary In Official Docs

| runtime | skill structure | subagent structure | lesson implication |
|---|---|---|---|
| OpenAI Codex | skill은 `SKILL.md` 중심 capability package다. | subagent는 `.codex/agents/*.toml`로 정의하며 `name`, `description`, `developer_instructions`가 required다. | `skill != subagent`를 분명히 가르쳐야 한다. skill은 reusable workflow, subagent는 delegated execution unit이다. |
| Claude Code | skill은 `.claude/skills/.../SKILL.md` 기반 instruction package다. | subagent는 `.claude/agents/*.md`로 정의하며 YAML frontmatter + system prompt body를 쓴다. | Claude에서는 `skill = playbook`, `subagent = specialized AI assistant`로 설명하는 편이 정확하다. |

## Course Translation Rule

이 course에서 공식 문서를 lesson 문장으로 번역할 때는 아래 순서를 유지한다.

1. 공식 문서의 최소 구조를 먼저 말한다.
2. 그 다음 `왜 이것이 reusable agent capability처럼 읽히는가`를 설명한다.
3. 마지막에만 lesson용 `8블록 teaching schema`를 덧붙인다.
